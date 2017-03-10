### Jenkins
download jenkins from official webpage
install msbuild plugin
id: daylong
pwd: (where)


### github project

github
http://github.com/notmikeb/WindowsFormsApplication3.git

dos>msbuild
dos>msbuild /t:Clean

note:
It must has README.MD before push other files to github
add remote github repository
git init
git remote add origin https://github.com/notmikeb/WindowsFormsApplication3.git

### windows shell script

dos>ping 127.0.0.1 -n 5 -w 1000
ping will do 5 times and timeout is 1000 ms 
dos>timeout /t 5

### jenkins trigger

JENKINS_URL/job/app3/build?token=TOKEN_NAME

可以透過下列 URL 觸發建置: JENKINS_URL/job/app3/build?token=TOKEN_NAME 或 /buildWithParameters?token=TOKEN_NAME
可以再加上 &cause=原因，參數內容將被記錄到建置原因中。

wget http://127.0.0.1/job/app3/build?token=daylong --user=daylong --password=goto1234 --auth-no-challenge
