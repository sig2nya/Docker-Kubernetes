* 참조 : https://www.daleseo.com/docker-networks/

Docker Network
==============
* 개요 : 보통 Container는 격리된 환경이라고 한다. 
  그렇다면, Network 통신은? -> Docker에서 제공하는 Network를 통해 Container간 통신이 가능하다. Tomcat과 MySQL을 사용하여 통신 시키는 것이 목적.

* \> docker network ls : Docker network list 확인</br>
  ![image](https://user-images.githubusercontent.com/70207093/181404415-fcb20830-7975-460b-9be6-d552e043fb65.png)

Docker Network 종류
===================
* bridge : 호스트 컴퓨터 내에서 여러 컨테이너(게스트)들이 서로 통신
* host : 컨테이너를 호스트와 동일한 네트워크에 연결
* overlay : 여러 호스트에 분산된 컨테이너들이 서로 통신
