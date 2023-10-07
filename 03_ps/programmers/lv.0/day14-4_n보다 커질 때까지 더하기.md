# n보다 커질 때까지 더하기

https://school.programmers.co.kr/learn/courses/30/lessons/181884

## 내 풀이

```kt
class Solution {
    fun solution(numbers: IntArray, n: Int): Int = numbers.fold(0) { acc, v -> (acc + v).also { if (n < it ) return it } }
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(numbers: IntArray, n: Int) = numbers.fold(0) { acc, i -> if (n >= acc) acc + i else acc }
}
```

```kt
class Solution {
    fun solution(numbers: IntArray, n: Int): Int {
        return numbers.fold(0) { acc, num -> (acc + num).also { if (n < it) return it } }
    }
}
```

## keyword

## DATE

> 2023-10-07
