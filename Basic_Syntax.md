## 코틀린 기본 문법

### 1. 세미콜론

* 기본적으로 세미콜론을 붙이지 않는다

### 2. 변수 선언

* 변수 선언 방법에는 2가지가 있다

    * var : 일반적으로 통용되는 변수, 언제든지 읽기 쓰기가 가능하다
    * val : 선언시에만 초기화가 가능하며, 중간에 값을 변경할 수 없음

* 변수는 선언 위치에 따라 두가지 이름으로 부른다

    * 클래스에 선언된 변수 : Property(속성)
    * 이 외의 Scope 내에 선언된 변수 : Local Variable (지역 변수)

* 고전적인 언어들은 변수 선언 후 초기화되지 않으면 기본 값으로 초기화 되거나 null 값이 할당되지 않았다는 표시로 null 값을 가지게 된다
> Kotlin은 기본 변수에서 null을 허용하지 않으며, 변수에 값을 할당하지 않은 채로 사용하면 문법 에러를 사용하고 컴파일을 막아주므로 의도치 않은 동작이나 NullPointerException을 원천적으로 차단해 준다는 장점이 있다.
    > 그런데 프로그램에 따라서는 null을 허용하는 nullable 변수(변수명 뒤에 ? 붙임으로써 구현 가능)로 선언해 줄 수 있다 하지만 NullPointerException이 발생 할 수 있게 된다

### 3. 자료형

* 자료형은 자바와 거의 동일하다 단, 내부적으로 UTF-16 BE 방식을 사용하므로 글자 하나하나가 2Byte의 메모리 공간을 사용한다

### 4. 형 변환

* Kotlin은 형 변환시 발생할 수 있는 오류를 막기 위해서 다른 언어들이 지원하는 '암시적 형변환'은 지원하지 않는다
    * 명시적 형변환 : 변환될 자료형을 개발자가 직접 지정함
    * 암시적 형변환 : 변수를 할당할 시 자료형을 지정하지 않아도 형변환 됨

### 5. 배열

* 배열은 처음 선언했을 때의 전체 크기를 변경할 수 없다는 단점이 있지만 선언하면 다른 자료구조보다 빠른 입출력이 가능하다는 장점이 있다

### 6. 타입 추론

* 변수나 함수들을 선언할 때나, 연산이 이루어 질때 자료형을 코드에 명시하지 않아도 코틀린이 자동으로 자료형을 추론해주는 기능

### 7. 함수

* 함수 : 특정한 동작을 하거나 원하는 결과값을 연산하는데 사용

```Kotlin
fun main() {
    println(add(5, 6, 7))
}

fun add(a: Int, b: Int, c:Int): Int {
    return a+b+c
    //  리턴 발생 시 함수 중간이더라도 함수 종료
}
```

* 단일 표현식 함수 : 위와 같이 여러가지 일을 하는 것이 아니라 a, b, c를 단순히 더해서 반환하는 역할과 같이 간단한 기능의 경우 마치 변수에 결과값을 할당하듯 기술할 수 있도록 함

```Kotlin
fun main() {
    println(add(5, 6, 7))
}

fun add(a: Int, b: Int, c: Int) = a + b + c
```

* 단일 표현식 함수는 반환형의 타입 추론이 가능하므로 반환형을 생략할 수 있다
> 외부에서 볼 때는 **자료형이 결정된 변수** 라는 개념으로 접근하는 것이 좋다

### 8. 조건문

* if문은 java와 동일, switch문은 when으로 사용

* Any 자료형 : 어떤 자료형이든 상관없이 호환되는 코틀린의 최상위 자료형

```Kotlin
fun main() {
    doWhen(12L)
}

fun dowhen (a:Any) {
    when(a) {
        1-> println("정수 1이다")
        "DiMo" -> println("디모의 코틀린 강좌")	
        is Long -> println("Long 타입이다")
        !is String -> println("String 타입이 아니다")
        else -> println("어떤 조건도 만족하지 않는다")
    }
}
```
> 실행결과 : Long 타입이다

* when의 조건이 맞을 때 값을 반환하는 표현식으로서의 역할을 하게 하려면 동작 대신 값을 써주면 된다

### 9. 반복문

* 기본적으로 for문은 값을 1을 증가시키며 반복한다

```Kotlin
fun main() {
    for(i in 0...9) {
        print(i)
    }
}
```

* 증가값은 step을 이용하여 변경할 수 있다

```Kotlin
fun main() {
    for(i in 0...9 step 3) {
        print(i)
    }
}
```

* 감소값은 downTo를 사용하면 된다

```Kotlin
fun main() {
	for(i in 9 downTo 0){ //1씩 감소하며 반복 
        print(i)
    }
}
```

### 10. 증감연산자

* 전위연산자
  * 변수가 호출되기 이전에 값을 변경시킴

* 후위연산자
  * 변수가 호출된 이후에 값을 변경시킴

* 증가연산자
  > ++을 변수 앞이나 뒤에 붙여 변수의 값을 1 증가시킴

* 감소연산자
  > --를 변수 앞이나 뒤에 붙여 변수의 값을 1 감소시킴