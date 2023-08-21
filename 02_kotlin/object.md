# 객체

## 객체 선언(object declaration)
- 클래스는 인스턴스가 오직 하나만 존재하게 보장하는 싱글턴 패턴을 내장
- 객체를 선언할 때 마찬가지로 싱글턴을 선언하는 방법 중 하나
- `object` 키워드 사용 
  - **즉, 클래스를 정의하며 객체를 생성하는 키워드**
- Java의 무명 내부 클래스(anonymous inner class)


### 싱글톤 (Singleton)
- 싱글톤 패턴은 객체의 인스턴스를 한개만 생성되게 하는 패턴
- 싱글톤 패턴을 사용함으로 인해서 object에 나타나는 특징
  - object키워드로 생성한 객체를 인스턴스화 하지 않고 함수와 변수를 바로 사용 가능 
  - 생성자 및 부생성자 사용 X
- Java에서 싱글톤을 구현하면 관례적으로 INSTANCE 변수를 사용
  - 코틀린에서 object 객체를 생성 하면 INSTANCE 변수를 생성하기 때문에 Java에서 접근 시 INSTANCE로 접근

### 정리 
- `object` 키워드로 선언
- 클래스를 정의하고 인스턴스화하여 변수 저장
- 클래스와 마찬가지로 property, method, 초기화 사용 가능
- 생성자 및 부생성자 사용 X
- 클래스나 인터페이스를 상속 가능


## 동반 객체(companion object)
- 코틀린은 정적 멤버가 없다.
  - 즉, Java의 static 키워드가 없다.
- `패키지 수준의 최상위 함수`, `객체 선언` 으로 활용 가능 
  - 최상위 함수는 static 메소드를 대신할 수 있음.
  - 객체 선언은 최상위 함수가 접근할 수 없는 클래스 내에 private 멤버 변수에 접근할 때 사용.
- 클래스 내부에 객체 선언 시 companion 키워드를 붙이면 동반객체로 선언
- 동반객체(companion)는 클래스 내에 하나만 생성 가능.
- 동반객체는 이름을 지정 할 수 있지만 이름을 지정하지 않으면 객체가 정의된 클래스의 명을 사용 
  - 기본적으로 Companion 으로 명명 된다고 함.

```kt
class TestClass {
  companion object {
    fun objAddFunction(a: Int, b: Int) = a+b
  }
}

fun main() {
  val a: Int = 10;
  val b: Int = 20;
  val result: Int = TestClass.objAddFunction(a, b) // TestClass의 동반객체의 objAddFunction을 바로 꺼내 쓴다.
  println(result)
}
// 30

// 또한 아래와 같이 Companion으로 명명된 규칙으로도 사용 가능
fun main() {
  val a: Int = 10;
  val b: Int = 20;
  val result: Int = TestClass.Companion.objAddFunction(a, b) // TestClass의 동반객체의 objAddFunction을 바로 꺼내 쓴다.
  println(result)
}
// 30

```
- 팩토리 패턴 구현 | 인터페이스 구현 | 무명 객체
  - 정리 필요



