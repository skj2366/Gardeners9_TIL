# startsWith()

-   이 문자열이 지정된 접두사로 시작하면 true 를 반환

```kt
fun String.startsWith(
    prefix: String,
    ignoreCase: Boolean = false
): Boolean
```

-   지정된 오프셋 startIndex에서 시작 하는이 문자열의 하위 문자열이 지정된 접두사로 시작 하는 경우 true 를 반환

```kt
fun String.startsWith(
    prefix: String,
    startIndex: Int,
    ignoreCase: Boolean = false
): Boolean
```

## .e.g

```kt
class Solution {
    var my_string: String = "banana"
    var is_prefix: String = "ban"
    fun solution(my_string: String, is_prefix: String): Int {
        return if (my_string.startsWith(is_prefix)) 1 else 0
    }

    println(solution(my_string, is_prefix)) // 1

    is_prefix = "qwer"

    println(solution(my_string, is_prefix)) // 0
}
```
