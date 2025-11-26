# Vue

## Onboarding
서버에서 데이터를 받아와 DOM을 직접 수정하는 AJAX 방식. 데이터 바뀔 때마다 매번 DOM 요소를 찾아 수정하기보다 편한 방법 없을까?
<ul>
<li>Vue를 통한 자동화</li>
<li>데이터가 바뀌면 UI는 어떠해야 한다 선언 </li>
<li>데이터가 바뀌면 화면이 알아서 바뀌는 Vue의 반응성. 더이상 DOM 조작에 신경X</li>
</ul>

## Frontend Development

웹사이트와 웹 애플리케이션의 사용자 인터페이스(UI)와 사용자 경험(UX)를 만들고 디자인하는 것. (HTML, CSS, JavaScript 등 활용)

- Client-side frameworks
    - 클라이언트 측에서 UI와 상호작용을 개발하기 위해 사용되는 JavaScript 기반 프레임워크
    - UI 효율적 만들기 위해 미리 짜놓은 코드의 뼈대. 부품단위 개발
    - 동적 웹사이트가 주로 사용. 대표적으로 Vue, React, Angular 있음. 

- Client-side frameworks의 필요성
    - 무언가를 읽는 곳에서 -> 무언가를 하는 곳으로 변화
    - 다루는 데이터가 많아짐 (일관성있고 안정적인 업데이트)
    - 동적이고 반응적인 웹 애플리케이션 개발(실시간 데이터 업데이트)
    - 코드 재사용성 증가(컴포넌트 기반, 모듈화된 코드구조)
    - 개발 생산성 향상(강력한 개발 도구)

- Single Page Application (SPA)
    - 단일 페이지에서 동작하는 웹 애플리케이션
    - 하나의 HTML 파일 위에서 JavaScript가 필요한 부분만 교체
    - 페이지 이동 없이 동작. 빠르고 부드러운 사용자 경험

- SPA 작동원리
    - 최초 로드 시 어플리케이션에 필요한 주요 리소스를 다운로드
    - 페이지 갱신에 대해 필요한 데이터만을 비동기적으로 전달 받아 화면의 필요한 부분만 동적으로 갱신 ( AJAX와 같은 기술 사용하여 필요한 데이터만 비동기적으로 로드)
    - JavaScript를 사용하여 클라이언트 측에서 동적으로 콘텐츠를 생성하고 업데이트(CSR방식)

- Client Side Rendering (CSR)
    - 클라이언트에서 콘텐츠를 렌더링하는 방식
    - 빈 집(HTML)에서 가구(JavaScript)를 배송받아 직접 조립하는 방식
    - 브라우저는 거의 텅 빈 HTML 과 JavaScript 파일 받아온 후 JavaScript가 실행되어 데이터를 요청하고, 화면을 동적으로 완성

- CSR 작동 원리
    - 사용자가 웹사이트에 요청 보냄
    - 서버는 최소한의 HTML과 JavaScript 파일을 클라이언트로 전송
    - 클라이언트는 HTML과 JavaScript 다운 받음
    - 브라우저가 JavaScript 실행하여 동적으로 페이지 콘텐츠를 생성
    - 필요한 데이터는 API 통해 서버로부터 비동기적으로 가져옴
    - (이후 서버는 더이상 HTML 제공하지 않고 요청에 필요한 데이터만 응답)

- CSR과 SPA 장점
    - 빠른 페이지 전환 (페이치 최초 로드 이후 필요한 데이터만 가져와 페이지 일부만 렌더링, 서버로 전송되는 데이터 양 최소화)
    - 사용자 경험, Frontend와 Backend 명확히 분리

- CSR과 SPA 단점
    - 느린 초기 로드 속도, SEO(검색엔진 최적화) 문제

## Vue
사용자 인터페이스를 구축하기 위한 JavaScript 프론트엔드 프레임워크

컴포넌트로 화면 조립, 데이터 바뀌면 화면도 자동으로 바뀌는 반응성이 가장 큰 특징

Vue의 핵심 기능: 선언적 렌더링, 반응성

Component: 재사용 가능한 코드 블록. UI를 독립적이고 재사용 가능한 일부분으로 분할하고 각부분을 개별적으로 다룸. 중첩된 Component의 트리 형태


## Vue 사용 방법

1. CDN 방식
Vue Application 생성하기

1-1. CDN 작성
![alt text](image.png)

1-2. application instance
![alt text](image-1.png)
전역 Vue 객체 불러옴. 구조분해할당 문법으로 Vue 객체의 createApp 함수를 할당

![alt text](image-2.png)
모든 Vue application은 createApp 함수로 새 application instance를 생성하는 것으로 시작함

1-3. Root Component
createApp 함수에는 객체(컴포넌트)가 전달됨. 
![alt text](image-3.png)
모든 App에는 다른 컴포넌트들을 하위 컴포넌트로 포함할 수 있는 Root 컴포넌트가 필요.

1-4. Mounting the App
HTML 요소에 Vue application instance를 연결. 각 앱 인스턴스에 대해 mount()는 한 번만 호출 가능
![alt text](image-4.png)
![alt text](image-5.png)

1-5. setup() 함수
컴포넌트 동작 전 미리 준비하는 시작점. 이 함수 안에서 데이터를 정의, 화면에 표시할 값 계산, 각종 로직 준비


2. NPM 설치 방식


## 반응형 상태
ref(): 반응형 상태를 선언하는 함수
![alt text](image-6.png)
일반 JavaScript 변수를 Vue가 변화를 감지할 수 있는 반응형 객체로 래핑하여 반환. 

컴포넌트 내에서 변하는 값의 상태를 추적 관리하기 위해 사용.

ref로 선언된 변수의 값이 변경되면 해당 값을 사용하는 템플릿에서 자동으로 업데이트

![alt text](image-7.png)
템플릿의 참조에 접근하려면 setup함수에서 선언 및 반환 필요.

![alt text](image-8.png)
편의상 템플릿에서 사용시 .value 작성 불필요

## Vue 기본 구조

- createApp()에 전달되는 객체는 Vue 컴포넌트. 
    - 컴포넌트의 상태는 setup() 함수 내에서 선언되어야 하며 객체를 반환해야 함.

- 템플릿 렌더링
    - 반환된 객체의 속성은 템플릿에서 사용 가능. {{}} 사용 메시지 값을 기반으로 동적 텍스트를 렌더링.
    - 유효한 JavaScript 표현식 사용 가능

- Event Listeners in Vue
![alt text](image-9.png)
    - v-on directive 사용하여 DOM 이벤트를 수신. 함수 내에서 반응형 변수 변경하여 업데이트

## 참고
- ref 객체
    - 변수 변형 감지를 위해 참조 자료형의 객체 타입으로 구현. (일반 변수는 감지 불가)

    - ref는 값 바뀌면 화면 자동 업데이트, 일반변수는 값 바뀌어도 화면 갱신X

- 템플릿 unwrap 주의
    - unwrap은 ref가 setup에서 반환된 객체의 최상위 속성인 경우에만 적용. 
    - 해결하려면 원하는 속성을 객체에서 분해하여 최상위 속성으로 만들어줌.
