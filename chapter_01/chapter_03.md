# TDD_Study

1부 3장 자료
---------------------------------------------------------------------------
###단위 테스트를 이용한 간단한 홈페이지 테스트

시작하기에 앞서
```
django-admin startproject superlists
```
명령어를 통해 프로젝트를 생성한 후

```
python manage.py startapp lists
```
명령어를 통해 lists라는 어플리케이션을 생성합니다.

---------------------------------------------------------------------------
###기능 테스트와 단위 테스트의 차이
- 기능 테스트(Function Test)
  - 사용자 관점에서 애플리케이션의 외부를 테스트하는 것
  - 올바른 기능성을 갖춘 어플리케이션이 만들어지는데 도움을 줌
- 단위 테스트(Unit Test)
  - 개발자 관점에서 애플리케이션의 외부를 테스트하는 것
  - 어플리케이션을 만드는동안 생기는 버그를 잡는데 도움을 줌

####TDD 접근법
 1. 기능 테스트(FT)를 먼저 작성
 1. 기능 테스트(FT)가 실패한다면 단위 테스트(UT)를 통해 코드 동작의 여부를 확인
 1. 단위 테스트(UT)가 실패한다면 테스트를 통과하도록 코드를 수정(여기서 통화 할때까지 2,3을 반복)
 1. 기능 테스트(FT)를 실행

---------------------------------------------------------------------------
###Django에서의 단위 테스트
Django에서는 'unittest.TestCase'의 확장 버전인 특수한 'TestCase'를 사용합니다.
(이는 테스트가 원활이 진행되도록 Django에 최적화된 버전을 말합니다.)

TestCase를 사용하기 위해서는
```
from django.test import TestCase
```
입력을 통해 TestCase를 import 해준 후 상속받아서 사용해야 합니다.

----------------------------------------------------------------------------
####Traceback을 읽고 에러해결 하기
예제

```
ERROR: test_root_url_resolves_to_home_page_view(lists.tests.HomePageTest)
--------------------------------------------------------------------------
Traceback (most recent call last):
    File "/workspace/.../test.py", line 8, in
test_root_url_resolves_to_home_page_view
    found = resolve('/')
  File "/usr/local/lib/.../urlresolver.py",
line 485, in resolve
    return get_resolver(urlconf).reslove(path)
  File "/usr/local/lib/.../urlresolver.py",
line 353, in resolve
    raise Reslover404({'tried':tried, 'path':new_path})
django.core.urlresolvers.Resolver404: {'tried':[[<RegexURLResolver
<RegexURLPattern list> (admin:admin) ^admin/>]], 'path':''}
--------------------------------------------------------------------------
[...]
```

1. 가장먼저 보아야할 ERROR는 어떤 테스트가 실패했는지 알려주는 역할을 합니다.
(예제에서는 test_root_url_resolves_to_home_page_view 테스트에 에러가 있습니다.)
1. 해당 테스트의 어떤 부분에서 에러가 발생하는 지를 찾습니다.
(예제에서는 line 8의 found = resolve('/')부분에 에러가 있습니다.

-----------------------------------------------------------------------------
###단위 테스트의 코드 주기
1. 단위 테스트가 어떻게 실패하는지 확인(Traceback)
1. 실패한 테스트를 수정하기 위한 최소한의 코드를 변경
