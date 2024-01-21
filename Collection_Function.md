# Collection Function

Kotlin에서는 open source로 제공하는 내장 함수들이 존재하는데 이 중에서는 Collection 객체에 접근하여 데이터를 조작 또는 처리할 수 있는 함수들이 있다

또한 이들은 Collection 인터페이스 구현하는 Iterable 인터페이스를 확장하는 확장 함수로 구성되어 있다

이들 중 여러 종류가 있는데 함수 이름의 키워드로 정리 해 보겠다

## filter
이름 그대로 사용자가 정의한 조건을 기반으로 조건에 부합하는 원소만 가져오는 함수이다
filter 함수에도 여러가지 바리에이션이 있다

* filter() : 후행 람다의 boolean 값이 true인 원소들만 반환
* filterNot() : 후행 람다의 boolean 값이 false인 원소들만 반환
* filterIndexed() : 후행 람다에서 Iterable의 원소뿐만 아니라 Index도 활용할 수 있는 filter()와 기능은 동일한 함수
* filterNotNull() : Iterable의 원소 중 null이 아닌 원소만 반환
* filterIsInstance() : 특정 타입의 원소만 반환
* filterTo() : filter() 함수를 거친 원소들을 파라미터로 받은 Iterable에 추가

## map
Iterable에 함수를 거쳐(iterate) 변환된 결과를 반환하는 함수이다

* map() : 후행 람다를 거쳐 변환된 리스트를 반환
* mapIndexed() : map()과 기능은 같으나 Index도 활용 가능한 함수
* mapNotNull() : null이 아닌 원소에 대해서만 후행 람다를 거친 리스트를 반환
* mapTo() : map() 함수를 거친 원소들을 파라미터로 받은 Iterable에 추가


## flat
flat은 평평한, 편평한이라는 의미를 가지고 있으며, Iterable의 원소들을 한곳으로 모아주는 역할을 한다
![flat](image.png)