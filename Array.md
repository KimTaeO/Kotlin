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

## 배열 사용

* 배열에 값 입력하기 
```Kotlin
// 배열의 값을 변경하는 방법에는 두 가지 방법이 존재한다
// 1
배열명[인덱스] = 값
// 2
배열명.set(인덱스, 값)
```

* 배열에 있는 값을 꺼내올 때도 인덱스로 접근하여 가져오거나 set 대신 get을 사용하여 값에 접근할 수 있다

## Collection

* 컬렉션은 배열과 같이 여러 개의 자료를 저장하는 자료형이다
* 배열과 다른 점은 크기가 고정되지 않는 동적 배열이라는 점이다
> ❗️ 컬렉션으로는 List, Map, Set등이 있고, 코틀린에서 동적으로 배열을 사용하기 위해서는 ```Mutable```이라는 접두어를 붙여야 한다

### List
* List는 저장된 인수에 인덱스를 부여한 컬렉션이며, 중복된 값을 저장할 수 있다

```Kotlin
// 리스트 생성
var mutableList = MutableListOf("one", "two")

// 리스트에 값 추가
mutableList.add(3, "three") // 인덱스 3에 값 추가
mutableList.add("four") // 리스트 맨 뒤에 값 추가

// 리스트에 저장된 값 사용
var sample = mutableList.get(0)

// 리스트에 저장된 값 수정
mutableList.set(1, "first")

// 리스트에 저장된 값 제거
// 리스트에서 값을 삭제하면 빈공간을 메꾸기 위해 값이 당겨집니다
mutableList.removeAt(1)
```

* 빈 리스트 사용하기
> 리스트를 선언할 때 저장되는 데이터의 타입을 알기 위해 제네릭에 데이터 타입을 알려준다
```Kotlin
var emptyList = MutableListOf<String>()
```

* ```size```프로퍼티를 사용하여 리스트의 길이를 구할 수 있습니다

### Set
* Set은 인덱스가 존재하지 않으며, 중복을 허용하지 않습니다 그리고 또한 순서도 없습니다
```Kotlin
// Set 생성
var set1 = mutableSetOf("A", "B")
var set2 = mutableSetOf<Type>()

// Set에 값 추가
set1.add("C")

// Set에 저장된 값 사용
println(set1) // ABC

// Set에 저장된 값 삭제
set1.remove("B")
```

### Map
* Map은 Key/Value쌍으로 저장되는 Collection입니다 Key는 Value를 조회하는데  사용됩니다 Key는 중복될 수 없지만, Value는 중복될 수 있습니다

```Kotlin
// Map 생성
var map1 = mutableMapOf<KeyType, ValueType>()
var map2 = mutableMapOf(Pair(Key, Value))
var map3 = mutableMapOf(Key to Value)

// Map에 값 추가 및 수정
map.put(Key, Value) // Key에 해당하는 Value가 있다면 Value가 수정되고, 없다면, 새로운 Key/Value값이 생성됩니다

// Map에 저장된 값 삭제
map.remove(Key)
```

> 코틀린의 기본적인 Collection들은 Immutable로 구현되어 있기 때문에 Immutable Collection에 저장된 값을 추가, 수정, 삭제 등을 할 수 없습니다. 그러므로 ```mutable```접두어를 붙인 Mutable Collection을 사용하여 추가, 수정, 삭제 등의 작업을 수행해야 합니다