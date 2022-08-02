* Docker Setting References
* * https://gamechangers.tistory.com/103
* * https://louky0714.tistory.com/131

Docker-Kubernetes
=================
* 개요 : WSL2를 이용한 Docker 환경 구축(Window10) 및 Container Orchestration
* * 준비물 : Ubuntu WSL / PowerShell
* * 윈도우 위에서 Docker 구축이 정말 어렵다.

* Kubernetes Reference : https://kubernetes.io/ko/docs/concepts/overview/what-is-kubernetes/

Kubernetes의 개요
================
<img src='https://d33wubrfki0l68.cloudfront.net/26a177ede4d7b032362289c6fccd448fc4a91174/eb693/images/docs/container_evolution.svg'></src>

1) 전통적인 애플리케이션의 배포 : 과거에는 서버 한대 -> 애플리케이션 하나. 이는 리소스의 낭비가 심해지고, 애플리케이션 하나당 서버 한대를 증설해야 하는 문제가 생겼다. 즉, 비용의 문제가 발생하였다. 해당 문제 해결책으로, 가상화라는 기술이 도입되었다.
2) 가상화된 배포 : 하나의 물리 서버 CPU에서 여러 VM을 실행할 수 있게 한다. VM을 통해서 애플리케이션들의 격리가 어느정도 유지될 수 있엇으며, 일정 수준의 보안을 제공할 수 있었다. 또한, 애플리케이션 하나가 한대의 서버 자원만 사용하였기에, 자원 낭비가 존재하였지만 여러 애플리케이션이 해당 자원을 활용하면서 자원 활용을 극대화 시킬 수 있었다. 즉, 비용 절감 효과를 기대할 수 있다.
3) 컨테이너 개발 시대 : VM과 유사하지만, OS를 공유하기때문에 VM보다 가볍다. VM 이미지보다 가벼우며, CI/CD가 용이, 개발과 운영의 분리, 시스템 운영에 용이함 등의 장점을 가진다.
