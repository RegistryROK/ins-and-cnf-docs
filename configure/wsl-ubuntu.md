# Configure WSL-Ubuntu

### Configure WSL Advenced Settings

- `.wslconfig` - 전역 설정 구성
- `wsl.conf` - 배포당 설정 구성

`%UserProfile%\\.wslconfig`:

```conf
[wsl2]
processors=2
memory=8GB
swap=16GB
swapFile="D:\\WSL\\swap.vhdx"
```

`/etc/wsl.conf`:

```conf
[boot]
command = "/usr/libexec/wsl-systemd"

[user]
default = registry
```

> Microsoft Docs - WSL 고급 설정 구성 <br/> https://learn.microsoft.com/ko-kr/windows/wsl/wsl-config#wslconfig

### Change APT Repository

`/etc/apt/sources.list` 열기:

```bash
sudo nano /etc/apt/sources.list
```

단축키 `Ctrl+\` 입력 후

교체할 문장 검색:

```
archive.ubuntu.com
```

교체될 문장 입력:

```
mirror.kakao.com
```

이후, A를 눌러서 모두 교체.

`security.ubuntu.com`도 동일한 방법으로 `mirror.kakao.com`으로 교체.

`Ctrl+X`를 눌러 저장 후 에디터 종료.

패키지 리스트 업데이트:

```bash
sudo apt update
```

최신화된 패키지 업그레이드:

```bash
sudo apt upgrade
```

### Install & Configure Zsh

Zsh 설치 및 Shell 변경:

```bash
sudo apt install zsh && chsh -s `which zsh`
```

Oh My Zsh 설치:

```bash
curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```

> Oh My Zsh <br/> https://github.com/ohmyzsh/ohmyzsh

`~/.zshrc` 열기:

```bash
sudo nano ~/.zshrc
```

`plugins=(git)`부분 `Ctrl+K`로 삭제 후, 다음을 입력:

```zsh
plugins=(
  zsh-autosuggestions
  zsh-syntax-highlighting
  zsh-better-npm-completion
)
```

`Ctrl+X`를 눌러 저장 후 에디터 종료.

터미널 다시 시작한 후:

```zsh
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions --depth=1

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting --depth=1

git clone https://github.com/lukechilds/zsh-better-npm-completion ~/.oh-my-zsh/custom/plugins/zsh-better-npm-completion --depth=1
```

### Configure Git

Git 정보 입력:

```zsh
git config --global user.name "Hyeonjun Lee"
git config --global user.email "registry.forbusiness@gmail.com"
```

Git 인증 저장

```zsh
git config --global credential.helper store
```
