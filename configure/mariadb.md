# Configure MariaDB

### Configure MariaDB

(docker로 설치한 경우 명령어에서 `sudo`를 빼고 입력)

`mysql_secure_installation` 설정하기:

```zsh
sudo mysql_secure_installation
```

순서대로 진행:

```zsh
- Current root password: Enter or Input
- Switch to unix_socket authentication?: y
- Change to root password?: n or y & input
- Remove anonymous users?: y
- Disallow root login remotely?: y
- Remove test database and access it?: y
- Reload privilege tables now?: y
```

`/etc/mysql/my.cnf` 열기:

```zsh
sudo nano /etc/mysql/my.cnf
```

MariaDB Prompt 옵션을 최하단에 추가하기:

```zsh
...
[mysql]
prompt='\u @ \h [\d] -> '
```

### Connect to MariaDB

(docker로 설치한 경우 명령어에서 `sudo`를 빼고 입력)

```zsh
sudo mariadb
```
