# 컴퓨터 과학 교양 강좌 : cs 50

---

[CHAPTER1](https://howonkim20.github.io/Study/CHAPTER1) 웹 프로그래밍의 기초

---

[CHAPTER2](https://howonkim20.github.io/Study/CHAPTER2) DB연결 웹앱

---

[CHAPTER3](https://howonkim20.github.io/Study/CHAPTER3) 웹 앱 개발 예약 서비스(1/4)

---

[CHAPTER4](https://howonkim20.github.io/Study/CHAPTER4) 웹 앱 개발 예약 서비스(2/4)

---

[CHAPTER5](https://howonkim20.github.io/Study/CHAPTER5) 웹 앱 개발 예약 서비스(3/4)

---

[CHAPTER6](https://howonkim20.github.io/Study/CHAPTER6) 웹 앱 개발 예약 서비스(4/4)

---

# chapter 1 : 웹 프로그래밍의 기초

<br> <br>

---

# 소단원

## 1. 웹의 동작

- 들어가기 전 <br>
  사람과 사람이 전화 통화를 하기 위해서도 몇 가지 규약이 필요합니다.
  서로 알아들을 수 있는 말을 사용해야 하며, 한쪽이 말할 때 다른 쪽에서는 들어야 합니다.
  또한, 전화 연결이 끊어지면 더 대화를 할 수가 없습니다.
  웹 브라우저와 웹 서버 간에도 서로 통신하기 위해서는 규약이 필요합니다.
  이때 필요한 규약이 HTTP입니다.
- 핵심 개념 <br>
  HTTP, Request 형식, Request Method, Response 형식, 응답 코드

        1. HTTP (Hypertext Transfer Protocol)란?
        팀 버너스리(Tim Berners-Lee)와 그가 속한 팀은 CERN에서 HTML뿐만 아니라 웹 브라우저 및 웹 브라우저 관련 기술과 HTTP를 발명하였습니다.
        문서화된 최초의 HTTP버전은 HTTP v0.9(1991년)입니다.
        HTTP는 서버와 클라이언트가 인터넷상에서 데이터를 주고받기 위한 프로토콜(protocol)입니다.
        HTTP는 계속 발전하여 HTTP/2까지 버전이 등장한 상태입니다.

        2. HTTP 작동방식
        HTTP는 서버/클라이언트 모델을 따릅니다.
        장점
        - 불특정 다수를 대상으로 하는 서비스에는 적합하다.
        - 클라이언트와 서버가 계속 연결된 형태가 아니기 때문에 클라이언트와 서버 간의 최대 연결 수보다 훨씬 많은 요청과 응답을 처리할 수 있다.
        단점
        - 연결을 끊어버리기 때문에, 클라이언트의 이전 상황을 알 수가 없다.
        - 이러한 특징을 무상태(Stateless)라고 말한다.
        - 이러한 특징 때문에 정보를 유지하기 위해서 Cookie와 같은 기술이 등장하게 되었다.

        3. URL (Uniform Resource Locator)
        인터넷 상의 자원의 위치
        특정 웹 서버의 특정 파일에 접근하기 위한 경로 혹은 주소

 <img width="704" alt="스크린샷 2021-02-15 오전 10 41 14" src="https://user-images.githubusercontent.com/71308639/107897131-b566b600-6f7b-11eb-9993-183c2e409b21.png">

HTTP (Hypertext Transfer Protocol)

- 요청 메서드 : GET, PUT, POST, PUSH, OPTIONS 등의 요청 방식이 온다.

- 요청 URI : 요청하는 자원의 위치를 명시한다.

- HTTP 프로토콜 버전 : 웹 브라우저가 사용하는 프로토콜 버전이다.

첫번째 줄의 요청메소드는 서버에게 요청의 종류를 알려주기 위해서 사용됩니다.

각각의 메소드 이름은 다음과 같은 의미를 가집니다.

참고로 최초의 웹 서버는 GET방식만 지원해줬습니다.

- GET : 정보를 요청하기 위해서 사용한다. (SELECT)

- POST : 정보를 밀어넣기 위해서 사용한다. (INSERT)

- PUT : 정보를 업데이트하기 위해서 사용한다. (UPDATE)

- DELETE : 정보를 삭제하기 위해서 사용한다. (DELETE)

- HEAD : (HTTP)헤더 정보만 요청한다. 해당 자원이 존재하는지 혹은 서버에 문제가 없는지를 확인하기 위해서 사용한다.

- OPTIONS : 웹서버가 지원하는 메서드의 종류를 요청한다.

- TRACE : 클라이언트의 요청을 그대로 반환한다. 예컨데 echo 서비스로 서버 상태를 확인하기 위한 목적으로 주로 사용한다.

### 참고링크

https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview

## 2. 웹 Front-End 와 Bak-End 1

- 들어가기 전에 <br>
  웹은 프론트엔드(FE)와 백엔드(BE)로 나눠집니다.
  우리가 인터넷을 하기 위해서 브라우저에서 웹을 탐색하곤 하는데요.
  브라우저를 프론트엔드 또는 클라이언트라고도 합니다.
  웹백엔드는 인터넷 사용자에게는 보이지 않는 것이죠.
  각각의 역할을 기술적인 관점에서 알아보도록 하죠.

- 핵심 개념 <br>
  HTML, CSS, JavaScript, 클라이언트, 서버

          웹프론트엔드?
          - 사용자에게 웹을 통해 다양한 콘텐츠(문서, 동영상, 사진 등)를 제공합니다.
          - 또한, 사용자의 요청(요구사항)에 반응해서 동작합니다.
          웹프론트엔드의 역할
          - 웹콘텐츠를 잘 보여주기 위해 구조를 만들어야 합니다.(신문,책등과 같이) - HTML
          - 적절한 배치와 일관된 디자인 등을 제공해야 합니다.(보기 좋게) - CSS
          - 사용자 요청을 잘 반영해야 합니다.(소통하듯이) - Javascript

- HTML 코드 예시<br>
  원하는 문서의 구조를 프로그래밍 언어로 표현해야 합니다.<br>
  HTML이라는 것은 그 구조를 잘 표현해 줍니다.

<img width="622" alt="스크린샷 2021-02-15 오전 11 19 30" src="https://user-images.githubusercontent.com/71308639/107898673-b39ef180-6f7f-11eb-8238-a4dd72e7e391.png">

- 스타일 - CSS 코드예시 <br>
  웹페이지를 꾸미기 위해서는 각각의 HTML 태그(문서의 구조를 표현한 각 조각 단위)를 꾸미기 위한 규칙이 필요합니다. <br>
  CSS는 이를 표현할 수 있는 프로그래밍 언어입니다.

<img width="636" alt="스크린샷 2021-02-15 오전 11 21 50" src="https://user-images.githubusercontent.com/71308639/107898792-037db880-6f80-11eb-82e2-228ea3717165.png">

- 동작 - JavaScript 코드예시<br>

  TML,CSS를 이리저리 움직이고 변경할 필요가 있을 거예요.<br>
  JavaScript가 그걸 해줍니다.

<img width="637" alt="스크린샷 2021-02-15 오전 11 23 17" src="https://user-images.githubusercontent.com/71308639/107898880-388a0b00-6f80-11eb-8319-cb075eba6445.png">

### 참고링크

http://html-css-js.com/ <br>

https://www.edwith.org/boostcourse-ui
