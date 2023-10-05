# 홀수 vs 짝수

https://school.programmers.co.kr/learn/courses/30/lessons/181887

## 내 풀이

```kt
import kotlin.math.*

class Solution {
    fun solution(num_list: IntArray): Int {
        return max(num_list.filterIndexed { i,v -> (i+1) % 2 == 0 }.sum(), num_list.filterIndexed { i,v -> (i+1) % 2 != 0 }.sum())
    }
}
```

## 다른 사람 풀이

```kt
import kotlin.math.max

class Solution {
    fun solution(numList: IntArray) = numList.indices.partition { it % 2 == 1 }.let { (oddList, evenList) -> max(oddList.sumOf { numList[it] }, evenList.sumOf { numList[it] }) }
}
```

```kt
class Solution {
    fun solution(num_list: IntArray): Int = num_list.filterIndexed { i, _ -> i % 2 == 0}.sum().let { if(num_list.sum() - it >= it) num_list.sum() - it else it}
}
```

## DATE

> 2023-10-05
