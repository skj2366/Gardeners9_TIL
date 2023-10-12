# A 강조하기

https://school.programmers.co.kr/learn/courses/30/lessons/181874

## 내 풀이

```kt
class Solution {
    fun solution(myString: String): String {
        return myString.toList().map { if (it === 'a') it.toUpperCase() else if (it === 'A') it else it.toLowerCase() }.joinToString("")
    }
}
```

## 다른 사람 풀이

```kt
class Solution {
    fun solution(myString: String): String {
        return myString.lowercase().replace("a", "A")
    }
}

class Solution {
    fun solution(myString: String): String {
        return myString.toList().joinToString("") { c -> if (c == 'a' || c == 'A') c.uppercase() else c.lowercase() }
    }
}

class Solution {
    fun solution(myString: String): String {
        return myString
            .lowercase()
            .map { if (it == 'a') it.uppercase() else it }
            .joinToString("")
    }
}
```

## keyword

## DATE

> 2023-10-12
