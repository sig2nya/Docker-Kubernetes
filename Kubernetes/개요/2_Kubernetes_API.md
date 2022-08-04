쿠버네티스 API
==============
* 개요 : 쿠버네티스 컨트롤 플레인의 핵심은 API 서버. API 서버는 최종 사용자, 클러스터의 다른 부분, 외부 컴포넌트가 서로 통신할 수 있는 HTTP API를 제공. 
* 쿠버네티스의 API를 사용하여 오브젝트(pod, namespace, configmap, event)를 질의 및 조작.
* 대부분의 작업은 kubectl CLI 혹은 API를 사용하는 kubeadm 등을 수행 가능. REST 호출 사용을 통해 API에 직접 접근

OpenAPI 명세
============
* OpenAPI V2 : 쿠버네티스 API 서버는 /openapi/v2 엔드포인트를 통해 통합된 OpenAPI v2 스펙을 제공. 요청 헤더에 다음과 같이 기재하여 응답 형식 지정 가능.
<table>
  <thead>
    <tr><th>헤더</th><th style=min-width:50%>사용할 수 있는 값</th><th>참고</th></tr></thead><tbody><tr><td><code>Accept-Encoding</code></td><td><code>gzip</code></td><td><em>이 헤더를 제공하지 않는 것도 가능</em></td></tr><tr><td rowspan=5><code>Accept</code></td><td><code>application/com.github.proto-openapi.spec.v2@v1.0+protobuf</code></td><td><em>주로 클러스터 내부 용도로 사용</em></td></tr><tr><td><code>application/json</code></td><td><em>기본값</em></td></tr><tr><td><code>*</code></td><td><code>JSON으로 응답</em></td></tr></tbody></table>
