## 제너릭
* 클래스나 함수에서 사용 가능한 자료형을 외부에서 지정할 수 있는 기능
  * 슈퍼 클래스를 자료형으로 파라미터를 받을 때 서브클래스를 파라미터로 전달하면 자동으로 캐스팅 연산을 해주어 상속 관계에 있는 모든 클래스들을 파라미터로 전달 할 수 있는데
    * 이때 캐스팅 연산은 프로그램의 성능을 저하시킬 수 있다 

* 이를 해결하기위해 고정작인 자료형을 받는것이 아닌 실질적인 자료형을 받는 ```타입 파라미터```를 받는다
  * ```타입 파라미터```에 특정 자료형이 사용되면 모든 코드는 할당된 자료형으로 대체된다
     >   이를 통해 캐스팅 연산없이 자료형을 그대로 사용할 수 있게 된다 

* ```타입 파라미터```의 이름은 클래스 규칙과 같지만 일반적으로 ```Type```의 이니셜인 ```T```를 사용하는 것이 관례이다
  * 여러개의 제너릭을 사용할 시에는 ```T```의 다음 알파벳인 ```U, V```를 추가적으로 사용한다

* 여기서 특정한 슈퍼 클래스를 상속받은 클래스 타입으로 제한하려면 ```<T: SuperClass>```형식으로 작성하면 된다 

### 제너릭 함수

정해진 타입의 매개변수가 아닌 여러 타입의 매개변수를 받기 위해 Generic Function을 사용할 수 있다. 함수 이름 앞에 타입 매개변수를 위치시킨다
```Kotlin
fun <Int> plusOne(num: T): T {
  // ...
}
```