# 코드 처리하기

https://school.programmers.co.kr/learn/courses/30/lessons/181932

## 내 풀이
```kt
class Solution {
    fun solution(code: String): String {
        var mode = 0
        var ret: String = ""
        (0 until code.length).forEachIndexed { i, v ->
            when (mode == 0) {
                true -> when (code[i].toString() == "1") {
                    true -> mode = 1
                    else -> if (i % 2 == 0) ret += code[i].toString()
                }
                else -> when (code[i].toString() == "1") {
                    true -> mode = 0 
                    else -> if (i % 2 != 0) ret += code[i].toString()
                }
            }
        }
        
        return if (ret.length == 0) "EMPTY" else ret
    }
}
```

## 다른 사람 풀이
```kt
class Solution {
    fun solution(code: String): String {
        var mode = 0
        var answer = ""
        code.forEachIndexed { i, v ->
            if (v == '1') mode = mode xor 1
            else if (mode == 0 && i % 2 == 0) answer += v
            else if (mode == 1 && i % 2 != 0) answer += v
        }
        return if (answer.isNotEmpty()) answer else "EMPTY"
    }
}
```

```kt
class Solution {
    fun solution(code: String) = code.foldIndexed("" to 0) { i, (ret, mode), c ->
        if (c == '1') ret to 1 - mode else if (mode == i % 2) ret + c to mode else ret to mode
    }.first.ifEmpty { "EMPTY" }
}
```

```kt
class Solution {

    private var mode = 0

    fun solution(code: String): String = code.filterIndexed { idx, ch ->
        if (ch == '1') mode = (mode + 1) % 2
        ch != '1' && mode == idx % 2
    }.ifEmpty { "EMPTY" }
}

```