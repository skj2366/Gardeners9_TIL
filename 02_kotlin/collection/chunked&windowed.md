# chunked()

컬렉션을 각각 주어진 크기를 초과하지 않는 목록 목록으로 분할

```kt
fun <T> Iterable<T>.chunked(size: Int): List<List<T>>
```

## .e.g
```kt
	val words = "one two three four five six seven eight nine ten".split(' ')
	val chunks = words.chunked(3)

	println(chunks) // [[one, two, three], [four, five, six], [seven, eight, nine], [ten]]
```


# windowed()

collection 의 element 를 주어진 사이즈로 구성 가능한 모든 리스트를 얻는다.

```kt
fun <T> Iterable<T>.windowed(
    size: Int, 
    step: Int = 1, 
    partialWindows: Boolean = false
): List<List<T>>
```

## .e.g
```kt
val sequence = generateSequence(1) { it + 1 }

val defaultWindow = sequence.windowed(5) // [[1, 2, 3, 4, 5], [2, 3, 4, 5, 6], [3, 4, 5, 6, 7], [4, 5, 6, 7, 8]]
println(defaultWindow.take(4).toList())

val windows = sequence.windowed(size = 5, step = 1)
println(windows.take(4).toList()) // [[1, 2, 3, 4, 5], [2, 3, 4, 5, 6], [3, 4, 5, 6, 7], [4, 5, 6, 7, 8]]

val moreSparseWindows = sequence.windowed(size = 5, step = 3)
println(moreSparseWindows.take(4).toList()) // [[1, 2, 3, 4, 5], [4, 5, 6, 7, 8], [7, 8, 9, 10, 11], [10, 11, 12, 13, 14]]

val fullWindows = sequence.take(10).windowed(size = 5, step = 3)
println(fullWindows.toList()) // [[1, 2, 3, 4, 5], [4, 5, 6, 7, 8]]

val partialWindows = sequence.take(10).windowed(size = 5, step = 3, partialWindows = true)
println(partialWindows.toList()) // [[1, 2, 3, 4, 5], [4, 5, 6, 7, 8], [7, 8, 9, 10], [10]]
```