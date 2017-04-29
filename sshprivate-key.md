# Use RSA public and private key to login without input password

## generate RSA ssh public and private keys
>> ssh-keygen
/var/lib/jenkins/.ssh/id_rsa
pub key /var/lib/jenkins/.ssh/id_rsa.pub

first pc (130.211.141.87)
use jenkins account. copy id_rsa.pub 

second pc (10.128.0.4)
login and put "id_ras.pub content" to ~/.ssh/autorized_key

back to jenkins job1
>> ssh dev@10.128.0.4 "git clone"


## pscp on windows
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
>> http://www1.se.cuhk.edu.hk/~hmleung/wordpress/?p=1295
use puttygen.exe GUI program to generate a public key (no ext name) and a private key (*.ppk)
save private-key at pc1 as ssh_private_key.ppk
save public-key at pc2 as ~/.ssh/authorized_keys

ppk files is used at pscp -i parameter
public key's content is copied to pc2's ~/.ssh/authorized_keys

```
pscp -i ssh_private_key.ppk pi@192.168.0.30:/home/pi/db1.py .
```

Same as putty ssh
```
putty -ssh -i c:\users\dalon\Documents\ssh_private_key.ppk pi@192.168.0.30
```

note:~/.ssh/authorized_keys could be authorized_keys1 or authorized_keys2......
caution: cannot use 2 authroized_keys




