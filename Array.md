# 배열

* 변수에 여러가지 값을 저장할 수 있는 대표적인 자료형이다

## 기본적인 배열 선언

* 기본적으로 Array앞에 기본 타입들인 Int, Char, Long 등을 붙여서 선언합니다

* 매개변수에는 배열의 갯수가 들어가게 됩니다

```Kotlin
//ex
var array = IntArray(1)
```
> String은 기본 타입이 아니기 때문에 StringArray()는 존재하지 않는다

* 대신 다음과 같이 배열을 선언하면 문자열로 이루어진 배열을 선언하는게 가능합니다
```Kotlin
var StringArray = Array(10, {item->""})
```

* 그리고 ArrayOf()라는 함수를 사용한다면 배열의 선언과 동시에 초기화 가능
```Kotlin
var numArray = arrayOf("one", "two", "three")
```