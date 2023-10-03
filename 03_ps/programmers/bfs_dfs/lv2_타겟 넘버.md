# 타겟 넘버

https://school.programmers.co.kr/learn/courses/30/lessons/43165

## 내 풀이
```kt
class Solution {
    fun dfs(idx: Int, res: Int, numbers:IntArray, target:Int): Int {
        return if (idx == numbers.size) if (res == target) 1 else 0
        else return dfs(idx+1, res + numbers[idx], numbers, target) + dfs(idx+1, res - numbers[idx], numbers, target)
    }
    
    fun solution(numbers: IntArray, target: Int): Int {
        var answer: Int = dfs(0, 0, numbers, target)
        return answer
    }
}
```
## 다른 사람 풀이
```kt
class Solution {
    fun solution(numbers: IntArray, target: Int): Int {
    return numbers.fold(listOf(0)) { list, i ->
        list.run {
            map { it + i } + map { it - i }
        }
    }.count { it == target }
  }
}
```

## DATE
> 2023-10-02