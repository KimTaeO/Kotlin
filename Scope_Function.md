## 스코프(범위) 함수
* 함수형 언어의 특징을 좀 더 편리하게 사용할 수 있도록 기본적으로 제공하는 함수이다
* 클래스에서 생성한 인스턴스를 스코프 함수에 전달하 인스턴스의 속성이나 함수를 더 깔끔하게 호출하여 사용할 수 있다

## 스코프 함수의 종류
* 스코프 함수의 종류로는 ```apply```, ```run```, ```with```, ```also```, ```let```이 존재한다
  * apply는 변수의 선언 시에 스코프 안에서 참조 연산자 없이 인스턴스를 조작할 수 있는 함수이고, 함수가 끝나고는 조작된 인스턴스를 반환해준다
  * run은 스코프 안에서 참조 연산자 없이 사용이 가능하고, 인스턴스를 조작할 수 있는점은 apply와 같으나, 스코프 내에서의 마지막 줄의 결과값을 반환하는 것에서 차이가 있다
  * with은 run과 동일한 기능을 가지지만, 인스턴스를 참조연산자 대신 파라미터로 받는다는 점에서 차이점이 생긴다
  * also는 apply와 동일한 역할을 하나 자기 자신을 가리키는 ```it```을 사용하여 인스턴스를 참조한다
  * let은 run과 동일한 역할을 하나 자기 자신을 가리키는 ```it```을 사용하여 인스턴스를 참조한다 추가적으로 객체가 null이 아닌 경우에만 실행이 되는 부가 기능도 가지고 있다
  > it을 사용하는 이유는 스코프 밖의 것들과 이름이 중복되는것을 피하기 위해서이다 