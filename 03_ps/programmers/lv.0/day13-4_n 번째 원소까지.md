# n 번째 원소까지

https://school.programmers.co.kr/learn/courses/30/lessons/181889

# 내 풀이

```kt
class Solution {
    fun solution(num_list: IntArray, n: Int): IntArray = num_list.sliceArray(0 until n)
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(num_list: IntArray, n: Int): IntArray = num_list.slice(0 until n).toIntArray()
}
```

## DATE

> 2023-10-04
