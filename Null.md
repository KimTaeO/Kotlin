## Null 처리

* null 상태에서 속성이나 함수를 사용하려 하면 NPE가 발생한다 
* Nullable 변수를 컴파일 하려면 널인지 아닌지를 체크를 해야한다
* Null 체크를 위한 편리한 연산자들을 제공하는데 이러한 종류들이 있다
  * ```?.``` null safe operator : 참조 연산자 실행 전에 객체가 null 인지 체크하고 만약 null 이라면 코드를 실행하지 않는다
  * ```?:``` elvis operator : 객체가 null이 아니라면 그대로 실행하지만 null이라면 연산자 우측의 객체로 대체시킴
  * ```!!.``` non-null assertion operator : 참조연산자를 사용할 때 Null 여부를 컴파일 시에 확인하지 않도록 하는 연산  