<details>
  <summary><span
 style="border-bottom:0.05em solid"><strong>네트워크 토폴리지의 개념과 종류</strong></span></summary>
  <hr>
  <img src="https://user-images.githubusercontent.com/104713339/210579163-9bda4bb4-f281-4df4-9856-c3c77ff29c41.png">

네트워크 토폴리지: 네트워크에 배치된 노드와 링크의 연결 형태를 의미합니다.
<br>

### 참고용어

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>노드</strong></span></summary>
서버, 라우터, 스위치 등 네트워크 장치를 의미합니다.
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>링크</strong></span></summary>
유선 또는 무선을 의미합니다.
</details>

---

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>버스 토폴로지</strong></span></summary>
  
중앙 통신 회선 하나에 여러 개의 노드가 연결되어 공유하는 네트워크 구성을 갖습니다. 주로 LAN에서 사용합니다.

---

### 장점

- 노드 추가와 삭제가 쉽고 설치 비용이 적습니다.
- 한 노드에 장애가 발생 해도 다른 노드에 영향을 미치지 않습니다.

### 단점

- 가운데 메인 링크에 많은 트래픽이 몰리면 정체현상이 발생하고 패킷 손실율이 높을 수 있습니다.
- 메인 링크에 장애가 발생 시 모든 노드에 영향을 미칠 수 있습니다.
- 스푸핑의 위험이 있습니다.
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>스타 토폴로지</strong></span></summary>

중앙에 있는 노드 하나에 다른 모든 노드가 연결된 형태입니다.
다른 노드로 가려면 반드시 거쳐야 하는 중앙 노드는 특히 보안이 강화되어 있습니다.

---

### 장점

- 중앙의 메인 노드에 장애가 발생해도 다른 노드에 영향을 미치지 않습니다.
- 한 노드에 침해가 발생해도 다른 노드에 접근하기 어렵기 때문에 비교적 안정성이 높습니다.

### 단점

- 중앙 노드에 장애가 발생 시 전체 네트워크를 사용할 수 없습니다.
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>트리 토폴로지</strong></span></summary>

계층형 토폴로지라고도 불립니다.
트리 형태를 갖기 때문에 리프 노드를 기반으로 한 노드 추가, 삭제는 쉬우나 그 이외에는 어렵습니다.

---

### 장점

- 리프 노드에서의 확장과 삭제가 용이합니다.

### 단점

- 루트 노드에 문제가 생기면 전체 노드에 영향을 미칠 수 있습니다.
- 특정 노드에 트래픽이 집중될 시 그 하위 노드에 영향을 미칩니다.
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>링형 토폴로지</strong></span></summary>

고리 모양으로 연결된 형태입니다.

---

### 장점

- 노드 수가 많아져도 데이터 손실이 없습니다.
- 노드를 거치면서 토큰을 기반으로 통신권한 여부를 따지고 권한이 없는 노드는 데이터를 전달 받지 않습니다.

### 단점

- 링크 혹은 노드 중 한 곳에만 에러가 발생해도 전체 네트워크에 영향을 미칩니다.
- 기본적으로 토큰을 기반으로 하기 때문에, 토큰이 없는 노드는 통신에 참여를 못합니다.
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>메시 토폴로지</strong></span></summary>

노드가 서로 연결된 그물망 형태를 갖습니다.
Full 메시 토폴리지와 Partial 메시 토폴리지가 있으며, Full은 모든 노드가 서로 연결된 형태, Partial은 부분적으로 노드들이 연결된 형태를 말합니다.
일반적으로 메시토폴리지라 함은 Full 형태를 말하며, Full의 특징을 기술하겠습니다.
(참고: Full의 경우 n \* (n - 1) / 2의 회선이 필요합니다.)

---

### 장점

- 한 노드 혹은 회선에 장애가 발생해도 다른 여러 개의 경로가 존재하므로 계속해서 네트워크를 사ㅏ용할 수 있습니다.
- 회선이 많기 때문에 트래픽 분산 처리에 용이합니다.

### 단점

- 모든 노드가 연결되어 있어 노드 추가, 삭제가 가장 어렵습니다.
  - 노드를 삭제 시 그와 연결 된 모든 노드와의 링크를 삭제해야 합니다.
  - 노드를 추가 시 다른 모든 노드와 링크를 연결해줘야 합니다.
- 회선이 많아 구축 비용이 고가입니다.
</details>

</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>CORS</strong></span></summary>
<hr>
Cross Origin Resource Sharing(교차 출처 자원 공유)의 약자로
다른 출처에서 리소스를 가져오는 것을 제한하는 동일 출처 정책(SOP)과 반대로, 추가 HTTP 헤더를 사용하여
다른 출처에 있는 자원에 접근할 수 있는 권한을 부여하도록 브라우저에 알려주는 체제입니다. 
<br></br>

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>SOP(Same-Origin-Policy)란?</strong></span></summary>
    동일출처정책이라는 의미로, 어떤 출처에서 불러온 문서나 스크립트가 다른 출처에서 가져온 리소스와 상호작용하는 것을 제안하는 보안 방식입니다.
  </details>
<hr>
</details>
