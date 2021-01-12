# Stateful 과 Stateless 서버

Created: 2021년 1월 6일 오후 10:41

유저간의 인터렉션은 없지만, 상대방의 플레이가 내 화면에 보일 수 있게끔 구현하는것

[http://post.procademy.co.kr/archives/624](http://post.procademy.co.kr/archives/624)

- Stateful :  이전의 클라이언트 - 서버간의 트랜잭션을 저장한다. 즉 서비스간 작업 처리의 상태가 항상 공유되고 있는 상태. → TCP/IP 소켓 통신
- Stateless : 통신이 끝나면 그  상태를 유지하지 않는 특징
    - 연결을 끊는 순간 클라이언트와 서버의 통신이 끝나며, 상태 정보는 유지하지 않는다.
    - server의 응답이 client와의 세션 '상태'와 독립적
    - HTTP 통신