# Install MariaDB

### Install Using APT Repository

의존성 패키지 설치:

```zsh
sudo apt install apt-transport-https curl
```

MariaDB Official GPG Key 추가:

```zsh
sudo curl -o /etc/apt/trusted.gpg.d/mariadb_release_signing_key.asc 'https://mariadb.org/mariadb_release_signing_key.asc'
```

다음 명령을 사용하여 Repository 설정:

```zsh
sudo sh -c "echo 'deb https://ftp.yz.yamagata-u.ac.jp/pub/dbms/mariadb/repo/10.10/ubuntu jammy main' >>/etc/apt/sources.list"
```

패키지 업데이트:

```zsh
sudo apt update
```

MariaDB 설치:

```zsh
sudo apt install mariadb-server
```

MariaDB 서비스 시작:

```zsh
sudo systemctl start mariadb
```

MariaDB 서비스 자동 시작:

```zsh
sudo systemctl enable mariadb
```

> MariaDB <br/> https://mariadb.org/download/?t=repo-config&d=22.04+%22jammy%22&v=10.10&r_m=yamagata-university

### Install Using Docker (Recommended)

MariaDB Docker Image Pull 하기:

```zsh
docker pull mariadb
```

Image로 Container 생성하기:

```zsh
docker run --detach --name mariadb --publish 3306:3306 --env MARIADB_ROOT_PASSWORD=mariadb mariadb:latest
```

Container bash에 액세스하기:

```zsh
docker exec -it mariadb bash
```

> MariaDB - Docker Hub <br/> https://hub.docker.com/_/mariadb
