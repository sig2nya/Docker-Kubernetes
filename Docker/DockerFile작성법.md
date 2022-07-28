* 출처 : https://velog.io/@ckstn0777/%EB%8F%84%EC%BB%A4%ED%8C%8C%EC%9D%BCDockerfile

Docker File
===========
* 개요 : 도커 이미지는 단순히 공식 허브에서 받을 수도 있다. 
하지만, 서버를 구축하여 애플리케이션을 배포하는 과정에서 필요한 패키지나 환경 설정 등을 반복해야하는 일이 생긴다면 번거로울 수 있다.
이러한 번거로운 작업을 줄이기 위해 Docker File을 이용하여 도커에게 시킬 수 있다.
<b>즉, Docker File 작성을 통하여 컨테이너에 필요한 패키지 / 소스 / 명령어 / 환경변수 설정 등을 시킬 수 있다.</b> 
따라서, 애플리케이션 빌드 및 배포와 환경구축을 자동화 할 수 있으며 이를 통해 컨테이너 오케스트레이션(Kubernetes 등)까지 가능할 것으로 생각된다.
* 요약 : DockerFile을 잘 작성하면 Container Orchestration이 가능할 것이다.

Docker File 작성
================
* 참조한 블로그는 VSCode를 사용하였지만, 나는 걍 Ubuntu WSL 18.04에서 진행.
```shell
FROM ubuntu:18.04 // 생성할 IMAGE의 BASE. ubuntu를 이용한 컨테이너 생성.
LABLE "purpose"="test" // 컨테이너에 대한 메타데이터

RUN apt-get update // container 내에서 apt-get update 수행
RUN apt-get install apache2 -y // 및 apache2 서버 install

ADD test.html /var/www/html // host에서 작성된 dockerfile과 같은 디렉토리의 test.html 파일을 이미지의 /var/www/html에 추가

// 작업공간 이동(=cd)
WORKDIR /var/www/html // /var/www/html 디렉토리로 이동

RUN ["/bin/bash", "-c", "echo hello > test2.html"] // 이미지에서 해당 명령어 수행

EXPOSE 80 // 80 port EXPOSE

CMD apachectl -DFOREGOUND
```

```
 > FROM : 생성할 이미지의 ORIGIN. 반드시 한번 이상 입력
 > LABEL : 이미지에 메타데이터를 추가.
 > RUN : 이미지 생성을 위한 '컨테이너 내부에서 실행될 명령어' / -y 옵션 권장.(RUN 명령어 실행시에 따로 CLI 이용이 불가능)
 > ADD : 파일을 해당 이미지에 추가. 즉, 위의 예제를 참고하면, ADD test.html /var/ww/html 명령이 해당 이미지에서 실행되며,
         DOCKERFILE이 위치한 디렉토리에서 test.html 파일을 가져와 이미지의 /var/www/html 디렉토리에 추가
 > WORKDIR : 명령어를 실행할 디렉토리. bash shell의 cd와 동일한 기능을 수행
 > EXPOSE : 이미지에서 노출할 포트를 설정
 > CMD : 컨테이너가 시작될 때마다 실행할 명령어. DOCKERFILE에서 한번만 사용 가능.
```

* 실습
* 1) \> mkdir dockerfile</br>
  ![image](https://user-images.githubusercontent.com/70207093/181397237-b26017f1-9f99-4a2f-a923-7a48d58c1582.png)
  
* 2) \> echo test >> test.html</br>
  ![image](https://user-images.githubusercontent.com/70207093/181397330-cf727d7d-d045-4dba-a101-787b2afd0321.png)
  
* 3) 도커파일 작성 : \> vi Dockerfile</br>
  ![image](https://user-images.githubusercontent.com/70207093/181397573-2aa22435-3b26-4df6-996e-66108c9ad19d.png)
  
* 4) 도커파일 빌드 : \> docker build -t <생성할 이미지명>:<태그명> <dockerfild 위치>
  ![image](https://user-images.githubusercontent.com/70207093/181397951-32434487-a6cf-4b15-928d-4cc7c9bac6af.png)
* * 위 사진을 확인해보면, Dockerfile에서 작성한 명령어가 잘 실행되는 것을 확인 가능.

* 5) 이미지 생성 확인</br>
  ![image](https://user-images.githubusercontent.com/70207093/181398324-8a410260-6830-498f-bd98-33a0b84a392d.png)
