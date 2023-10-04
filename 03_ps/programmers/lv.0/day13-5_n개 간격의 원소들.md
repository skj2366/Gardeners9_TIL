# n개 간격의 원소들

https://school.programmers.co.kr/learn/courses/30/lessons/181888

# 내 풀이

```kt
class Solution {
    fun solution(num_list: IntArray, n: Int): IntArray = num_list.filterIndexed { i, v -> i % n == 0 }.toIntArray()
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(num_list: IntArray, n: Int): IntArray {
        return num_list.filterIndexed { index, _ -> index % n == 0 }.toIntArray()
    }
}

class Solution {
    fun solution(numList: IntArray, n: Int) = (numList.indices step n).map { numList[it] }
}
```

## DATE

> 2023-10-04
