<details>
  <summary><span
 style="border-bottom:0.05em solid"><strong>네트워크 토폴리지의 개념과 종류</strong></span></summary>
  <hr>
  <img src="https://user-images.githubusercontent.com/104713339/210579163-9bda4bb4-f281-4df4-9856-c3c77ff29c41.png">

네트워크 토폴리지: 네트워크에 배치된 노드와 링크의 연결 형태를 의미합니다.
네트워크에서 가장 기본이 되는 내용으로, 토폴로지의 종류와 각 특징 등을 간단하게라도 이해하고 계시는걸 권장드립니다.
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
<hr>
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>CORS에 대해 설명해주세요.</strong></span></summary>
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

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>HTTP와 HTTPS의 차이점에 대해 설명해주세요.</strong></span></summary>
<hr>
HTTPS는 기존의 HTTP에 Secure Socket Layer 계층을 하나 더 두어
HTTP 통신에서는 수행하지 않았던 데이터의 암호화를 통해 보안을 한층 더 높인 통신 기법입니다.

<hr>
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>REST와 RESTful에 대해서 설명해주세요.</strong></span></summary>
<hr>

REST란
URI를 통해 자원을 명시하고,
METHOD를 통해 자원에 대한 CRUD Operation을 명시하는 방법으로
네트워크 상에서 Client와 Server사이의 통신 방식 중 하나입니다.

RESTful
REST의 원리를 따르며 REST API의 설계 규칙을 올바르게 지키는 것을 의미합니다.

<hr>
  <details>
    <summary><span style="border-bottom:0.05em solid"><strong>REST API 설계 규칙</strong></span></summary>
    
    1. /(구분자: 슬래쉬)는 계층 관계를 나타낼 때 사용합니다.
    2. URI의 마지막에는 /(구분자: 슬래쉬)를 사용하지 않습니다.
    3. -(하이픈)은 URI의 가독성을 높이는 데 사용합니다.
    4. _(언더바)는 URI에 사용하지 않습니다.
    5. URI경로에 대문자는 가급적 피합니다.
    6. 파일확장자는 URI에 포함시키지 않습니다.
    7. 리소스 간에 연관관계가 있는 경우에는 "/리소스명/{리소스ID}/연관관계가있는리소스명"으로 표현합니다.
  </details>
<hr>
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>네트워크 병목현상이 무엇인지 설명하고 개선할 수 있는 방법을 제시하세요.</strong></span></summary>
  <hr>

대량의 트래픽이 한곳에 몰려 데이터 흐름이 제한되는 상황을 말합니다.
메모리 용량을 늘리거나 서버-클라이언트 간 네트워크 회선을 네트워크 토폴리지에 기반해서 늘리는 방법 등이 있습니다.

추가질문: 네트워크 토폴리지가 무엇인가요? (네트워크 토폴리지 부분 참고) 
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>TCP/IP 계층과 OSI 7계층 간의 계층 구조 차이를 간단히 설명하세요.</strong></span></summary>
  <hr>
전체적인 역할은 같으나 계층의 세분화에서 약간 다릅니다.
TCP/IP 계층의 애플리케이션 계층은 OSI 7계층에서 애플리케이션, 프레젠테이션, 세션 계층으로 나뉩니다.
링크 계층은 OSI 7계층에서 데이터링크, 물리 계층으로 나뉘어서 TCP/IP는 총 4계층으로 구성되어 있습니다.
그 외 전송 계층과 인터넷 계층이 동일하게 하나씩 있습니다.
</details>


<details>
  <summary><span style="border-bottom:0.05em solid"><strong>HTTP가 무엇인지 말하고 HTTPS와의 차이를 설명하세요.</strong></span></summary>
  <hr>
클라이언트와 서버간에 데이터 요청/응답 시 사용되는 프로토콜입니다.
HTTP는 암호화 하지 않은 데이터를 전송하기 때문에 서버와 주고 받는 데이터를 볼수 있는 반면,
HTTPS는 암호화된 데이터를 전송하기 때문에 제 3자가 데이터를 볼 수 없습니다.
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>HTTPS의 암호화 방식을 알고 있나요?</strong></span></summary>
  <hr>
HTTP 요청이 오면 대칭키 또는 비대칭키 암호화 방식을 사용해 암호화 한 후에 응답 데이터를 보냅니다.

대칭키 암호화는 클라이언트와 서버가 동일한 키를 사용해 암호화/복호화를 하기 때문에 속도가 빠릅니다.
하지만 두 키중 하나만 노출돼도 복호화를 할 수 있어서 보안상 위험할 수 있습니다.

비대칭키 암호화는 비교적 느리지만 보다 안정적입니다.
공개키가 노출 되어도 개인키가 있어야만 복호화를 할 수 있기 때문입니다.
</details>

