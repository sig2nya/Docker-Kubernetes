Pod(파드)
========
* 개요 : Pod란 쿠버네티스에서 생성하고 관리할 수 있는 배포 가능한 가장 작은 컴퓨팅 단위. 하나 이상의 컨테이너 그룹. Pod는 네트워크 및 스토리지를 공유하며 해당 컨테이너를 구동하는 방법에 대한 명세를 수행
* 파드의 사용 : 아래는 nginx를 이미지를 실행하는 컨테이너로 구성된 pod의 예시. 
```javascript
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```
* 위와 같이 파드를 생성하려면, 다음과 같은 명령을 실행
```
kubectl apply -f https://k8s.io/examples/pods/simple-pod.yaml
```
