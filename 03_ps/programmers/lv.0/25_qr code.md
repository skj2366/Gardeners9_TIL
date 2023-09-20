# qr code

https://school.programmers.co.kr/learn/courses/30/lessons/181903

## 내 풀이

```kt
class Solution {
    fun solution(q: Int, r: Int, code: String) = code.filterIndexed { i, s -> i % q == r }
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(q: Int, r: Int, code: String): String {
        return code.indices.filter { it % q == r }.joinToString("") { code[it].toString() }
    }
}
```

```kt
class Solution {
    fun solution(q: Int, r: Int, code: String): String {
        return code.foldIndexed("") { index, acc, n ->
            if (index % q == r) acc + n
            else acc
        }
    }
}
```

## DATE

> 2023-09-21
