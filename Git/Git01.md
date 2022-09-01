# 🎁GIT

## 0. 들어가기 전, 간단한 실습과 공부방향

### 오늘 익혀야 할 명령어

```bash
$ git clone {git reposiory url} .
$ git add .
$ git commit
$ git push
```

- commit은 version을 만듦 ex) 버튼 추가, 기능 추가
- push는 로컬에 있는 파일을 Github에 올리는 동작

> 💡 터미널 붙여 넣기 단축키 `shift` + `insert`

> 💡 `git clone {url} .`  점을 찍으면 현재 위치한 디렉토리가 git repository가 된다.

> 💡 **`clone` 과 `pull` 의 차이**<br>
> `clone` : 로컬 저장소의 내용이 원격 저장소의 내용과 일치 <br>(리모트 설정을 자동으로 해주는 초기 다운로드에 사용) <br>
> `pull` : 원격 저장소의 내용을 가져와서 현재 브랜치와 병합(merge)까지 해줌<br>

<br>

## 1. Git & GitHub 기본 개념

### Git과 GitHub

- git은 소스코드의 변경 내역을 저장하는 버전 관리 도구
- github은 git을 쉽게 쓰기 위해 GUI를 지원하는 서비스


> 💡 **Sourcetree** <br>
> CUI와 병행해서 많이 사용하는 GUI, 브런치를 시각적으로 확인할 때 사용 <br>
> [https://www.sourcetreeapp.com/](https://www.sourcetreeapp.com/)


> 💡 프레임워크는 레고다. 부품 + 설명서, 그대로 조립 (내 코드를 부른다) <br>
> 라이브러리는 내 코드가 있고 라이브러리를 가져와서 사용하는 것이다. (내 코드가 라이브러리를 불러서 사용)

</aside>

<br>

## 2. Git

### Git 설치하기

**git 명령어**

```bash
$ git # 깃 설치 확인
$ git --version # 버전확인
$ git update-git-for-windows # 깃 버전 업데이트 (윈도우)
$ git config --global user.name "{name}" # 사용자 이름 설정
$ git config --global user.email {email} # 사용자 이메일 설정
$ git config --list # 사용자 정보 확인

$ git add . # 현재 디렉토리에서 업데이트된 파일 모두 스테이징
$ git add -A # 수정된 파일을 모두 스테이징
$ git diff # 스테이징되지 않은 변경 사항 확인
$ git diff --staged # 스테이징 되었으나 아직 커밋되지 않은 변경 사항 확인
$ git status # 파일 상태 확인
$ git log # 커밋 히스토리 확인
```

**리눅스 명령어**

```bash
$ mkdir test # test 폴더 생성
$ cd test # test 폴더로 이동
$ touch file.html # file.html 파일 생성
$ ls # 폴더 내 파일보기

$ vi file.html # vi 에디터
shift + i # Insert 모드 진입
ESC # 수정 후 ESC
:wq! # write quit (강제)

$ rm file.html # file.html 파일 삭제
$ cd .. # 상위 폴더 이동
$ rmdir test # test 폴더 삭제
```


>💡 실무에서는 `vi` 대신 `vim`을 사용한다.

<br>

**VSC에 기본 터미널을 Git Bash로 설정하기**

1. `Ctrl` + `Shift` + `P`
2. ‘Select Defalt Profile’ 검색
  <img src="https://user-images.githubusercontent.com/46313348/187867955-6f8aa768-e6f6-4bae-a1bc-7990a896bb26.png" alt=""/>
  
3. Git Bash로 설정

<br>

### Commit 해보기

```bash
$ cd {프로젝트 폴더}
$ git init # 깃 저장소로 만들기
$ touch README.md

$ git add . # 모든 파일 및 폴더 스테이징
$ git commit -m "first commit"
```
<br>

### 저장소에서 무시할 파일 설정하기

`.gitignore` 파일에 버전 관리에서 제외할 파일을 명시한다. 명시된 파일은 git에서 추적이 되지 않고 push를 해도 repo에 올라가지 않는다.
(`git status` 명령어로 확인 가능)

🔗**.gitignore 자동 생성기**

[https://www.toptal.com/developers/gitignore](https://www.toptal.com/developers/gitignore)

<br>

## 3. GitHub

### 작업 사이클

```bash
$ git pull # 혼자 작업 시 생략 가능
# 파일 수정이나 추가
$ git add .
$ git commit -m 'message'
$ git push
```


> 💡 **Fork** 시 타인의 프로젝트를 내 repository로 복제해서 가지고 올 수 있다.
> <img src="https://user-images.githubusercontent.com/46313348/187869858-474db2fe-e379-4ce0-9c0b-bbd90e90f760.png" alt="" />

<br >

### README.md 생성하기

```bash
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main # branch를 main으로 수정
git remote add origin {git url}
git push -u origin master
```

<br>

### 링크 연결하기

**GitHub 페이지 만들기**

Settings - Pages - Branch - Main → url 생성 확인 가능
<img src="https://user-images.githubusercontent.com/46313348/187867962-6b6b054f-eac6-472a-ad4e-3220dba2ba8f.png" alt="" />

<br>

**도메인 만들고 연결하기**

1. 카페24
   1) 도메인 구매 [https://www.cafe24.com/](https://www.cafe24.com/)
   2) 나의 서비스 관리 - 나의 DNS 관리 - A레코드 추가 (도메인에 실 서버인 GitHub의 IP를 알려줌)
   3) 나의 서비스 관리 - 별칭 관리 - CNAME 추가 - 별칭과 실제 GitHub Pages 도메인 입력
      <img src="https://user-images.githubusercontent.com/46313348/187867966-c210440d-86f2-4016-9e33-b8f4ccaf034e.png" alt="" />
      >💡 Github pages 의 IP 주소는 `$ nslookup {GitHub Pages Url}`로 확인 할 수 있다.
      <br>
2. GitHub <br>
  Custom domain에 별칭 입력 (GitHub에 도메인의 별칭을 알려줌)
  <img src="https://user-images.githubusercontent.com/46313348/187867969-70196c9a-c0ac-471f-af08-fbce52a0f99c.png" alt="" />
