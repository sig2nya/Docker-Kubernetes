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

Docker Network Create
=====================
* 컨테이너의 네트워크 연결을 위해 Network 생성
* \> docker network create test</br>
  ![image](https://user-images.githubusercontent.com/70207093/181425782-0872fbd5-ec89-42a6-a2d1-63bd0b1c4a14.png)
* \> docker network inspect test : Containers 항목에 아무것도 없는 것을 확인</br>
  ![image](https://user-images.githubusercontent.com/70207093/181429165-b91ac846-4df8-4e5d-b945-ce760c8e0d1b.png)


Tomcat DockerFile
=================
![image](https://user-images.githubusercontent.com/70207093/181422394-248d6c4d-bbcd-4242-9f37-b9dc4b0f1cad.png)

> docker build -t ./ 명령어 수행 후 다음과 같이 tomcat이 구동된 것을 확인
> ![image](https://user-images.githubusercontent.com/70207093/181422815-a658703b-1b89-4cdd-a099-40d3204a966d.png)
 
Docker Network Connect
======================
* \> docker network connect test [Container] : Container 실행 후, 해당 Container를 network에 connect
  ![image](https://user-images.githubusercontent.com/70207093/181429401-64b33f53-270a-41b4-8a35-9bead594f0c2.png)
* \> docker exec friendly_kowalevski ping mysql : 마찬가지로, 다른 컨테이너도 해당 네트워크에 연결 및 명령어 수행</br>
  ![image](https://user-images.githubusercontent.com/70207093/181430320-9cb85d86-e92a-4967-b790-78e9c5c4ee07.png)
