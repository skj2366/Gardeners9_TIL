# 네트워크

## 내 풀이
js 풀이가 있었다

## 다른 사람 풀이
```kt
class Solution {
    fun solution(n: Int, computers: Array<IntArray>): Int {
        var answer = 0
        val q=java.util.ArrayDeque<Int>()
        val visit=BooleanArray(n)

        for(i in 0 until n){
            if(!visit[i]){
                visit[i]=true
                answer++
                q.add(i)
                while(!q.isEmpty()){
                    val p=q.poll()
                    for(j in 0 until n){
                        if(p==j)    continue
                        if(!visit[j]&&computers[p][j]==1){
                            q.add(j)
                            visit[j]=true
                        }
                    }
                }   
            } 
        }     
        return answer
    }
}
```

```kt
class Solution {
    fun solution(n: Int, computers: Array<IntArray>): Int {
        var routeList = mutableListOf<MutableList<Int>>()

        for(i in 0 until n){
            var route = dfs(computers, mutableMapOf(), i, mutableListOf())
            route.sort()
            routeList.add(route)
        }

        return routeList.toHashSet().size
    }
    fun dfs(a: Array<IntArray>, c: MutableMap<Int, Boolean>, v: Int, route: MutableList<Int>): MutableList<Int> {
        c[v] = true
        route.add(v)

        for (i in 0 until a.size) {
            if (a[v][i] == 1 && (c[i] == null || c[i] == false) ) {
                dfs(a, c, i, route)
            }
        }
        return route
    }
}
```

## DATE
> 2023-10-03