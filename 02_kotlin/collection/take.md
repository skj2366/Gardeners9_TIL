# take()

```kt
fun <T> Array<out T>.take(n: Int): List<T>

public fun <T> Array<out T>.take(n: Int): List<T> {
    require(n >= 0) { "Requested element count $n is less than zero." }
    if (n == 0) return emptyList()
    if (n >= size) return toList()
    if (n == 1) return listOf(this[0])
    var count = 0
    val list = ArrayList<T>(n)
    for (item in this) {
        list.add(item)
        if (++count == n)
            break
    }
    return list
}
```

Collection의 앞에서 부터 n 만큼 취해서 List로 반환


```kt
(0..10).toList().take(5)
// [0, 1, 2, 3, 4]
```

# takeLast()
```kt
fun <T> Array<out T>.takeLast(n: Int): List<T> 

public fun <T> Array<out T>.takeLast(n: Int): List<T> {
    require(n >= 0) { "Requested element count $n is less than zero." }
    if (n == 0) return emptyList()
    val size = size
    if (n >= size) return toList()
    if (n == 1) return listOf(this[size - 1])
    val list = ArrayList<T>(n)
    for (index in size - n until size)
        list.add(this[index])
    return list
}
```

Collection의 뒤에서부터 n만큼 취해서 List로 반환

```kt
(0..10).toList().takeList(5)
// [10, 9, 8, 7, 6]
```

# takeWhile()
```kt
inline fun <T> Array<out T>.takeWhile(
    predicate: (T) -> Boolean
): List<T>

public inline fun <T> Array<out T>.takeWhile(predicate: (T) -> Boolean): List<T> {
    val list = ArrayList<T>()
    for (item in this) {
        if (!predicate(item))
            break
        list.add(item)
    }
    return list
}
```
조건식을 만족하는 값들의 리스트를 반환


```kt
val chars = ('a'..'z').toList()
println(chars.take(3)) // [a, b, c]
println(chars.takeWhile { it < 'f' }) // [a, b, c, d, e]
println(chars.takeLast(2)) // [y, z]
println(chars.takeLastWhile { it > 'w' }) // [x, y, z]
```

# takeLastWhile()

```kt
public inline fun <T> Array<out T>.takeLastWhile(predicate: (T) -> Boolean): List<T> {
    for (index in lastIndex downTo 0) {
        if (!predicate(this[index])) {
            return drop(index + 1)
        }
    }
    return toList()
}
```
주어진 조건자를 만족하는 마지막 요소를 포함하는 목록을 반환
```kt
val chars = ('a'..'z').toList()
println(chars.take(3)) // [a, b, c]
println(chars.takeWhile { it < 'f' }) // [a, b, c, d, e]
println(chars.takeLast(2)) // [y, z]
println(chars.takeLastWhile { it > 'w' }) // [x, y, z]
```