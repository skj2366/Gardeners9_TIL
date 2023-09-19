# Kotlin Collection \ reduce() and fold()

accumulate function

## reduce()

순서가 있는 데이터 (Iterator 등)의 각 데이터를 재귀적으로 연산을 수행하여 리턴하는 함수.
초기값의 지정 없이 첫번째 요소(element)로 시작하며, 반환 데이터 타입은 첫번쨰 요소의 데이터 타입으로 반환.

```kt
inline fun <S, T : S> Array<out T>.reduce(
    operation: (acc: S, T) -> S
): S
```

> 공식문서의 reduce(), 즉 누산기이다.

**operation- 현재 누산기 값과 요소를 가져와 다음 누산기 값을 계산하는 함수**

```kt
val stringList: List<String> = listOf("ba", "na", "na")
val res: String = stringList.reduce { acc, s -> acc + s }
println(res)
// "banana"
```

```kt
val numberList: List<Int> = listOf(1, 2, 3, 4, 5)
val res: Int = numberList.reduce { acc, s -> acc + s }
println(res)
// 15
```

## fold()

reduce()와 같이 순서가 있는 데이터를 재귀적으로 연산하여 수행한 값을 리턴하는 함수이지만,
초기값을 지정할 수 있다.
컬렉션이 비어 있으면 지정된 초기 값을 반환한다.

```kt
inline fun <T, R> Array<out T>.fold(
    initial: R,
    operation: (acc: R, T) -> R
): R
```

> 공식문서의 fold()

```kt
val stringList: List<String> = listOf("ba", "na", "na")
val res: String = stringList.fold("this is ") { acc, s -> acc + s }
println(res)
// "this is banana"
```

```kt
val numberList: List<Int> = listOf(1, 2, 3, 4, 5)
val res: Int = numberList.fold(500) { acc, s -> acc + s }
println(res)
// 515
```

list가 비어있으면 reduce는 에러 (UnsupportedOperationException) 발생
fold는 정상 출력 됨
