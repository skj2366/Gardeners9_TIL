# 배열의 길이를 2의 거듭제곱으로 만들기

https://school.programmers.co.kr/learn/courses/30/lessons/181857


## 다른 사람 풀이

```kt
import kotlin.math.*

class Solution {
    fun solution(arr: IntArray): IntArray {
        val len = arr.size
        var n = 1
        while (n < len) { n*=2 }
        return arr + IntArray(n-len){ 0 }
    }
}
```
```kt
import kotlin.math.*

class Solution {
    fun solution(arr: IntArray): IntArray {
        return arr.copyOf(2.0.pow(ceil(ln(arr.size.toDouble()) / ln(2.0))).toInt())
    }
}
```

## keyword

## DATE

> 2023-10-24
