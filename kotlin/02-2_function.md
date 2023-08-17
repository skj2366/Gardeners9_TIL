# 코틀린 문법_함수편

## 함수

- fun 으로 선언 
- 매개변수(parameter)와 함수 선언 마지막에 리턴 타입을 명시 가능 
  - 타입 추론(type inference)으로 리턴타입 생략도 가능 

``` kt
fun addInt(a:Int, b:Int, c:Int): Int {
  return a+b+c
}
```

### expression