* Docker Setting Reference
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
![image](https://user-images.githubusercontent.com/70207093/182288607-3c1a7cfc-066b-43ed-b18e-26af8268a511.png)

1) 전통적인 애플리케이션의 배포 : 초기 조직은 애플리케이션을 물리 서버에서 실행했었다. 한 물리 서버에서 여러 애플리케이션의 리소스 한계를 정의할 방법이 없었기에, 리소스 할당의 문제가 발생했다. 예를 들어 물리 서버 하나에서 여러 애플리케이션을 실행하면, 리소스 전부를 차지하는 애플리케이션 인스턴스가 있을 수 있고, 결과적으로는 다른 애플리케이션의 성능이 저하될 수 있었다. 이에 대한 해결책은 서로 다른 여러 물리 서버에서 각 애플리케이션을 실행하는 것이 있다. 그러나 이는 리소스가 충분히 활용되지 않는다는 점에서 확장 가능하지 않았으므로, 물리 서버를 많이 유지하기 위해서 조직에게 많은 비용이 들었다.
