# ๐GIT

## 0. ๋ค์ด๊ฐ๊ธฐ ์ , ๊ฐ๋จํ ์ค์ต๊ณผ ๊ณต๋ถ๋ฐฉํฅ

### ์ค๋ ์ตํ์ผ ํ  ๋ช๋ น์ด

```bash
$ git clone {git reposiory url} .
$ git add .
$ git commit
$ git push
```

- commit์ version์ ๋ง๋ฆ ex) ๋ฒํผ ์ถ๊ฐ, ๊ธฐ๋ฅ ์ถ๊ฐ
- push๋ ๋ก์ปฌ์ ์๋ ํ์ผ์ Github์ ์ฌ๋ฆฌ๋ ๋์

> ๐ก ํฐ๋ฏธ๋ ๋ถ์ฌ ๋ฃ๊ธฐ ๋จ์ถํค `shift` + `insert`

> ๐ก `git clone {url} .`  ์ ์ ์ฐ์ผ๋ฉด ํ์ฌ ์์นํ ๋๋ ํ ๋ฆฌ๊ฐ git repository๊ฐ ๋๋ค.

> ๐ก **`clone` ๊ณผ `pull` ์ ์ฐจ์ด**<br>
> `clone` : ๋ก์ปฌ ์ ์ฅ์์ ๋ด์ฉ์ด ์๊ฒฉ ์ ์ฅ์์ ๋ด์ฉ๊ณผ ์ผ์น <br>(๋ฆฌ๋ชจํธ ์ค์ ์ ์๋์ผ๋ก ํด์ฃผ๋ ์ด๊ธฐ ๋ค์ด๋ก๋์ ์ฌ์ฉ) <br>
> `pull` : ์๊ฒฉ ์ ์ฅ์์ ๋ด์ฉ์ ๊ฐ์ ธ์์ ํ์ฌ ๋ธ๋์น์ ๋ณํฉ(merge)๊น์ง ํด์ค<br>

<br>

## 1. Git & GitHub ๊ธฐ๋ณธ ๊ฐ๋

### Git๊ณผ GitHub

- git์ ์์ค์ฝ๋์ ๋ณ๊ฒฝ ๋ด์ญ์ ์ ์ฅํ๋ ๋ฒ์  ๊ด๋ฆฌ ๋๊ตฌ
- github์ git์ ์ฝ๊ฒ ์ฐ๊ธฐ ์ํด GUI๋ฅผ ์ง์ํ๋ ์๋น์ค


> ๐ก **Sourcetree** <br>
> CUI์ ๋ณํํด์ ๋ง์ด ์ฌ์ฉํ๋ GUI, ๋ธ๋ฐ์น๋ฅผ ์๊ฐ์ ์ผ๋ก ํ์ธํ  ๋ ์ฌ์ฉ <br>
> [https://www.sourcetreeapp.com/](https://www.sourcetreeapp.com/)


> ๐ก ํ๋ ์์ํฌ๋ ๋ ๊ณ ๋ค. ๋ถํ + ์ค๋ช์, ๊ทธ๋๋ก ์กฐ๋ฆฝ (๋ด ์ฝ๋๋ฅผ ๋ถ๋ฅธ๋ค) <br>
> ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ ๋ด ์ฝ๋๊ฐ ์๊ณ  ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ๊ฐ์ ธ์์ ์ฌ์ฉํ๋ ๊ฒ์ด๋ค. (๋ด ์ฝ๋๊ฐ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ๋ถ๋ฌ์ ์ฌ์ฉ)

</aside>

<br>

## 2. Git

### Git ์ค์นํ๊ธฐ

**git ๋ช๋ น์ด**

```bash
$ git # ๊น ์ค์น ํ์ธ
$ git --version # ๋ฒ์ ํ์ธ
$ git update-git-for-windows # ๊น ๋ฒ์  ์๋ฐ์ดํธ (์๋์ฐ)
$ git config --global user.name "{name}" # ์ฌ์ฉ์ ์ด๋ฆ ์ค์ 
$ git config --global user.email {email} # ์ฌ์ฉ์ ์ด๋ฉ์ผ ์ค์ 
$ git config --list # ์ฌ์ฉ์ ์ ๋ณด ํ์ธ

$ git add . # ํ์ฌ ๋๋ ํ ๋ฆฌ์์ ์๋ฐ์ดํธ๋ ํ์ผ ๋ชจ๋ ์คํ์ด์ง
$ git add -A # ์์ ๋ ํ์ผ์ ๋ชจ๋ ์คํ์ด์ง
$ git diff # ์คํ์ด์ง๋์ง ์์ ๋ณ๊ฒฝ ์ฌํญ ํ์ธ
$ git diff --staged # ์คํ์ด์ง ๋์์ผ๋ ์์ง ์ปค๋ฐ๋์ง ์์ ๋ณ๊ฒฝ ์ฌํญ ํ์ธ
$ git status # ํ์ผ ์ํ ํ์ธ
$ git log # ์ปค๋ฐ ํ์คํ ๋ฆฌ ํ์ธ
```

**๋ฆฌ๋์ค ๋ช๋ น์ด**

```bash
$ mkdir test # test ํด๋ ์์ฑ
$ cd test # test ํด๋๋ก ์ด๋
$ touch file.html # file.html ํ์ผ ์์ฑ
$ ls # ํด๋ ๋ด ํ์ผ๋ณด๊ธฐ

$ vi file.html # vi ์๋ํฐ
shift + i # Insert ๋ชจ๋ ์ง์
ESC # ์์  ํ ESC
:wq! # write quit (๊ฐ์ )

$ rm file.html # file.html ํ์ผ ์ญ์ 
$ cd .. # ์์ ํด๋ ์ด๋
$ rmdir test # test ํด๋ ์ญ์ 
```


>๐ก ์ค๋ฌด์์๋ `vi` ๋์  `vim`์ ์ฌ์ฉํ๋ค.

<br>

**VSC์ ๊ธฐ๋ณธ ํฐ๋ฏธ๋์ Git Bash๋ก ์ค์ ํ๊ธฐ**

1. `Ctrl` + `Shift` + `P`
2. โSelect Defalt Profileโ ๊ฒ์
  <img src="https://user-images.githubusercontent.com/46313348/187867955-6f8aa768-e6f6-4bae-a1bc-7990a896bb26.png" alt=""/>
  
3. Git Bash๋ก ์ค์ 

<br>

### Commit ํด๋ณด๊ธฐ

```bash
$ cd {ํ๋ก์ ํธ ํด๋}
$ git init # ๊น ์ ์ฅ์๋ก ๋ง๋ค๊ธฐ
$ touch README.md

$ git add . # ๋ชจ๋  ํ์ผ ๋ฐ ํด๋ ์คํ์ด์ง
$ git commit -m "first commit"
```
<br>

### ์ ์ฅ์์์ ๋ฌด์ํ  ํ์ผ ์ค์ ํ๊ธฐ

`.gitignore` ํ์ผ์ ๋ฒ์  ๊ด๋ฆฌ์์ ์ ์ธํ  ํ์ผ์ ๋ช์ํ๋ค. ๋ช์๋ ํ์ผ์ git์์ ์ถ์ ์ด ๋์ง ์๊ณ  push๋ฅผ ํด๋ repo์ ์ฌ๋ผ๊ฐ์ง ์๋๋ค.
(`git status` ๋ช๋ น์ด๋ก ํ์ธ ๊ฐ๋ฅ)

๐**.gitignore ์๋ ์์ฑ๊ธฐ**

[https://www.toptal.com/developers/gitignore](https://www.toptal.com/developers/gitignore)

<br>

## 3. GitHub

### ์์ ์ฌ์ดํด

```bash
$ git pull # ํผ์ ์์ ์ ์๋ต ๊ฐ๋ฅ
# ํ์ผ ์์ ์ด๋ ์ถ๊ฐ
$ git add .
$ git commit -m 'message'
$ git push
```


> ๐ก **Fork** ์ ํ์ธ์ ํ๋ก์ ํธ๋ฅผ ๋ด repository๋ก ๋ณต์ ํด์ ๊ฐ์ง๊ณ  ์ฌ ์ ์๋ค.
> <img src="https://user-images.githubusercontent.com/46313348/187869858-474db2fe-e379-4ce0-9c0b-bbd90e90f760.png" alt="" />

<br >

### README.md ์์ฑํ๊ธฐ

```bash
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main # branch๋ฅผ main์ผ๋ก ์์ 
git remote add origin {git url}
git push -u origin master
```

<br>

### ๋งํฌ ์ฐ๊ฒฐํ๊ธฐ

**GitHub ํ์ด์ง ๋ง๋ค๊ธฐ**

Settings - Pages - Branch - Main โ url ์์ฑ ํ์ธ ๊ฐ๋ฅ
<img src="https://user-images.githubusercontent.com/46313348/187867962-6b6b054f-eac6-472a-ad4e-3220dba2ba8f.png" alt="" />

<br>

**๋๋ฉ์ธ ๋ง๋ค๊ณ  ์ฐ๊ฒฐํ๊ธฐ**

1. ์นดํ24
   1) ๋๋ฉ์ธ ๊ตฌ๋งค [https://www.cafe24.com/](https://www.cafe24.com/)
   2) ๋์ ์๋น์ค ๊ด๋ฆฌ - ๋์ DNS ๊ด๋ฆฌ - A๋ ์ฝ๋ ์ถ๊ฐ (๋๋ฉ์ธ์ ์ค ์๋ฒ์ธ GitHub์ IP๋ฅผ ์๋ ค์ค)
   3) ๋์ ์๋น์ค ๊ด๋ฆฌ - ๋ณ์นญ ๊ด๋ฆฌ - CNAME ์ถ๊ฐ - ๋ณ์นญ๊ณผ ์ค์  GitHub Pages ๋๋ฉ์ธ ์๋ ฅ
      <img src="https://user-images.githubusercontent.com/46313348/187867966-c210440d-86f2-4016-9e33-b8f4ccaf034e.png" alt="" />
      >๐ก Github pages ์ IP ์ฃผ์๋ `$ nslookup {GitHub Pages Url}`๋ก ํ์ธ ํ  ์ ์๋ค.
      <br>
2. GitHub <br>
  Custom domain์ ๋ณ์นญ ์๋ ฅ (GitHub์ ๋๋ฉ์ธ์ ๋ณ์นญ์ ์๋ ค์ค)
  <img src="https://user-images.githubusercontent.com/46313348/187867969-70196c9a-c0ac-471f-af08-fbce52a0f99c.png" alt="" />
