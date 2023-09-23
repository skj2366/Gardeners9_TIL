# 등차수열의 특정한 항만 더하기

https://school.programmers.co.kr/learn/courses/30/lessons/181931

## 내 풀이
```kt
class Solution {
    fun solution(a: Int, d: Int, included: BooleanArray): Int {
        return included.foldIndexed(0) { i, acc, s ->  acc + (a + (i * d)) * if (s) 1 else 0 }
    }
}
```

## 다른 사람 풀이
```kt
class Solution {
    fun solution(a: Int, d: Int, included: BooleanArray) = included.indices.filter { included[it] }.sumOf { a + d * it }
}
```

```kt
class Solution {
    fun solution(a: Int, d: Int, included: BooleanArray): Int {

        return included.mapIndexed{i,v -> 
            (a + d * i).takeIf{v} ?: 0
        }.sum()
    }
}
```

```kt
class Solution {
    fun solution(a: Int, d: Int, included: BooleanArray): Int {
        return List(included.size) { a + d * it }
            .filterIndexed{ idx, value -> included[idx] }
            .sum()
    }
}
```