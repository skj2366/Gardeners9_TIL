# n 번째 원소부터

https://school.programmers.co.kr/learn/courses/30/lessons/181892

# 내 풀이

```kt
class Solution {
    fun solution(num_list: IntArray, n: Int): IntArray = num_list.sliceArray(n-1..num_list.lastIndex)
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(numList: IntArray, n: Int) = numList.copyOfRange(n - 1, numList.size)
}
```

```kt
class Solution {
    fun solution(num_list: IntArray, n: Int): IntArray = num_list.slice(n - 1..num_list.lastIndex).toIntArray()
}
```

## DATE

> 2023-10-04
