# Markdown__
# Markdown 이란?
일반 텍스트 문서의 양식을 편집하는 `문법`이다.
특수기호와 문자를 이용한 간단한 구조의 문법을 사용한다.

# GitHub 이란?
`git`은 여러명의 개발자가 특정 프로젝트를 자신의 컴퓨터로 협업하여 개발하면서 버전을 관리할 수 있는 시스템이다.
`git`은 소프트웨어 이므로 https://git-scm.com/downloads 를 통해 다운받아야 한다.
`GitHub`은 git을 이용한 프로젝트를 지원하는 웹 호스팅 서비스이다.
많은 개발자들이 GitHub 을 통해 오픈소스를 관리하고 있다.

## 1. 마크다운 문법
### 1.1 header
```python

# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
```

# This is a H1  (문서 제목)
## This is a H2 (문서 부제목)
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6

### 1.2 목록(1., 2., 3. ,* , + ,- 사용)   
```python
1. 빨강
2. 주황
3. 노랑
*  초록
+  파랑
-  보라
*  분홍
    - 검정
        + 하늘
            +초록
```

1. 첫번째
2. 두번째
3. 세번째
+  파랑
-  보라
*  분홍
    - 검정
        + 하늘
            + 초록
### 1.3. 코드

#### 1.3.1 코드블럭 사용 (```)
```
    ```
        적고싶은 내용을 적어준다
    ```
```
### 1.4 수평선

```
* * *
***
*****
---
-----------------------------

```

* * *
***
*****
---
-----------------------------

### 1.5 이미지
```
![해바라기](http://www.pask.net/b_pask/data/file/exhibition/3555251663_drlesiuV_15514343408505B15D.jpg)

```
![해바라기](http://www.pask.net/b_pask/data/file/exhibition/3555251663_drlesiuV_15514343408505B15D.jpg)

##2. git 사용하기

## 2.1 git 기초
 ![깃](https://s3-ap-northeast-2.amazonaws.com/opentutorials-user-file/module/3963/10395.png)
 - local: 우리가 사용하고 있는 컴퓨터
 - remote: 원격 저장소
 - repo: repository의 준말, 저장소
 
 ######`working directory`
 우리가 지금 사용하고 있는 컴퓨터에 있는 작업 디렉토리를 말합니다. 
 ######`staging area`
 git 은 파일이 추가되고, 삭제되고, 수정되는 등 변경사항을 전부 파악할 수 있습니다.
 
 그리고 local repo에 저장할 변경사항이 있는 파일들을 설정할 수 있고, 그 햣
 파일들이 staging area에 임시적으로 저장됩니다.
 ###### `local repo`
 local repo는 전 단계인 staging area의 파일들을 최종적으로 우리 컴퓨터에 저장하는 저장소입니다.

local repo는 다음 단계인 remote repo에 저장하기 전 단계입니다.
######`remote repo`
원격 저장소라는 의미이고, GitHub 저장소가 될 것입니다.

## 2.2 git 기초 명령어
+ README.md 파일은 무슨 파일일까요?
우리가 만든 프로젝트에 대한 설명 및 실행방법 등을 적어놓은 파일이라고 생각하시면 됩니다.
 확장자가 md 인데 이것은 markdown 문법을 사용한다는 의미입니다.
### 2.2.1 git clone
원격 저장소의 저장소를 그대로  복사해 가져와서 이용할 수 있다.
```
git clone https://github.com/hyo-hyun/markdown.git
```
### 2.2.2 git init
저장소를 초기화 하는 명령어 입니다.
명령어를 실행하게 되면 `Initialized empty Git repository in 폴더경로/.git/` 이라는 문장이 나온다.
git repository 가 초기화 되었다는 말이다. 이때 '.git' 폴더는 숨김 처리가 되어 있다.

' .git ' 폴더의 용도는 현재 git repository를 생성한 폴더와 관련된 관리 정보가 저장되는 폴더라고 할 수 있습니다.
즉, 파일의 변경(추가,삭제,수정 등)의 이벤트가 발생될 때 변경된 내역들을 하나하나 저장해놓는 폴더라고 할 수 있습니다.
### 2.2.3 git status 
현재 저장소의 상태를 확인하는 명령어 이다.
이 명령어를 최초에 실행하게 되면,
````
$ git status
#On branch master
#
#Initial commit
#
nothing to commit(create/copy files and use "git add" to track)

````

위와 같은 문구들이 생성됩니다.
아직 폴더 내에 아무런 파일 변화가 없다는 것을 말해주고 있습니다.

### 2.2.4 git commit
staging area 에서 local repo로 최종적으로 저장하는 명령어 이다.

### 2.2.5 git log
commit 내역을 확인하는 명령어 이다.
Initial commit 은 우리가 처음에 README.md 파일을 만들 때 자동으로 commit 되어 생성된 것 입니다.

### 2.2.6 git remote
local repo에 commit 이 되었으므로, remote repo에 저장해야 한다.

원격 저장소를 확인하기 위해 `git remote -v ` 명령어를 입력하여 아무것도 나오지 않는다면
 
 원격 저장소로 아무것도 연결되어 있지 않다는 것을 알 수 있습니다.
*****
원격 저장소와 등록을 해보자. 
````
$ git remote add origin https://github.com/hyo-hyun/markdown.git
````
를 입력한 후 `git remote -v` 를 입력하면
````
$ git remote -v
origin https://github.com/hyo-hyun/markdown.git (fetch)
origin https://github.com/hyo-hyun/markdown.git (push) 
````
가 나오게 되면 연결 된 것을 알 수 있습니다.

여기서 `origin` 은 원격 저장소의 별명입니다.

### 2.2.7 git push
원격 저장소로 저장해주는 명령어
`git push -u origin master` 를 입력한다.
```
$ git push -u origin master

error: src refspec master does not match any.
error: failed to push some refs to 'URL'
```
에러메시지가 발생하였다.

이는 repository에 commits 한 내용이 없기 때문에 발생한 에러이다.


따라서 repository에 처음 commits 할 내용을 만들면 문제를 해결 할 수 있다.
```
touch initial

git add initial

git commit -m "initial commit"

git push -u origin master
```