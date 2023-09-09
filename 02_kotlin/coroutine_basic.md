## Kotlin coroutine

코루틴은 Kotlin에서 비동기 프로그래밍을 간편하게 다루기 위한 라이브러리

Kotlin 코루틴은 비동기 작업을 간편하게 다룰 수 있으며, 스레드 관리와 예외 처리 등 다양한 기능을 제공

### 1. 코루틴 시작하기

```kotlin
import kotlinx.coroutines.*

fun main() {
    // GlobalScope에서 코루틴 시작
    GlobalScope.launch {
        delay(1000) // 1초 대기
        println("Hello, Coroutine!")
    }

    // 메인 스레드가 종료되지 않도록 대기
    Thread.sleep(2000)
}
```

### 2. 코루틴 일시 중단 함수

코루틴은 delay()와 같은 일시 중단 함수를 사용하여 비동기 작업을 수행

```kt
import kotlinx.coroutines.*

fun main() = runBlocking {
    launch {
        delay(1000)
        println("코루틴이 일시 중단되었다가 다시 실행됨")
    }
    println("메인 스레드가 계속 실행됨")
    delay(2000)
}

```

### 3. 코루틴 스코프
코루틴은 스코프 내에서 실행되며 스코프가 종료되면 함께 종료

```kt
import kotlinx.coroutines.*

fun main() = runBlocking {
    println("메인 스코프 시작")
    launch {
        println("코루틴 스코프 시작")
        delay(1000)
        println("코루틴 스코프 종료")
    }
    println("메인 스코프 종료")
}

```

### 4. 예외 처리
```kt
import kotlinx.coroutines.*

fun main() = runBlocking {
    val job = launch {
        try {
            delay(1000)
            throw RuntimeException("예외 발생!")
        } catch (e: Exception) {
            println("예외 처리: $e")
        }
    }
    job.join()
}

```

