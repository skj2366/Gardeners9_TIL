# replaceRange

주어진 범위의 부분이 대체 문자 시퀀스로 대체되는 이 문자 시퀀스의 내용이 포함된 문자 시퀀스를 반환

```kt
fun CharSequence.replaceRange(
    startIndex: Int,
    endIndex: Int,
    replacement: CharSequence
): CharSequence

fun String.replaceRange(
    startIndex: Int,
    endIndex: Int,
    replacement: CharSequence
): String
```

## .e.g

```kt
var my_string = "He11oWor1d"
var overwrite_string = "lloWorl"
var s = 2

println(my_string.replaceRange(s, s+overwrite_string.length, overwrite_string))

// "HelloWorld"
```
