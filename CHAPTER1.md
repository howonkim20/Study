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

## <b> 1. 웹의 동작 </b>

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

## <b> 2. 웹 Front-End 와 Bak-End 1 </b>

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

## <b> 3. 웹 Front-End 와 Bak-End 2 </b>

- 백 엔드 (Back-End)란?<br>
  backend는 정보를 처리하고 저장하며, 요청에 따라 정보를 내려주는 역할을 한다. 가령 쇼핑몰이라면, 상품 정보를 가지고 있고, 주문을 받아서 저장하고, 사용자가 관심있어 하는 상품을 골라주는 역할이 back-End의 역할이다

- 백 엔드 개발자가 알아야 할 것들 <br>
  프로그래밍 언어(JAVA, Python, PHP, Javascript 등)
  웹의 동작 원리
  알고리즘(algorithm), 자료구조 등 프로그래밍 기반 지식
  운영체제, 네트워크 등에 대한 이해
  프레임워크에 대한 이해(예: Spring)
  DBMS에 대한 이해와 사용방법(예: MySQL, Oracle 등)

## <b> 4. Class 와 id 속성 </b>

- 들어가기 전 <br>
  HTML 속성중 class 와 id 는 무엇이며 어떻게 사용할까요?
  이번 소단원에서는 고유한 값인 id와 중복 사용이 가능한 class의 활용 방법에 대해 작성하도록 하겠습니다.
  다른 웹 사이트에서 Class와 Id를 어떻게 사용했는지 확인해보며 이해를 도모하는 것도 좋은 방법입니다.

- 핵심내용 <br>
  HTML 태그 안에서 사용되는 Class 속성과 Id 속성

        ID : 고유한 속성으로 한 HTML 문서에 하나만 사용이 가능 합니다.
        고유한 ID값이 있다면 하나하나에 특별한 제어를 할수 있으며 검색에도 용이 합니다.

        Class?
        - 하나의 HTML문서 안에 중복해서 사용 가능합니다.
        - 하나의 태그에 여러 개의 다른 class 이름을 공백을 기준으로 나열할 수가 있습니다.
        - 홈페이지 전체적인 스타일을 일관성 있게 지정하기 위해서는 class의 사용이 필수적입니다.

        이렇게 구분할 수 있지만, 많은 회사마다 개발단계에서 어떠한 약속(convention)을 만들어서 자신들만의 규칙을 사용하기도 합니다.

        예를 들어 ID사용을 금하는 곳도 있습니다.

        class로만 사용하는 곳도 있습니다.

        그건 팀이 결정하기 나름입니다.

        하지만 반대의 경우 즉 모든 것을 id만으로 사용하는 것은 없겠죠?

## <b> 5. CSS 선언방법 </b>

- 들어가기 전 <br>
  CSS를 HTML 안에 선언하는 방식은 3가지가 있습니다.
  이를 잘 이해하고 활용하는 것이 좋습니다.

- 핵심 개념 <br>
  inline, internal, external

### 1. CSS 의 구성

<img width="618" alt="스크린샷 2021-02-15 오후 1 42 42" src="https://user-images.githubusercontent.com/71308639/107906113-b3105600-6f93-11eb-8e9d-b543c168debd.png">

- span : selector(선택자)
- color : property
- red : value

### 2. Style을 HTML 페이지에 적용하는 3가지 방법

<br><br>

#### <b> 2. inline? </b> <br>

HTML 태그 안에다가 작성합니다. 다른CSS 파일에 적용한 것 보다 가장 먼저 적용합니다.
<img width="619" alt="스크린샷 2021-02-15 오후 1 47 08" src="https://user-images.githubusercontent.com/71308639/107906383-53667a80-6f94-11eb-901e-99ddcde8fbc7.png">

<br> <br>

#### <b> 3. internal? </b> <br>

style 태그로 지정합니다.
구조와 스타일이 섞이게 되므로 유지보수가 어렵습니다.
별도의 CSS파일을 관리하지 않아도 되며 서버에 CSS파일을 부르기 위해 별도의 브라우저가 요청을 보낼 필요가 없습니다.

<img width="468" alt="스크린샷 2021-02-15 오후 1 50 32" src="https://user-images.githubusercontent.com/71308639/107906579-ca037800-6f94-11eb-8897-268ecb6969c3.png">

<br> <br>

#### <b> 4. external </b> <br>

외부파일(.css)로 지정하는 방식입니다.
CSS 코드가 아주 짧지 않다면 가급적 이 방법으로 구현하는 것이 가장 좋습니다.
현업에서는 여러개의 CSS 파일로 분리하고 이를 합쳐서 서비스에서 사용하기도 합니다.
internal 코드와 같은 css코드를 구현하고, style.css와 같은 별도 파일로 만듭니다.
이후에 아래처럼 link태그로 추가하면 됩니다.

<img width="468" alt="스크린샷 2021-02-15 오후 1 50 32" src="https://user-images.githubusercontent.com/71308639/107906676-0d5de680-6f95-11eb-91ae-220c2c7247e2.png">

### <b>5. 우선순위</b>

inline은 별도의 우선순위를 갖지만, internal 과 external은 우선순위가 동등합니다. 따라서 겹치는 선언이 있을 경우 나중에 선언된 속성이 반영됩니다.

참고자료

Difference Between Inline, External and Internal CSS Styles
https://www.hostinger.com
세 가지 방식에 대한 예제와 설명입니다.

## <b> 6. 상속과 우선순위 결정 (1) <b>
