# 2장 unittest 모듈을 이용한 기능 테스트 확장

##selenium
우리는 unittest를 할때 selenium을 사용한다.
이것은 brwoser를 띄어서 실제로 유저가 사용하는 스토리를 **code**로 구현하는것이다.

##comment
우리 책의 저자는 comment(주석)을 신뢰하지 않는다.
보다 쉽게 이해되는 코드를 작성하여 주석 없이 코드만으로 전체적인
구조를 확인 할 수 있는것을 선호한다

##unittest module
예시코드
```
from selenium import webdriver
import unittest


class NewVisitorTest(unittest.TestCase):

    def setUp(self):
        self.browser = webdriver.Firefox()

    def tearDown(self):
        self.browser.quit()

    def test_cat_start_a_list_and_retrivev_it_later(self):

        self.browser.get('http://localhost:8000')

        self.assertIn('new church', self.browser.title)
        self.fail('finish the test')

if __name__ == '__main__':
    unittest.main(warnings='ignore')
```

우리는 django.test import TestCase 를 경험했지만 여기선 unittest를 사용한다.
python 에서 제공하는 모듈이다.

[unittest python doc](https://docs.python.org/3/library/unittest.html?highlight=unittest#module-unittest)

django에서 다뤘듯이 `setUp`은 테스트코드가 실행 되기 전 이고
`tearDown`은 테스트코드가 실행 되고 난 이후이다.
setUp에서 browser를 켜는 행위를 하고 tearDown에서 닫는 행위를 하면
firefox가 이리저리 떠다니는것을 막을 수 있다.

위 코드를 실행시켜보면 firefox가 켜지고, 꺼지는것을 확인할 수 있다.


## implicitly_wait

책에서 보면 암묵적 대기 라고 설명된 로직인데
용도는 firefox 브라우져가 완전히 켜질 때 까지 기다리는것이다.
아직 켜지지 않았는데 로직을 테스트한다면 올바른 테스트가 불가능하기 때문이다.




