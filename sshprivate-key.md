# Use RSA public and private key to login without input password

## generate RSA ssh public and private keys

> > ssh-keygen  
> > /var/lib/jenkins/.ssh/id\_rsa  
> > pub key /var/lib/jenkins/.ssh/id\_rsa.pub

first pc \(130.211.141.87\)  
use jenkins account. copy id\_rsa.pub

second pc \(10.128.0.4\)  
login and put "id\_ras.pub content" to ~/.ssh/autorized\_key

back to jenkins job1

> > ssh dev@10.128.0.4 "git clone"

## ssh usage

### ssh files

* ~/.ssh/id\_rsa
  **private-key** ! **should not give it to any one** !

* ~/.ssh/id\_rsa.pub 
  public key

* ~/.ssh/authorized_keys  
  store other persons authorized public keys ~ could store a few public keys  
  when server-pc has client-pc's public key in authorized\_key, client-pc could login in without prompt_

* ~/.ssh/know\_hosts  
  client-PC stores server-PC's ssh service to recognize the ssh service 

### pscp on windows

need to input password everytime  
copy files from windows to remote

```
pscp pi@192.168.0.30:/home/pi/db1.py .
```

copy local readme.txt to remote 's /home/pi folder

```
pscp readme.txt pi@192.168.0.30:/home/pi/
```

### pscp without password prompt

> > [http://www1.se.cuhk.edu.hk/~hmleung/wordpress/?p=1295](http://www1.se.cuhk.edu.hk/~hmleung/wordpress/?p=1295)  
> > use puttygen.exe GUI program to generate a public key \(no ext name\) and a private key \(\*.ppk\)  
> > save private-key at pc1 as ssh\_private\_key.ppk  
> > save public-key at pc2 as ~/.ssh/authorized\_keys

ppk files is used at pscp -i parameter  
public key's content is copied to pc2's ~/.ssh/authorized\_keys

```
pscp -i ssh_private_key.ppk pi@192.168.0.30:/home/pi/db1.py .
```

Same as putty ssh

```
putty -ssh -i c:\users\dalon\Documents\ssh_private_key.ppk pi@192.168.0.30
```

note:~/.ssh/authorized\_keys could be authorized\_keys1 or authorized\_keys2......  
caution: cannot use 2 authroized\_keys

### alias a ssh host

Add login information to ~/.ssh/config

```
Host mypi
    Hostname 192.168.0.10
    Port 22
    User pi
```

### login without password prompt

copy client-PC's id_rsa.pub to server-PC's ~/.ssh/authorized\_keys_

```
bash-client>scp ~/.ssh/id_rsa.pub server-pc:~/client_id_rsa.pub
bash-client>ssh server-pc
>> has a password prompt
bash-server>cat ~/client_id_rsa.pub >> ~/.ssh/authorized_keys
bash-server>logout
>> back to client
bash-client>ssh server-pc
>> NO password prompt !!! success ~
```

if there is any problem, add **-v** to ssh parameter list for more information

 

