# 투민 홈페이지 수정 시작 가이드

투민 홈페이지를 직접 수정하고 인터넷에 반영하는 방법입니다. 해머텍과 동일한 방식으로 작동합니다.

---

## 📌 기본 원리

홈페이지 파일들은 **GitHub** 저장소에 저장됩니다.
1. 내 컴퓨터에서 파일을 고치고 수정합니다.
2. `publish.bat` 파일을 실행하면 자동으로 변경 사항이 GitHub에 업로드(push)됩니다.
3. 업로드 후 약 1~2분 뒤 홈페이지에 자동으로 반영됩니다.

---

## A. 처음 딱 한 번만 하는 준비

### 1) 프로그램 설치
(이미 해머텍 작업을 위해 설치하셨다면 이 단계는 건너뛰셔도 됩니다.)
* **Git**: [다운로드](https://git-scm.com/download/win)
* **VS Code**: [다운로드](https://code.visualstudio.com)

### 2) GitHub 로그인 (Git Bash 창에서 최초 1회 실행)
```bash
gh auth login
```
화면 안내에 따라 웹 브라우저에서 로그인합니다.

### 3) 투민 저장소 생성 및 연동 (최초 1회)
GitHub에 `twoomin-static` (또는 원하시는 이름) 저장소를 만드신 후, 아래 명령어를 통해 현재 폴더를 Git 저장소로 초기화하고 연결합니다.

```bash
# 1. 현재 폴더로 이동 (Git Bash 또는 PowerShell)
cd "e:/업무/투민 홈페이지/홈페이지 자료/twoomin"

# 2. Git 초기화
"C:/Program Files/Git/cmd/git.exe" init

# 3. GitHub 원격 저장소 연결 (깃허브 주소를 적어주세요)
"C:/Program Files/Git/cmd/git.exe" remote add origin https://github.com/[사용자이름]/[저장소이름].git

# 4. 최초 파일 올리기
"C:/Program Files/Git/cmd/git.exe" add .
"C:/Program Files/Git/cmd/git.exe" commit -m "최초 업로드"
"C:/Program Files/Git/cmd/git.exe" branch -M main
"C:/Program Files/Git/cmd/git.exe" push -u origin main
```

---

## B. 그다음부터 — 홈페이지 고칠 때마다

### 1) 내용 고치기
1. **VS Code**를 열고 → **File** → **Open Folder** → `twoomin` 폴더를 선택합니다.
2. `gemini-code-1782349471149.html` 또는 이미지 파일들을 수정하고 **Ctrl + S**로 저장합니다.

### 2) 인터넷에 올리기 (자동 도구 사용)
* 폴더 안에 있는 **`publish.bat`** 파일을 더블 클릭하여 실행합니다.
* 수정 내용을 입력하고 엔터를 누르면 자동으로 업로드됩니다.

또는 수동으로 Git Bash에서 아래 명령어를 차례로 입력해도 됩니다:
```bash
"C:/Program Files/Git/cmd/git.exe" pull
"C:/Program Files/Git/cmd/git.exe" add .
"C:/Program Files/Git/cmd/git.exe" commit -m "수정함"
"C:/Program Files/Git/cmd/git.exe" push
```

* 업로드 완료 후 약 1분 뒤 반영됩니다.
* 브라우저에서 확인할 때는 **Ctrl + Shift + R** (강력 새로고침)을 눌러주세요.
