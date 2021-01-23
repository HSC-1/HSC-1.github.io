---
layout: post
title:  "0.환경설정"
date:   2021-01-22
excerpt: "ubuntu OS, 가상환경,Github"
tag:
- markdown 
- syntax
- sample
- test
- jekyll
comments: true
---

# 0.환경설정
## 1.ubuntu  
우분투라는 OS를 처음 들어봤다 첫 날 노트북 수령하러 갈 때 직접 설치해야하나 싶었지만 이미 설치되어 문제가 없었다.하지만 윈도우랑 다른 문제가있다.
 - 소리가 안난다.  
 control + alt + t 를 누르면 터미널이 켜지고 alsamixer를 치면 소리설정이 보인다 느낌대로 어느 한곳이 0으로 되어있어서 소리가 안난 것이니 올리면 해결.
 - 한글입력이 안된다.  
 글로만 보면 이해가 힘들지만 아직 그림붙이는걸 모르겠어서 추가 수정할 예정이지만 글로나마 짧게 말하면 설정에 들어가 왼쪽에 지역과 언어가 있다(영어로)  언어팩을 다운받아야한다.  
 진짜 처음 노트북 수령하거나 포멧해서 처음 켰으면  소프웨어 업데이트를 할 것, 설치된 언어 관리를 누르면 뭐 설치하겠냐고 묻는데 설치하면 현재 지역에 맞게 언어와 영어가 설치 될것이다. 다시 설정화면에서 +를 누르면 한글이 3개가 보일 텐데 ()에 Hangul이 있는 걸 선택하면 된다.  
  **참고로 한/영 전환은 shift + space 다 설정으로 바꿀 수 있다**

## 2. 가상환경  
이해한 내용을 바탕으로 기재하면 버전관리등 관리 이점이 있고 문제 발생시 그냥 새로운 가상환경을 만들어 쉽게 해결하기에 필요한것 같다. anaconda로 가상환경을 구축했다.  
[아나콘다 설치 링크](https://www.anaconda.com/products/individual) 또는 터미널에서 저것을 입력하면 설치할 수 있다.  
- 아나콘다 설치  
``` 
$ wget https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh
$ bash Anaconda3-2020.02-Linux-x86_64.sh
```
이제 터미널에 다시 켜서 (base)가 뜬다면 설치가 제대로 된것이다.
 - 가상환경 생성  
  test를 자기가 만들고 싶은 이름으로 바꾸면 된다. 뒤에 파이썬은 자기가 사용할 버전을 입력하면된다.
```terminal
$ conda -n test python=3.7
```
- 가상환경 활성화 
```
$ conda activate test  
```
이제 내가 배우면서 쓰는 패키지들을 다운받는데 
```
$ conda install anaconda notebook
$ conda install matplotlib
$ conda install tensorflow-gpu
$ conda install pandas
$ conda install seaborn
$ conda install cmake 
```
## 3.GitHub,Git
- **Git : 개발하며 작성한 소스코드 버젼 관리용이**
- **GitHub : Git을 관리하며 여러사람과 협력용이**   

### **우분투 환경에서 git 설치**  

    $ apt-get install git

### **계정 연결하기**
큰따운표 안에 있는 것을 자기 것으로 쓰면됩니다.

    $ git config --global user.email "test@email.com"
    $ git config --global user.name "test"

만약 Git에 등록된 정보를 보고 싶으면   

    $ git config -l

### **디렉토리 관리**
작업하는 디렉토리에 `$ git init` 을 하면 .git 이 생성된다.

    $ echo "아무내용" >> readme.md

위의 코드를 하면 readme.md파일생성과 함께 아무내용이라는 내용이 들어간다.


    $ git status 

위의 코드를 사용하면 변화를 알 수 있다.  

---
아래의 코드를 쓰면 `readme.md` 파일을 잠시 올린다. `readme.md` 대신 --all를 쓴다면 변화된 모든 것이 올라간다.

    $ git add readme.md 

이제 아래의 코드로 큰 따옴표 안에 설명을 넣으면 된다.

    $ git commit -m "설명"

이제 내 로컬에 있는 저장소를 원격 저장소와 연결해야하는데 깃허브에 있는 저장소가 없다면 만들어주고 있으면 주소를 `origin` 뒤에다가 붙여주면 된다. 저 `origin`은 원격 저장소의 닉네임 느낌으로 생각하면 된다.

    $ git remote add origin 주소

이제 원격저장소로 아래코드를 사용해서 올리면 된다.

    $ git push origin master  

branch가 없으면 그냥 git push만 해도 올라 갈것이다.~~정확히 모름 항상 `origin master`를 까먹어서 `git push` 만했음~~

만약 다른 컴퓨터에서 `github`에 올라온 것을 다시 내려받을려면 아래 코드를 사용하면 된다.

    $ git clone 원격저장소주소
---

### 참고 링크
