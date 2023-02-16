## Prerequisites
Make sure you have [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [Docker desktop](https://www.docker.com/products/docker-desktop) installed.   
## Installation 
Clone/git pull the repo into any local directory    
```
git https://github.com/rcemper/Beyond-Server-Limits.git   
```
Run the IRIS container with your project:   
```
docker-compose up -d --build   
```
## How to Test it   
- There is a version in C++ precompiled for docker in subdirectory **/cpp/** rccslave(.cpp)  
it is foreseen if special privigeges (?root?) are required    
- The Python variant is not context sensitive and works in Windows and Linux  

First start the Listener  
````
$>python3 <download_dir>/py/rccslave.py  
````
Next  
````
docker-compose exec iris iris session iris  
````
**[or use WebTerminal](http://localhost:42773/terminal/)**  

From Command Prompt  
```` 
USER>Do go^rcc.master(<slave-ip-adr>)
start Remote Command Master
server = 192.168.0.9 port = 6666
Enter command [.=exit master, *** = stop slave & exit master]
??> :whoami
??> :
````
and on the Slave end you see  
the command that is executed  
````
<download-dir>python3 py\rccslave.py  
==> whoami && exit
cemper9\cemper
````
#### Remember:
the command you submit is executed in a subprocess   
It is a single shot and you have to providea all required parameters   
my personal prefence on Windows:
````
??> :Start https://community.intersystems.com
````

[Article in Spanish](https://es.community.intersystems.com/post/rompe-los-l%C3%ADmites-del-servidor)
