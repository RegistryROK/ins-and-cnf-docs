# Install OpenJDK-11

Openjdk-11 설치하기:

```zsh
sudo apt install openjdk-11-jdk
```

`~/.zshrc` 열기:

```zsh
sudo nano ~/.zshrc
```

최하단에 환경변수 추가:

```zsh
# Java
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export PATH="$PATH:$JAVA_HOME/bin"
```

Zsh 스크립트 실행하기:

```zsh
source ~/.zshrc
```

환경변수 확인:

```zsh
echo $JAVA_HOME
```
