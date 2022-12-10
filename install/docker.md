# Install Docker Engine (CLI)

> Install Docker Engine <br/> https://docs.docker.com/engine/install/ubuntu/

### Before Install

Older Versions 삭제:

```zsh
sudo apt purge docker docker-engine docker.io containerd runc
```

### Set up Repository

패키지 업데이트:

```zsh
sudo apt update
```

의존성 패키지 설치:

```zsh
sudo apt install ca-certificates curl gnupg lsb-release
```

Docker Official GPG Key 추가:

```zsh
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

다음 명령을 사용하여 Repository 설정:

```zsh
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Install Docker Engine

패키지 업데이트:

```zsh
sudo apt update
```

Docker Engine, Docker CLI, Docker-Compose Plugin 설치:

```zsh
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

(Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock 에러 발생 시):

```zsh
sudo chmod 666 /var/run/docker.sock
```
