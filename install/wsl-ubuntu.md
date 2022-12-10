# Install WSL-Ubuntu

### Install WSL-Ubuntu Using WSL Install Command

Windows Terminal을 관리자 권한으로 실행 후 다음 명령을 입력:

```powershell
wsl --install
```

설치 완료 후 컴퓨터를 다시 시작

> Microsoft Docs - WSL 설치 <br/> https://learn.microsoft.com/ko-kr/windows/wsl/install

### Change WSL Path

WSL 종료:

```powershell
wsl --shutdown
```

Ubuntu 내보내기:

```powershell
wsl --export Ubuntu D:\WSL\Backup\Ubuntu.tar
```

Ubuntu 등록 해제:

```powershell
wsl --unregister Ubuntu
```

Ubuntu 원하는 경로로 가져오기:

```powershell
wsl --import Ubuntu D:\WSL\Ubuntu D:\WSL\Backup\Ubuntu.tar
```
