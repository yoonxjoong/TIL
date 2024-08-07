# Cross-site-Scripting 공격

Cross-site-Scripting => xss 인 이유? css의 약어를 이미 사용중이라서.

### XSS 공격
  - 게시판, 웹 메일 등에 악성 스크립트 코드를 삽입 하여 개발자가 고려하지 않은 기능이 작동하게 하는 공격
  - 파일 변조를 이용하여 악성 스크립트 코드를 삽입 -> 서버 내에서 해당 스크립트를 실행하여 유포자가 원하는 동작을 하게 만들어 서버 PC를 공격

### Reflected XSS
  - URL 파라미터에 스크립트를 넣어 서버에 저장하지 않고 그 즉시 스크립트를 만드는 방식
  - 브라우저 자체에서 차단하는 경우가 많음

##### 공격 순서
  1. XSS 공격 스크립트 포함된 URL 노출
  2. 감연된 URL를 서버에 Request 전송
  3. 웹 서버에서 해당 스크립트를 포함한 Response 전송

### Stored XSS
  - 사이트 게시판, 댓글 등 스크립트가 서버에 저장되어 실행되는 방식
  - 일반적인 XSS 공격

##### 공격 순서
  1. XSS 공격 스크립트 포함된 게시글 포스팅
  2. 사용자에게 감염된 게시글 URL를 노출
  3. 사용자가 게시글을 확인함으로써 URL에 대한 요청을 서버에 전송
  4. 웹 서버에서 해당 스크립트를 포함한 Response 전송


### XSS 방지법
  - script 문자 필터링
    - 입력값에 대한 검증을 추가하여 서버 측에서 필터링을 해주어야함
    - <, >, ", ' 등의 특수 문자를 필터링
   
  - 특수 문자를 HTML Entity로 변환
