## 목차

[GIT](#GIT)

[영역](#영역)  

[로컬(local)](#로컬(local))  

[원격 저장소](#원격_저장소)  

[gitignore](#gitignore)

---

### GIT

분산 버전 관리 시스템

코드의 ‘변경 이록’을 기록하고 ‘협업’을 원활하게 하는 도구

hash = commit 의 고유 값 

- 역할
    
    코드의 버전(히스토리)를 관리
    
    개발되어 온 과정 파악
    
    이전 버전과의 변경 사항 비교
    
</br>

### 영역

- **Working Directory (W.D)**
    
    실제 작업 중인 파일들이 위치하는 영역
    
- **Staging Area**
    
    Working Directory에서 변경된 파일 중 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 중간 준비 영역
    
- **Repository**
    
    버전 이력과 파일들이 영구적으로 저장되는 영역
    
    모든 버전과 변경 이력이 기록됨

버전 = **commit** = 변경된 파일들을 저장하는 행위

올리고 싶은 파일들만 올리고 싶을 때(난 멤버 기능만 구현했고 다른 건 개발중인데… → 멤버 기능만 모아서 멤버.ver로 올려야겠다! → 멤버 기능들만 모아 staging area 로 snapshoot 찍기 ( ✌️ 찰칵 )

![영역설명](https://github.com/user-attachments/assets/8ea1d105-4557-46a4-b0a0-e4e66dffdc7f)

</br>

### 동작

- `git` 명령어 사용

- `git config` 로 작성자 정보 설정

        `git config --global user.email “메일주소”`

        `git config --global user.name “유저네임”`
    
    global로 설정 (전역)  → 전역이기 때문에 앞으로 재입력하지 않아도된다

- `git init`

    로컬 저장소 설정(초기화) → git의 버전 관리를 시작할 디렉토리에서 진행

    git의 관리를 받기 시작한 디렉토리 내에서는 `(master)` 가 표시

    *** git 로컬 저장소 내에 또 다른 로컬 저장소를 만들지 말 것 (중첩 git repository 최악이에..)

- `git add`

    변경 사항이 있는 파일을 staging area에 추가

    공백으로 원하는 파일 지칭하여 추가 가능

    `.` 붙이면 모든 변경 사항 한번에 다 올릴 수 있음

- `git commit`

    staging에 있는 파일들을 저장소에 기록

    해당시점의 버전을 생성하고 변경 이록을 남기는 것

- `git log`

    commit 목록 확인, commit history 보기

- `git log --online` commit 목록 한 줄 보기

- `git config --global -l` git global 설정 정보 보기

- `git status`

    로컬 저장소의 파일 상태 확인 ( 커밋할게 있는지 없는지 ), staging area 에 올라가 있는지

- `git commit -m`

    commit 메시지 올리고 commit

</br>
    
### 로컬(local)

현재 사용자가 직접 접속하고 있는 기기 또는 시스템

개인 컴퓨터, 노트북, 태블릿 등 사용자가 직접 조작하는 환경  

</br>
    
### 원격 저장소

코드와 버전 관리 이력을 온라인 상의 특정 위치에 저장하여 여러 개발자가 협업하고 코드를 공유할 수 있는 저장 공간

`git remote` 로 시작

- 로컬 저장소에 원격 저장소 추가
  
    - `git remote add origin remote_repo_url`
    
        origin 자리는 추가하는 원격 저장소 별칭
    
        별칭을 사용해 로컬 저장소 한 개에 여러 원격 저장소를 추가할 수 있음 
    
        `git remote -v`  로 원격저장소 url 잘 들어갔는지 확인 가능
    
    - `git push origin master` 원격 저장소에 commit 업로드
       
        *git 아 push 해줘 origin 이라는 이름의 원격 저장소에 master 라는 이름의 브랜치를*

- 원격 저장소의 변경 사항 받아오기
    
    `git pull origin master` 
    
- 원격 저장소 전체를 복제 (다운로드)
    
    `git clone remote_repo_url`
    

예를 들어보자면 clone 은 새롭게 앱을 다운 받는 느낌이고, pull 은 이미 받아져 있는 앱을 업데이트 하는 느낌이다

</br>
    
### gitignore

프로젝트에 맞는 .gitignore 파일 만들기

🔗 https://www.toptal.com/developers/gitignore/

git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는 데 사용되는 텍스트 파일

프로젝트에 따라 공유하지 않아야 하는 것들도 존재하기 때문

`touch .gittnore` 확장자 적지 않고 만들어야함 파일명 앞에 `.` 입력

 
