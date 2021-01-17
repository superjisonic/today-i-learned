# Docker 란?

> 컨테이너 기반의 오픈소스 가상화 플랫폼

## 도커 컨테이너

**컨테이너** : 무역에서 나온 단어로, 배에 실을 화물의 운송 단위를 규격화 한것이다.
포워더(브로커)들이 다양한 소스의 화물들을 한 컨테이너에 모아서 보내기도 한다

**도커 컨테이너** : 다양한 프로그램, 실행환경을 컨테이너로 추상화하고 동일한 인터페이스를 제공해준다.

### 가상화 기술

도커 컨테이너는 격리된 공간에서 프로세스가 동작하는 가상화 기술

[**기존의 가상화 방식]** 
⇒ OS를 가상화 (ex. VMware, VirtualBox)
- 호스트 OS 위에 `게스트 OS 전체를 가상화` 하여 사용하는 방식
- 사용법이 간단함
- 여러가지 OS를 가상화 할 수 있다(윈도우에서 리눅스 돌리기.. 등)
***- 단점: 무겁고 느려서 운영환경에선 사용할 수 없음***

 

### 프로세스 격리방식, 즉 컨테이너의 등장

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/facf19b0-c090-4567-909f-ce83be475f65/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/facf19b0-c090-4567-909f-ce83be475f65/Untitled.png)

- 단순히 프로세스를 격리시키기 때문에 가볍고 빠르게 동작한다.
- CPU나 메모리는 딱 프로세스가 필요한 만큼만 추가로 사용 ⇒ 성능적으로 거의 손실이 없다.
- 하나의 서버에 여러개의 컨테이너를 실행하면 서로 영향을 미치지 않고 독립적으로 실행됨
    - 마치 가벼운 VM을 사용하는 느낌
    - 실행중인 컨테이너에 명령어 입력 및 yum, apt-get으로 패키지 설치가능
    - 여러개의 프로세스를 백그라운드로 실행할 수도 있다
    - CPU나 메모리 사용량 제한 가능
    - 호스트의 특정 포트와 연결하거나 호스트의 특정 디렉토리를 내부 디렉토리인 것처럼 사용할 수도 있다
- 새로운 컨테이너를 만드는 시간은 1-2초

> 사실 도커가 컨테이너 기술의 최초는 아니고, 리눅스 컨테이너(LXC), 솔라리스 존 등 다양한 기술이 있었음. 도커는 LXC기반으로 시작해서 자체적인 기술로 발전

## 도커 이미지(Image)란

도커 이미지 : 컨테이너 **실행에 필요한 파일과 설정 값을 포함**하고 있는것

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c5d8e016-5355-497d-acf1-6afa21bb1d09/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c5d8e016-5355-497d-acf1-6afa21bb1d09/Untitled.png)

### 특징

- 상태값을 가지지않음
- 불변성 (Immutable)
- 컨테이너와의 관계
    - 컨테이너는 이미지를 실행한 상태라고 볼 수 있다
    - 추가되거나 변하는 값은 컨테이너에 저장됨
    - 같은 이미지에서 **여러개의 컨테이너**를 생성할 수 있다
    - 컨테이너의 상태가 변경되거나 삭제되어도 이미지는 변하지 않고 그대로 남아있다.

### 예시

- Gitlab 이미지
    - CentOS 기반
    - ruby, go, redis, gitlab source, nginx등을 갖고 있다
- MySQL 이미지
    - Debian기반
    - MySQL 실행하는데 필요한 파일과 실행 명령어, 포트정보 가지고 있음

### 관리

도커이미지는 `도커 허브에 등록`하거나 Docker Registry 저장소를 직접 만들어 관리할 수 있다.

출처
[https://subicura.com/2017/01/19/docker-guide-for-beginners-1.html](https://subicura.com/2017/01/19/docker-guide-for-beginners-1.html)
