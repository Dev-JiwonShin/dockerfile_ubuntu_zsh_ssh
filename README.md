# dockerfile_ubuntu_zsh_ssh
<br>

### Dockerfile with zsh&ssh in ubuntu
### 우분투에서 zsh, ssh를 추가한 도커파일입니다. 아래 명령어를 따라하시면 

<br>
<br>
<br>
<br>
<br>

## How to use?


```

cd 

git clone this

docker create -it -P -p 22:22 --name zsh_ssh_0 ubuntu_dockerfile:1.0

docker start zsh_ssh_0

docker exec -it zsh_ssh_0 zsh
```



## Check your installation?
```
# If it doesn't work, you should do install again
service ssh start

service mysql start
```




<br>
<br>
<br>
<br>
<br>


## mysql에서 한글이 깨지면 아래 명령어를 입력하세요.
```
vi /etc/mysql/my.cnf
```
```
[client]
default-character-set=utf8

[mysql]
default-character-set=utf8


[mysqld]
collation-server = utf8_unicode_ci
init-connect='SET NAMES utf8'
character-set-server = utf8
```
```
:wq
```
