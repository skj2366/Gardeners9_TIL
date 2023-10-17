# ad 제거하기

https://school.programmers.co.kr/learn/courses/30/lessons/181870

## 내 풀이

```kt
class Solution {
    fun solution(strArr: Array<String>): Array<String> {
        return strArr.filter { it.indexOf("ad") == -1 }.toTypedArray()
    }
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(strArr: Array<String>): Array<String> = strArr.filter{!it.contains("ad")}.toTypedArray()
}
```

## keyword

## DATE

> 2023-10-17
