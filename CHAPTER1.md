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

- 들어가기전 <br>
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

        4.
        <img width="704" alt="스크린샷 2021-02-15 오전 10 41 14" src="https://user-images.githubusercontent.com/71308639/107897131-b566b600-6f7b-11eb-9993-183c2e409b21.png">
