# x 사이의 개수

https://school.programmers.co.kr/learn/courses/30/lessons/181867

## 내 풀이

```kt
class Solution {
    fun solution(myString: String): IntArray {
        return myString.split("x").map { it.length }.toIntArray()
    }
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(myString: String) = myString.split("x").map(String::length)
}
```

## keyword

## DATE

> 2023-10-18
