# 폰켓몬

https://school.programmers.co.kr/learn/courses/30/lessons/1845?language=python3

코틀린이 없다.. 근데 같이 풀재서 js로 ..

## 내 풀이

```js
function solution(nums) {
    let cnt = nums.length / 2;
    let whdfb = new Set(nums).size;
    if (whdfb >= cnt) return cnt;
    else return whdfb;
}
```

### 다시 푼 것

```kt
function solution(nums) {
    return Math.min(nums.length/2, new Set(nums).size)
}
```

```java
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;
import java.util.stream.Collectors;

class Solution {
    public int solution(int[] nums) {
        int x = nums.length / 2;
        int y = new HashSet<Integer>(Arrays.stream(nums).boxed().collect(Collectors.toList())).size();

        return Math.min(x, y);
    }
}
```

```py
def solution(nums):
    return min( len(nums)/2, len(set(nums)) )
```

## 다른 사람 풀이

```js
function solution(nums) {
    const max = nums.length / 2;
    const arr = [...new Set(nums)];

    return arr.length > max ? max : arr.length;
}
```

```kt
import java.util.Arrays;
import java.util.stream.Collectors;

class Solution {
    public int solution(int[] nums) {
        return Arrays.stream(nums)
                .boxed()
                .collect(Collectors.collectingAndThen(Collectors.toSet(),
                        phonekemons -> Integer.min(phonekemons.size(), nums.length / 2)));
    }
}
```

## 아마도 코틀린으로 풀면?

```kt
import kotlin.math.*
fun main() {
//     val nums: IntArray = intArrayOf(3,1,2,3) 		// 2
//     val nums: IntArray = intArrayOf(3,3,3,2,2,4)		// 3
    val nums: IntArray = intArrayOf(3,3,3,2,2,2)		// 2
    println( min(nums.size / 2, HashSet(nums.toList()).size) )
}
```

> 로컬에서 돌려보기 성공

```kt
class Solution {
    fun solution(nums: IntArray): Int = min(nums.size / 2, HashSet(nums.toList()).size)
}
```

> 아마도 이걸로 성공 할 수 있을듯 하다

## DATE

> 2023-09-27 00:10
