## 중첩 클래스
* 클래스 안에 하나의 클래스가 더 존재하는 것으로써, 클래스끼리 기능이 강하게 연관되어있다는 것을 나타내기 위해 사용하는 것이다
* 보통 ```외부클래스.중첩클래스()```식으로 접근할 수 있다
* 이때 중첩 클래스 대신에 내부 클래스라는 것도 사용이 가능하다
    * 중첩 클래스에 ```inner```키워드를 붙여 만들 수 있다
    * 혼자서 인스턴스화 될 수 없으며 외부클래스의 객체가 있어야지만 생성과 사용이 가능하다

* 중첩 클래스는 서로 다른 클래스로 간주되어 서로 속성과 함수에 접근할 수 없지만, 내부 클래스는 외부 클래스 내부에 존재하는 것이기 때문에 접근이 가능하다  