# 내용정리
## strict mode란?
- strict mode는 자바스크립트 언어의 문법을 좀 더 엄격히 적용하여 오류를 발생시킬 가능성이 높거나 자바스크리브 엔진의 최적화 작업에 문제를 일으킬 수 있는 코드에 대해 명시적인 에러를 발생시킴.
- strict mode 보단 린트 도구 사용을 선호.
- ES6에 도입된 클래스와 모듈은 기본적으로 strice mode가 적용됨

## strict modedml 적용
- 전역의 선두 또는 함수 몸체의 선두에 'use strice';를 추가.
``` js
'use strict';
function foo() {
    x = 10; //ReffereceError
}
```

``` js
function foo() {
    'use strict';
    x = 10; // ReffereceError
}
```

## 전역에 strict mode를 적용하는 것은 피하자
- 전역에 적용한 strict mode는 스크립트 단위로 적용된다
- 스크립트 단위로 적용된 strict mode는 다른 스크립트에 영향을 주지 않고 해당 스크립트에 한정되어 적용됨
- 외부 서드파티 라이브러리를 사용하는 경우 라이브러리가 non-strict mode인 경우도 있어 전역에 strict mode를 적용하는건 바람직하지 않음

## 함수 단위로 strict mode를 적용하는 것도 피하자
- strict mode는 즉시 실행 함수로 감싼 스크립트 단위로 적용하는 것이 바람직

## strict mode가 발생시키는 에러
### 암묵적 전역
- 선언하지 않은 변수를 참조하면 ReffereceError

### 변수, 함수, 매개변수의 삭제
- delete 연산자로 변수, 함수, 매개변수를 삭제하면 SyntaxError 

### 매개변수 이름의 중복
- SyntaxError 발생

### with 문의 사용
- SyntaxError qkftod
- with는 성능과 가독성에 안좋으므로 사용하지 않는게 좋음

## strict mode 적용에 의한 변화
### 일반 함수의 this
- strict mode에서 함수를 일반 함수로서 호출하면 this에 undefinded가 바인딩됨.
- 생성자 함수가 아닌 일반 함수 내부에서는 this를 사용할 필요가 없기 떄문

### arguments 객체
- strict mode에서는 매개변수에 전달된 인수를 재할당하여 변경해도 argumetns에 반영되지 않음

# 추가정리
