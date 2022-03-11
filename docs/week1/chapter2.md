---
sidebar_position: 2
---

# 2장 자바스크립트란?

현재 웹 프론트엔드를 다룰 수 있는 유일한 언어이자, node.js의 등장으로 브라우저에서만 동작하는 언어에서 거의 모든 영역으로 확장하고 있는
자바스크립트의 탄생과 성장에 대해서 다루고자 한다. 이해하기 쉽게 연도별로 정리해보았다.

## 2.1 자바스크립트의 탄생

1995년, 90%의 웹 브라우저 시장 점유율을 가지고 있던 넷스케이프 커뮤니케이션즈는 브라우저에서 보조적인 기능을 수행하는
경량 프로그래밍 언어를 입히기로 결정하고 브랜든 아이크가 이를 개발한다. 이후 1996년 3월 "모카", 9월 "라이브스크립트", 12월 "자바스크립트"로
최종 명명되며 자바스크립트가 탄생힌다.

## 2.2 자바스크립트의 표준화

**크로스 브라우징 이슈**  
1996년 8월, 마이크로소프트가 자바스크립트의 파생 버전인 "JScript"를 만들어 ~~인터넷 익스플로러3.0~~ 에 탑재했다.
하지만 JScript와 자바스크립트가 표준화되지 못해, 모든 브라우저에서 동작하는 웹페이지를 개발하기 어려운 문제가 생겼다.

**ECMAScript의 탄생**  
1997년 7월, 표준화된 자바스크립트 초판 사양이 완성되었다.  
2009년, ES5가 HTML5와 함께 출현하면서 JSON, strict mode, map, filter,등의 큰 변화가 있었다.  
2015년, ES6가 출현하며 let/const, arrow function, Map/Set, 템플릿 리터럴 등의 변화가 한번 더 생기면서
프로그래밍 언어로서 갖춰야 할 기능들을 대거 도입했다.

## 2.3 자바스크립트 성장의 역사

초창기 자바스크립트는 말 그대로 스크립트 언어였다. 웹페이지의 보조적인 역할을 수행했고, 진정한 프로그래밍 언어로 인정받지 못하는 경우가 많았다.
하지만 꾸준한 발전을 통해 프로그래밍 언어로 인정받고있다.

### 2.3.1 Ajax

1999년, 자바스크립트에서 서버와 브라우저 사이에 비동기 방식으로 데이터를 교환할 수 있는 Ajax가 XMLHttpRequest라는 이름으로 등장했다.
기존 자바스크립트의 경우, 변경할 필요가 없는 부분까지 포함된 HTML 코드를 전부 서버로부터 받아와야 했지만 Ajax의 등장으로
변경해야하는 부분만 렌더링하는 방식이 가능해졌다. 이를 통해 웹 브라우저도 데스크탑 애플리케이션처럼 부드러운 화면 전환이 가능해졌다.

### 2.3.2 jQuery

2006년, "write less, do more"이라는 모토를 가진 jQuery의 등장으로, DOM 조작을 쉽게 할 수 있게 되었다.

### 2.3.3 V8 자바스크립트 엔진

2008년, V8 자바스크립트 엔진이 등장하면서 자바스크립트는 데스크탑 애플리케이션과 유사한 사용자 경험을 제공할 수 있었다.
자바스크립트는 이 과정에서 꾸준히 발전하면서 웹 서버에서 수행되던 로직들이 클라이언트로 대거 이동하게 되었고, 프론트엔드 영역이
주목받는 계기가 되기도 했다.

### 2.3.4 Node.js

2009년, V8 자바스크립트 엔진으로 개발된 자바스크립트 런타임 환경 Node.js가 탄생한다. 브라우저의 자바스크립트 엔진에서만
동작하던 반쪽짜리 언어였던 자바스크립트 언어가 브라우저의 한계에서 벗어나 다른 환경에서도 동작할 수 있게 되었다.

자바스크립트는 크로스 플랫폼을 위한 가장 중요한 언어로 대두되었다. 웹은 물론 하이브리드 앱, 서버 사이드, 데스크탑, 머신러닝,
로보틱스 환경을 위한 프로그래밍 언어로서 세계에서 가장 인기있는 프로그래밍 언어가 되었다.

### 2.3.5 SPA 프레임워크

프론트엔드 영역에서 처리해야할 로직들이 많아지면서 수많은 자바스크립트 파일들을 관리하는 것이 힘들어졌다.
이 과정에서 아키텍쳐 구축을 쉽게하고 확장하기 쉬운 SPA 방식의 프레임워크 "React, Vue, Angular, Svelte" 등이
탄생하였다.

## 2.4 자바스크립트와 ECMAScript

ECMAScript는 자바스크립트의 핵심 문법들을 정의한 표준 사양이다. 각 브라우저 제조사는 ECMAScript 사양을 준수하면서
클라이언트 사이드 Web API를 추가한 브라우저 내장 자바스크립트 엔진을 구현한다. 즉, 자바스크립트란 ECMAScript에 각종 Web API를
부분집합으로 두는 더욱 큰 개념이라고 볼 수 있다.

## 2.5 자바스크립트의 특징

자바스크립트는 웹 브라우저에서 동작하는 유일한 프로그래밍 언이다.

**인터프리터 언어**  
자바스크립트는 개발자가 별도의 컴파일 작업을 수행하지 않는 인터프리터 언어다. 인터프리터 언어는 코드가 실행되는 단계인 런타임에
문 단위로 한 줄씩 중간코드인 바이트코드로 변환한 후 실행한다. 코드가 실행되기 전 단계인 컴파일 타임에 소스코드 전체를
한번에 머신 코드로 변환한 후 실행하는 컴파일러 언어와 대비해 속도가 느린 단점이 있기 때문에, 모던 자바스크립트 엔진은
인터프리터와 컴파일러의 장점을 결합해 문제를 해결했다.

**프로토타입 기반의 객체지향 언어**  
자바스크립트는 명령형, 함수형, 프로토타입 기반 객체지향 프로그래밍을 지원하는 멀티 패러다임 프로그래밍 언어이다.

## 2.6 ES6 브라우저 지원 현황

인터넷 익스플로러를 제외한 모던 브라우저의 96~99%는 ES6를 지원한다. Node.js도 v4부터 ES6를 지원한다. 구형 브라우저를
고려하는 상황이라면 바벨과 같은 트랜스파일러를 사용할 필요가 있다.