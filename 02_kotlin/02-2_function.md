# 코틀린 문법 

### 함수

- fun 으로 선언 
- 매개변수(parameter)와 함수 선언 마지막에 리턴 타입을 명시 가능 
  - 타입 추론(type inference)으로 리턴타입 생략도 가능 

``` kotlin
fun addInt(a:Int, b:Int, c:Int): Int {
  return a+b+c
}
```

### expression
- 식
- statement와 다르게 값을 만들고 다른 식의 하위 요소로 계산에 참여
  - 자바에서는 모든 것이 statement (문), 코틀린은 루프를 제외한 대부분의 제어 구조 식
  - 코틀린은 if는 식, 자바는 문
  - 대입문은 자바에서는 식이었지만 코틀린에서는 문이다. 
    - ....? 햇갈리긴 하다.

### 식이 본문인 함수
- 본문이 중괄호로 둘러싸인 함수 = 블록이 본문이 함수 
``` java
public static int add(int a, int b) {
  return a+b;
}
```

- 등호와 식으로 이뤄진 함수 = 식이 본문이 함수
``` kotlin
fun add(a: Int, b: Int) = a+b
// 리턴 타입은 타입추론됨 : Int
```

### 타입 추론 
자료형을 명시하지 컴파일러가 식을 분석해 식의 결과 자료형을 함수 반환 타입으로 알아서 정해준다.

``` kotlin
// 위의 식의 본문인 함수의 코드와 같다
fun add(a: Int, b: Int): Int = a+b
```

### 문자열 템플릿
- string template
- 문자열 리터럴 안에서 사용됨.
- `$` 연산자를 사용하면 선언된 변수를 사용할 수 있음.
- `${}` : 식을 사용 할 수 있음


#### .e.g
``` kotlin 
var cellPhoneNum: String = "010-1234-5678"

println("My phone Number is ${cellPhoneNum}")

// My phone Number is 010-1234-5678
```


## Class & Property

### 클래스
- 값 객체(Value Object)
  - 코드없이 데이터만 저장하는 클래스
  - 코틀린의 기본 접근제어자는 public으로 생략하면 public 이다.

```kt
class Cat(val name: String)
```


### 프로퍼티

- 자바에서는 필드, 접근자 등을 한데 묶어서 프로퍼티라고 칭함
  - 자바에서는 데이터를 필드에 저장
  - 필드 멤버는 보통 private 구성 (정보 은닉)
  - 평균적으로 게터(getter), 세터(setter) 사용
    - Lombok 
- 코틀린은 프로퍼티를 기본 기능으로 제공
  - val : 읽기전용
    - java의 getter 기능 제공
  - var : 읽고 쓰기
    - java의 getter, setter 기능 제공


``` java
public class Person {
    private final String name;
    private boolean isMarried;

    public Person(String name, boolean isMarried) {
        this.name = name;
        this.isMarried = isMarried;
    }

    public String getName() {
        return this.name;
    }

    public void setIsMarried(boolean isMarried) {
        this.isMarried = isMarried;
    }

    public boolean getIsMarried() {
        return this.isMarried;
    }
}
```

```kt
class Person(val name: String, var isMarried: Boolean)
```


- setter 

```java
Person person = new Person("Harry", false);
person.setIsMarried(true);
```
> JAVA


```kt
val person = Person("Harry", false)
person.isMarried = true
```

### 커스텀 접근자
- 커스텀 접근자는 프로퍼티 값을 읽거나 쓸 때 호출되는 특별한 함수다.
- class property로 getter와 setter 기능을 제공하지만 가독성을 위해서 혹은 추가 기능을 위한 커스텀 접근자를 사용 할 수 있다.

```kt
class Person {
  var name: String
  var age: Int
    get() {
      println("execute getter")
      return field
    }
    set(value: Int) {
      field = value
    }
}
```

```kt
class Person(val firstName: String, val familyName: String) {
  val fullName: String
    get(): String {
      return "$firstName $familyName"
    }
}


fun main() {
  val person = Person("John", "Doe")
  println(person.fullName) // John Doe
}
```


### enum class 

- 기본 
```kt
enum class Animal {
  Cat, Dog, Pig, Cow
}
```

- 프로퍼티가 있는 enum

```kt
 작성중 입니다. ... 아 뭔가 정리하기가 너무 난잡하고 힘드네요 
 글 정리에 소질이 없따 ..
```