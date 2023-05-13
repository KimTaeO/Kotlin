## data 클래스와 enum 클래스
* data 클래스는 내부적으로 함수를 구현해준다 
  * 내용의 동일성을 판단하는 ```equals()```
```
    fun main() {
        val people1 = People("홍길동", 17)
        val people2 = People("홍길동", 17)

        println(people1.equals(people2))
    }

    data class People(
    val name: String,
    val age: Long
    )
```

  * 객체의 내용에서 고유한 코드를 생성하는 ```hashcode()```
```
    fun main() {
	    val human1 = Human("홍길동", 17)
        val human2 = Human("홍길동", 18)
    
        println(human1.hashCode())	// 1678651939
        println(human2.hashCode())	// 1678651940
    }

    data class Human(
	    val name: String,
        val age: Long
    )
```
  * 포함된 속성을 보기쉽게 나타내는 ```toString()```
```
    fun main() {
	    val human = Human("홍길동", 17)
	    val animal = Animal("초코", 3)
    
        println(human)  // Human(name=홍길동, age=17)
        println(animal) // Animal@12edcd21
    }

    data class Human(
	    val name: String,
        val age: Long
    )

    class Animal(
	    val name: String,
        val age: Long
    )
```
  * 객체를 복사하여 똑같은 내용의 새 객체를 만드는 ```copy()```
```
    fun main() {
	    val human = Human("홍길동", 17)
    
        println(human.copy())   //Human(name=홍길동, age=17)
        println(human.copy(name = "강해린"))   // Human(name=강해린, age=17)
    }

    data class Human(
	    val name: String,
        val age: Long
    )
```

  * 속성을 순서대로 반환하는 ```componentX()```
    * 객체의 내용을 원하는대로 꺼내 사용하기 위해 내부적으로 사용됨
```
    fun main() {
	    val human = Human("홍길동", 17)
        val (a, b) = human  // 내부적으로 component1(), component2() 함수가 사용됨
        println("${a}, ${b}")   // 홍길동, 17
    }

    data class Human(
	    val name: String,
        val age: Long
    )
```

* enum 클래스