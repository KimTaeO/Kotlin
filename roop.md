# 반복문

## for 반복문
```Kotlin
// 일반적인 for 반복문 형태
for(변수 in 시작값..종료값) {// 시작값부터 종료값까지 숫자를 중가시키며 반복합니다
}

// 종료값을 제외하고 반복하는 형태
for(변수 in 시작값 until 종료값) {
}

// step 예약어를 사용하여 변수의 증가값을 조절할 수 있습니다
for(변수 in 시작값..종료값 step 증가폭) {
}

// 값을 감소시키는 for 반복문
for(변수 in 시작값 downTo 종료값) {
}

// 배열이나 컬렉션의 원소들을 반복시키는 for문
for(변수 in 배열 또는 컬렉션) {
}
```