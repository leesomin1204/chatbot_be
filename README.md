# Chatbot 백엔드

## 개요
AI 챗봇 대화 서버 (Spring Boot 기반) <br>
클라이언트로부터 사용자의 메시지를 전달받아 응답을 생성하고, 이를 JSON 형태로 반환하는 간단한 챗봇 백엔드입니다. <br>
프론트엔드에서 요청한 메시지를 받아 고정 응답 또는 향후 AI 모델 응답으로 확장 가능하도록 설계되어 있습니다.

## 기능 설명
- 기능 설명
  - API 개요
    - 요청 방식: GET
    - 요청 URL: /chat?message={사용자입력}

## 코드 리뷰
- ChatController.java
  - /chat 엔드포인트를 제공하는 REST 컨트롤러
  - @RequestParam으로 사용자 메시지를 받고, ChatService를 통해 응답을 생성
  - 결과는 JSON 형태로 반환
 
- ChatService.java
  - 사용자 메시지를 입력받아 응답 메시지를 생성하는 핵심 서비스 클래스
  - 현재는 단순한 문자열 조합 기반 응답을 사용
  - 추후 GPT API, KoGPT 등 AI 챗봇 연동으로 확장 가능
 
- ChatData.java
  - 메시지를 표현하는 데이터 클래스
  - 메시지의 type (user/system)과 message 본문 필드를 포함
