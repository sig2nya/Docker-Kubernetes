* 참조 : https://kubernetes.io/ko/docs/tasks/tools/install-kubectl-linux/

Installation Kubernetes in Ubuntu 18.04 WSL2
============================================
> 1) curl을 이용하여 kubectl 바이너리 설치 : curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
![image](https://user-images.githubusercontent.com/70207093/183565441-b286d0f9-d9cb-45b7-ba34-c07c1083c267.png)
> 2) 바이너리 검증을 위한 파일 다운 : curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
![image](https://user-images.githubusercontent.com/70207093/183565599-d02e74fa-4d67-4475-af0d-76af45123ab4.png)
> 3) 체크섬 검증 : echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
![image](https://user-images.githubusercontent.com/70207093/183565684-60d1b35d-9406-481a-bc5c-96bdc33c1509.png)
> 4) kubectl 다운로드 및 version 확인 : sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl / kubectl version --client
![image](https://user-images.githubusercontent.com/70207093/183565892-2e647ce1-a0da-434d-9d2b-1f87cfea5b34.png)
> 5) 구글 클라우드 공개 샤이닝 키 다운로드 : sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
> 6) 쿠버네티스 apt 리포지토리 추가 : echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
> 7) 'apt-get update' 이후 'apt-get install -y kubectl'를 통하여 kubectl 설치
> 8) 클러스터 구축을 위한 minikube 설치 : curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 / sudo install minikube-linux-amd64 /usr/local/bin/minikube
![image](https://user-images.githubusercontent.com/70207093/183566865-44284c47-ec12-4b4a-ba93-4c46edd85447.png)
* * 도커가 설치되어 있지 않다면
![image](https://user-images.githubusercontent.com/70207093/183566995-d2617b78-ae62-42d1-8f93-1da8ee5ad0d5.png)
