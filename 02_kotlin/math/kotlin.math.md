# Package kotlin.math
수학 함수와 상수.

## 조건 
`import kotlin.math.*`

## CONST 

### absoluteValue
```kt
val Double.absoluteValue: Double
val Float.absoluteValue: Float
val Int.absoluteValue: Int
val Long.absoluteValue: Long
```
값의 절대값을 반환 

### PI
```kt
const val PI: Double
```
원주와 지름의 비율, 약 3.14159

### E
```kt
const val E: Double
```
자연 로그의 기초, 약 2.71828.

### sign
```kt
val Double.sign: Double
val Float.sign: Float
val Int.sign: Int
val Long.sign: Int
```
값의 부호를 반환

### ulp
```kt
val Double.ulp: Double
val Float.ulp: Float
```
값의 ulp (마지막 장소의 단위)를 반환

## FUN

### max()
```kt
fun max(a: UInt, b: UInt): UInt
fun max(a: ULong, b: ULong): ULong
fun max(a: Double, b: Double): Double
fun max(a: Float, b: Float): Float
fun max(a: Int, b: Int): Int
fun max(a: Long, b: Long): Long
```
두 값 중 큰 값을 반환

### min()
```kt
fun min(a: UInt, b: UInt): UInt
fun min(a: ULong, b: ULong): ULong
fun min(a: Double, b: Double): Double
fun min(a: Float, b: Float): Float
fun min(a: Int, b: Int): Int
fun min(a: Long, b: Long): Long
```
두 값 중 작은 값을 반환

### abs()
```kt
fun abs(x: Double): Double
fun abs(x: Float): Float
fun abs(n: Int): Int
fun abs(n: Long): Long
...

```
주어진 값의 절대값을 반환

### pow()
```kt
fun Double.pow(x: Double): Double
fun Float.pow(x: Float): Float
fun Double.pow(n: Int): Double
fun Float.pow(n: Int): Float
```
값을 주어진 인수값의 거듭제곱으로 반환.
* **값의 기준은 Double**


### acos()
```kt
fun acos(x: Double): Double
fun acos(x: Float): Float
```
주어진 값의 아크코사인을 반환.
반환 된 값은 0.0 에서 PI 라디안 범위의 각도.

### acosh()
```kt
fun acosh(x: Double): Double
fun acosh(x: Float): Float
```
값의 역 하이퍼 볼릭 코사인을 계산

### asin()
```kt
fun asin(x: Double): Double
fun asin(x: Float): Float
```
주어진 값의 아크 사인을 계산하여 반환. 
반환 된 값은 -PI/2 에서 PI/2 라디안 범위의 각도.

### asinh()
주어진 값의 역 쌍곡 사인 반환

### atan()
주어진 값의 아크탄젠트 반환.
반환 된 값은 -PI/2 에서 PI/2 라디안 범위의 각도.

### atanh()
역 쌍곡 탄젠트

### cbrt()
주어진 값의 세제곱근

### ceil()
```kt
fun ceil(x: Double): Double
fun ceil(x: Float): Float
```
주어진 값을 정수로 올림 하여 반환

### cos()
```kt
fun cos(x: Double): Double
fun cos(x: Float): Float
```

라디안으로 주어진 각도의 코사인 반환

### cosh()
쌍곡코사인

### exp()
오일러의 수 e를 주어진 값의 거듭제곱으로 계산

### floor()
```kt
fun floor(x: Double): Double
fun floor(x: Float): Float
```
주어진 값을 정수로 내림하여 반환

### hypot()
```kt
fun hypot(x: Double, y: Double): Double
fun hypot(x: Float, y: Float): Float
```
sqrt(x^2 + y^2)

### ln()
```kt
fun ln(x: Double): Double
fun ln(x: Float): Float
```
주어진 값의 자연 로그 반환

### log()
```kt
fun log(x: Double, base: Double): Double
fun log(x: Float, base: Float): Float
```
주어진 밑에 대한 값 x의 로그를 반환
- log10 : 밑이 10인 상용로그
- log2 : 밑이 2인 이진로그


### round()
```kt
fun round(x: Double): Double
fun round(x: Float): Float
```
반올림 

### roundToInt()
```kt
fun Double.roundToInt(): Int
fun Float.roundToInt(): Int
```
Double 및 Float 값을 가장 가까운 정수로 반올림하고 결과를 Int 로 변환.

### roundToLong()
Double 및 Float 값을 가장 가까운 정수로 반올림하고 결과를 Long 으로 변환.

### sign()
```kt
fun sign(x: Double): Double
fun sign(x: Float): Float
```
주어진 값의 부호를 반환

### sin()
주어진 각도의 사인 반환
- sinh() : 쌍곡사인

### sqrt()
```kt
fun sqrt(x: Double): Double
fun sqrt(x: Float): Float
```
주어진 값의 제곱근 계산

### tan()
주어진 각도의 탄젠트 계산
- tanh() : 쌍곡 탄젠트


