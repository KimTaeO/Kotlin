# Extension functions(확장 함수)
코틀린은 클래스에 상속하거나 디자인 패턴을 사용하지 않고 새로운 기능으로 클래스를 확장할 수 있는 기능을 제공한다.
확장(extension)선언을 통해 이루어지며, 외부 라이브러리를 가져다 사용할 때에는 함수를 추가하거나 변경하기가 어려운데 확장함수를 통해 새로운 기능들을 추가할 수 있다

클래스 외부에서 정의되지만 해당 클래스의 멤버 함수인 것처럼 사용할 수 있는 함수이다

* ```Receiver Type```: 확장 대상이 될 클래스
* ```Receiver Object```: 확장 함수의 내부 구현 시 ```this```키워드를 사용하여 ```Receiver Type```이 가지고 있는 ```public``` 인스턴스에 접근하는 객체

* 확장함수를 만들기 위해서는 ```Receiver Type```에 ```.```을 붙여 새로운 함수를 만들 수 있다

* 메모리 주소값 저장 작업이 컴파일 시에 이루어지는 정적 바인딩이 이루어짐(이후의 값이 변경 X)

## 코틀린 확장 함수를 자바에서 호출하기

확장 함수는 top-level함수로 취급되는데 top-level함수는 자바에서 static 키워드로 번역된다 따라서 확장 함수는```Receiver Type```의 private 멤버에 접근할 수 없다

확장 함수가 컴파일되어 static 함수가 될 때에는 ```Receiver Type```이 메서드의 첫번째 파라미터로 추가되기 때문에 다음과 같은 코틀린의 확장함수는 다음과 같은 자바 메서드로 해석된다


Kotlin
```Kotlin
fun Int.plusOne(): Int {
    return this + 1
}
```


Java
```Java
public static Int plusOne(Int int) {
    return int + 1
}
```