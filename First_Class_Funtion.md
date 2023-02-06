## First Class Funtion(일급함수)
* 일급함수의 특징
    * 변수나 데이터를 할당 가능해야 한다(variable)
    ```Kotlin
    fun main() {
        val hello : () -> {"Hello World!"}

        println(hello())
    }
    ```
    * 함수를 객체의 인자로 넘길 수 있어야 한다(parameter)
    ```Kotlin
        fun printlnFunc(func: () -> String) {
        println("${func()}")
    }

    fun main() {
        val hello: () -> String = { "Hello world!" }

        printlnFunc(hello)
    }
    ```
    * 함수를 객체의 리턴 값으로 리턴할 수 있어야 한다(return value)
    ```Kotlin
        fun getFunc(): () -> String {
        return { "Hello world!" }
    }

    fun main() {
        val returned: () -> String = getFunc()

        println("${returned()}")
    }
    ```
