# dockerfile_ubuntu_zsh_ssh
<br>

### Dockerfile with zsh&ssh in ubuntu
### 우분투에 zsh, ssh를 추가한 도커파일입니다.
### 반복된 설치 작업이 번거로워, 제가 쓰려고 만든 파일입니다~! 
### 도커파일의 코드에 대한 상세한 설명은 [velog](https://velog.io/@dev-jiwonshin/%EB%8F%84%EC%BB%A4%ED%8C%8C%EC%9D%BC-with-sshzsh-in-%EC%9A%B0%EB%B6%84%ED%88%AC)에 적어두었습니다. 

<br>
<br>
<br>
<br>
<br>

## How to use?


```

cd 

git clone https://github.com/Dev-JiwonShin/dockerfile_ubuntu_zsh_ssh.git

docker build -t ubuntu_dockerfile:1.0

docker create -it -P -p 22:22 -p 3307:3306 --name zsh_ssh_0 devjiwonshin/ubuntu_dockerfile:1.0

docker start zsh_ssh_0

docker exec -it zsh_ssh_0 zsh
```


<br>
<br>
<br>
<br>
<br>

## Check your installation
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
