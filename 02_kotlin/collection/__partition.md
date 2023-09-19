# Kotlin Collection partition

원래 배열을 목록 쌍으로 분할합니다. 여기서 첫 번째 목록에는 술어가 true 를 산출 한 요소가 포함 되고 두 번째 목록에는 술어가 false 를 산출 한 요소가 포함 됩니다.

=> 배열을 조건의 true, false로 나눈다.

```kt
inline fun <T> Sequence<T>.partition(
    predicate: (T) -> Boolean
): Pair<List<T>, List<T>>

public inline fun <T> Sequence<T>.partition(predicate: (T) -> Boolean): Pair<List<T>, List<T>> {
    val first = ArrayList<T>()
    val second = ArrayList<T>()
    for (element in this) {
        if (predicate(element)) {
            first.add(element)
        } else {
            second.add(element)
        }
    }
    return Pair(first, second)
}
```

```kt
val array = intArrayOf(1, 2, 3, 4, 5)
val (even, odd) = array.partition { it % 2 == 0 }
println(even) // [2, 4]
println(odd) // [1, 3, 5]
```

> intArray에서 짝수와 홀수를 나누는 예제
