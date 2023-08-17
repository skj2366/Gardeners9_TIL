# 코틀린 문법 

## 변수 선언 
### var (= variable)
- 일반 적인 변수를 선언할 때 사용.
- 언제든지 읽기 쓰기가 가능 
  - like javascript's let
  - like JAVA's 그냥 변수 
- Mutable


### val (= value)
- 선언 시에만 초기화 가능
- 선언 이후에는 값 변경 불가능
  - like javascript's const 
  - like JAVA's final
- Immutable


#### 특징
- 코틀린은 기본 변수에 Null 허용하지 않지만 변수를 선언 후 사용 전까지는 null로 허용될 수 있다.
```kt
fun main() {
  var 변수: Int; // 임시로 null이 허용됨.
  변수 = 1;
}
```

- nullable 존재하긴하나 NullPointerException에 주의해야함.
```kt
fun main() {
  var 변수: Int? = null // nullable
}
```

## 자료형 
- 자바와 거의 동일하다.

### 정수 및 실수
- Int
  - 10진수
    - 10
  - 16진수
    - 0xff
  - 2진수
    - 0b
- Long
  - 1L
- Double
  - 1.5
  - 1.5e10
- Float
  - 11.1f


### 문자
- 2Bytes / UTF-16 BE

- Char
  - 'a'
  - '차'
  - 'A'

### 문자열
- Char 의 집합

- String
  - "test string"
  - 멀티라인


``` kt
func main() {
  var str: String = "test string"

  var strMultiRaw:String = """str
  multi
  raw"""

}
```

### boolean
- Boolean
  - true
  - false




