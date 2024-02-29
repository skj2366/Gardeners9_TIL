# ETC

## 주의점?

- (컬럼 작업하며) Null이 허용될 수 있으면 모델에 `Option<T>`로 선언해 줘야함
``` rs
enum Option<T> {
    Some(T),
    None,
}
```
> https://showx123.tistory.com/58


## Rust Naming 
https://rust-lang.github.io/api-guidelines/naming.html

### Struct Naming Convention
- struct 규칙은 대문자로 시작 
- 2단어 이상이면 파스칼 케이스
  - e.g) CreateTodoSchema
