#기능 테스트를 이용한 Django 설치

> _"테스트를 작성 후 실행한다.그리고 테스트가 예상대로 실패하는지 확인한다"_

우선 테스트를 위해 장고를 설치하며 시작 줄 알았다. 하지만 TDD는 그것마저
테스트를 우선으로 행한다.


```{.python}
# functional_tests.py

from selenium import webdriver

browser = webdriver.Firefox()
browser.get('http://localhost:8000')

assert 'Django' in brower.title
```
첫번째 테스트이다. 현재 우리가 행하는 것은 **기능 테스트**(Functional Test)이다.
개발관점의 단위 테스트(Unit Test)와는 다르다. 

그리고 테스트는 당연히 실패한다. 우리는 장고 프로젝트를 시작하지도 않았다.
하지만 이 실패가 TDD의 시작이다.

```
$ django-admin startproject superlists
```
이제 우리의 장고 프로젝트가 시작됐다.(pyenv로 파이썬 3.5.1 버전이라는 가정하에 진행한다.) 
```
$ python superlists/manage.py runserver
```
이렇게 서버를 실행하고 다시 functional_tests.py를 실행한다.
It worked!라는 제목이 우릴 반기고, 타이틀에 'Welcome to Django' 가 보인다.
우리의 첫번째 테스트를 통과했다.

---

###Git 리포지토리 실행

너무나 당연히, 프로젝트를 시작하면 VCS(git)를 사용한다.
```
$ git init
```
이후 db.sqlite3, pyc, Ds_store(맥의 경우), swp이나 swo(리눅스 계열) 등을 .gitignore에 추가한다.
혹은 Github에서 새로운 repo를 파서 clone을 받아도 된다. 이때 자동으로 .gitignore를 생성해 주도록하면
어느정도 백업파일을 걸러준다. db.sqlite3는 장고에서 프로젝트 초기나 개발용으로 간편하게 사용할 수 있는 db파일이다.
버전관리가 필요없기 때문에 꼭 넣어준다.

`$ git status`로 스테이징할 파일들을 잘 보고 `$ git add`로 스테이징한다. `$ git commit -v`로 커밋 메시지를 남긴다.

[Git Alias](https://git-scm.com/book/tr/v2/Git-Basics-Git-Aliases) : git 명령어를 줄일 수 있는 단축 설정이다.
