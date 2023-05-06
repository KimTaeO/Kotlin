## Argument

* 클래스의 함수 파라미터를 전달하지 않았을 때의 ```Default Argument```를 설정하여 파라미터가 없으면 기본값으로 대체되도록 할 수 있다
* ```Default Argument```가 2개 이상이고, 그중 몇개의 ```Default Argument```만 사용하고 싶다면 ```Named Arguments```를 사용하여 해결할 수 있다
  * ```Named Arguments```는 파라미터의 이름을 사용하여 직접 파라미터에 값을 할당하는 것이다 
    ```Kotlin
    class User(
        val name: String = "익명",
        val age: Long = 0,
        val gender: Gender = Gender.NONBINARY
    )
    
    enum class Gender {
        MALE, FEMALE, NONBINARY
    }
    
        fun main() {
            val user = User(
                name = "홍길동",
                age = 17
            )
    // 이와 같은 형식으로 User 인스턴스를 만든다면
    // Gender에는 Default Value인 Gender.NONBINARY가 들어가게 된다
        }
    ```
    
* ```vararg```는 한 타입의 파라미터에 대해 개수가 정해지지 않은 파라미터이다 
  * 다른 파라미터와 함께 사용할 때는 맨 마지막으로 작성해주어야 한

* ```infix function```은 마치 연산자처럼 사용이 가능하며
* 함수를 정의할 때 infix 예약어를 앞에 붙이고, 함수 이름에 ```infix```함수가 적용될 자료형 이름으로 적용한다