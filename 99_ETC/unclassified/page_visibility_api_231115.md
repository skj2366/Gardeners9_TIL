# 2023-11-15 Wed 

## Web Browser에서 application 실행 확인 방법 

- using javascript Web API > `Page Visibility API`

### Page Visibility API
- 문서가 언제 표시되거나 숨겨지는지 알 수 있는 이벤트와 페이지가 현재 보이고 있는지 상태를 살펴볼 수 있는 기능을 제공
- 문서가 보이지 않을 때 작업 수행 줄여서 리소스를 절약하고 성능을 개선하는데 유용
- 조건 : `사용자가 창을 최소화하거나 다른 탭으로 전환`

### 사용 사례
- 사용자가 페이지를 보고 있지 않은 한 다음 슬라이드로 넘어가지 않아야 하는 이미지 캐러셀이 있는 사이트
- 특정 정보에 대한 대시보드를 표시하는 애플리케이션이 페이지가 표시되지 않을 때 서버에 업데이트를 요청하고 싶지 않은 사이트
- 페이지가 미리 렌더링 되는 시기를 감지하여 정확한 페이지 조회 수를 유지하려는 사이트
- 디바이스가 대기 상태(사용자가 전원 버튼을 눌러 화면을 끄는 경우)에 있을 때 소리를 끄고 싶어 하는 사이트

### 인스턴스 속성

#### Document.hidden ( + Document.webkithidden)
Document.hidden 읽기 전용 속성은 페이지가 숨겨졌는지 여부를 Boolean 값 리턴.

``` js 
document.addEventListener("visibilitychange", function () {
  console.log(document.hidden);
  // 숨김 여부가 변했을 때의 행동
});

```

#### Document.visibilityState
이 element가 현재 표시된 컨텍스트를 나타내는 document의 가시성을 반환.

 document가 background 또는 보이지 않는 탭(다른 탭)에 있는지, 또는 pre-rendering을 위해 로드 된 것인지를 아는 것은 유용합니다. 가능한 값은 다음과 같습니다.

- 'visible' : 페이지 내용은 적어도 부분적으로 보일 수 있습니다. 실제로 이는 페이지가 최소화 되지 않은 창(브라우저)에서의 선택된 탭 을 의미 합니다.
- 'hidden' : 페이지 내용은 사용자에게 표시되지 않습니다. 실제로 이는 document가 background-tap(다른 탭)이거나, 최소화 된 창의 일부이거나, OS 화면 잠금이 활성 상태임을 의미합니다.
이 property의 값이 변경되면 visibilitychange 이벤트가 Document로 전송

``` js 
document.addEventListener("visibilitychange", () => {
  console.log(document.visibilityState);
  // 기타 동작...
});

```

### Etc 
- 오디오를 재생하는 탭은 활성화된 탭으로 간주되어 스로틀링되지 않습니다.
- 실시간 네트워크 연결(WebSockets 및 WebRTC)을 사용하는 코드를 실행하는 탭은 이러한 연결 시간이 초과하여 예기치 않게 닫히는 것을 방지하기 위해 스로틀링이 해제됩니다.
- IndexedDB 프로세스도 시간 초과를 피하고자 스로틀링이 되지 않은 상태로 유지됩니다.


> 출처 : https://developer.mozilla.org/ko/docs/Web/API/Page_Visibility_API#%EB%8B%A4%EB%A5%B8_%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4%EB%A1%9C%EC%9D%98_%ED%99%95%EC%9E%A5