# 무작위로 K개의 수 뽑기

https://school.programmers.co.kr/learn/courses/30/lessons/181858

## 내 풀이

```kt
class Solution {
    fun solution(arr: IntArray, k: Int): IntArray {
        var a = arr.toSet().take(k)
        while (a.size < k) {
            a += -1
        }
        return a.toIntArray()
    }
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(arr: IntArray, k: Int): List<Int> {
        return (0 until k).map { if (it >= arr.toSet().size) -1 else arr.distinct()[it] }
    }
}

class Solution {
    fun solution(arr: IntArray, k: Int): IntArray = if (arr.distinct().size < k) arr.distinct().toIntArray() + IntArray(k - arr.distinct().size) { -1 } else arr.distinct().slice(0 until k).toIntArray()
}
```

## keyword

## DATE

> 2023-10-19
