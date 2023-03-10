<!-- 프로세스와 스레드의 차이점 -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>프로세스와 스레드의 차이점</strong></span></summary>
<hr>
프로세스는 운영체제로부터 자원을 할당 받는 작업의 단위를 말하며, 스레드는 이 프로세스로부터 자원을 할당 받아 실행하는 단위를 말합니다.
  
프로세스는 각각의 독립적인 객체로 기본적으로 메모리를 공유하지 않으며,<br>
스레드는 하나의 프로세스 안에서 Stack영역을 제외한 Code, Data, Heap 영역의 데이터를 공유합니다.
<hr>
</details>

<!-- 멀티 프로세스와 멀티 스레드의 차이점 -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>멀티 프로세스와 멀티 스레드의 차이점</strong></span></summary>
<hr>
멀티 프로세스란 하나의 응용 프로그램을 여러 개의 프로세스로 구성하여 각 프로세스가 하나의 작업을 처리하도록 하는 것입니다.

반면 멀티스레드는 하나의 응용 프로그램을 한 프로세스에 여러 개의 스레드로 구성하여 하나의 스레드가 하나의 작업을 처리하도록 하는 것입니다.

멀티 스레드는 하나의 프로세스 안에서 Stack영역을 제외한 메모리 공간을 공유하기 때문에
Context Switching에 있어서 멀티 프로세스보다 빠르다.

또한, 멀티 프로세스는 메모리 공유를 위해서는 IPC(프로세스간 통신)가 필요하고
프로세스를 생성할 때 드는 별도의 시스템 콜이 필요하기 때문에
멀티 스레드보다 사용되는 통신비용과 자원 사용량이 더 크다.
따라서, 멀티 프로세스 대신 멀티 스레드를 주로 사용한다.

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>번외</strong></span></summary>
    하지만 스레드는 메모리를 공유하고 있는 만큼
    멀티 스레드에서 같은 자원을 동시에 사용할 경우 동기화 문제가 발생할 수 있으며,
    하나의 스레드에서 오류가 발생하게 될 경우
    하나의 프로세스 안에 있는 모든 스레드에 영향을 미칠 수 있다.
    만일 데이터를 쓰고 수정하는 작업이 빈번한 상황이라면 동기화 기술을 많이 사용해야 하기 때문에 멀티프로세스를 고려해 볼 수도 있습니다.
  </details>
<hr>
</details>

<!-- 컨텍스트 스위칭이란 -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>컨텍스트 스위칭이란?</strong></span></summary>
<hr>
컨텍스트 스위칭은 CPU가 현재 작업중인 프로세스에서 다른 프로세스로 넘어갈 때 기존의 프로세스 상태를 PCB에 저장하고,
다음에 실행할 프로세스의 PCB 정보에서 주요 프로세스 상세 정보를 CPU에 업데이트한 후 해당 프로세스를 실행시킵니다.

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>번외</strong></span></summary>
컨텍스트 스위칭이 필요한 케이스

     1. 할당된 시간을 모두 사용하거나
     2. 인터럽트가 발생하여 CPU가 이를 처리해야 하거나
     3. 시스템 호출이 발생하여 사용자 모드 / 커널 모드의 전환이 수행될 때

PCB란?

    PCB는 프로세스 상태관리와 문맥교환을 위해 필요하며,
    프로세스를 제어하기 위해 프로세스의 상태 정보를 저장해놓는 곳이다.

  </details>
<hr>
</details>

<!-- 교착상태 -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>교착상태란?</strong></span></summary>
<hr>
교착 상태(dead lock)란 두 개 이상의 프로세스가 서로 상대방의 작업이 끝나기 만을 기다리고 있기 때문에 무한 대기에 빠지는 상태를 말합니다.

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>번외</strong></span></summary>
    
    ※ 데드락 발생 조건 4가지
      상호 배제: 자원은 한번에 한 프로세스만 사용 가능
      점유 대기: 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당된 자원을 사용하기 위해 대기하는 프로세스 존재
      비 선점: 한 프로세스에 할당된 자원은 사용이 끝날 때까지 강제로 빼앗을 수 없음
      순환 대기: 순환 형태로 자원을 대기하고 있는 프로세스의 집합
  </details>
<hr>
</details>

<!-- Thread Safe와 Thread Safe를 지키는 방법 -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>Thread Safe란 무엇이며, 스레드의 안전성을 지키는 방법에 대해 설명해주세요.</strong></span></summary>
<hr>
Thread Safe란,
멀티 스레드 환경에서 같은 공유 자원에 대해 동시에 접근이 이루어져도 데이터의 무결성이 지켜지고 정상적으로 동작하는 것을 의미합니다.

Thread Safe를 보장하는 방법으로는 Mutual Exclusion, Atomic Operation, Thread Local Stoarge, Re Entrancy, Immutable objects가 있습니다.

1. Mutual Exclusion: 공유 자원에 하나의 스레드만 접근할 수 있도록, 세마포어/뮤텍스로 락을 적용하는 방법

2. Atomic Operation: 공유자원에 원자적으로 접근하여 상호 배제를 구현하는 방법

3. Thread Local Storage : 스레드끼리 공유하는 힙, 데이터 영역의 자원 접근을 최소화하고, 각 스레드가 독립적으로 가지는 스택 영역의 자원만 사용하도록 설계하는 방법

4. Re Entrancy: 여러 스레드에서 동시에 가능하지만 각각의 스레드가 함수 내에서 공유 자원을 이용하지 않아 항상 정상적인 호출 결과를 얻는 방법

5. Immutable objects : 공유 자원 사용 시 불변 객체를 사용하여 객체 생성 이후에 값을 변경할 수 없도록 하는 방법
<hr>
</details>

<!-- Paging vs Segmentation -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>Paging과 Segmentation에 대해서 설명해주세요.</strong></span></summary>
<hr>

Paging과 Segmentaiton은 **가상 메모리 관리 기법**이며,
Paging은 **고정된 영역**의 페이지로 분할하여 물리 주소와 가상 주소를 관리하는 방식이고,
Segmentation은 **가변적인 영역**의 세그먼트로 분할하여 관리하는 방식입니다.
<br>

##### ※ 내부단편화(Paging) vs 외부단편화(Segmentation)

내부단편화는 고정된 메모리 블럭에 **사용되지 않고 남아있는 공간이 발생**하는 것을 의미하고,
외부단편화는 메모리 상에 남아 있는 **총 공간**은 할당 **요청한 공간보다 크지만**, 남아있는 **공간이 연속적이지 않아, 할당할 수 없는 경우**를 의미합니다.

##### ※ 페이지 테이블 vs 세그먼트 테이블

Paging은 페이지 번호에 할당된 프레임 번호를 기입하여 사용하고,
Segmentation은 세그먼트 번호에 할당된 세그먼트 주소와 변위값(길이)을 기입하여 사용합니다.

| Page Table                             | Segment Table                                |
| -------------------------------------- | -------------------------------------------- |
| ![Page Table](./images/page-table.png) | ![Segment Table](./images/segment-table.png) |

<hr>
</details>

<!-- 캐시의 지역성에 대해 설명해주세요. -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>캐시의 지역성에 대해 설명해주세요.</strong></span></summary>
<hr>

**캐시의 지역성**이란
Cache Hit를 늘리기 위해(Hit Rate를 높이기 위해)
어느 한 순간에 특정 부분을 집중적으로 참조하는 특성을 의미합니다.

**캐시의 지역성의 종류**에는<br>
최근에 참조된 주소의 내용이 곧바로 다시 참조되는 **시간 지역성**과<br>
실제 프로그램이 참조된 주소에서 인접하나 주소의 내용이 참조되는 **공간 지역성**이 있습니다.<br>

**[번외] - 캐시를 사용하는 이유 / 캐시의 성능**<br>
CPU 성능에 비해 상대적으로 느린 하드디스크나 SSD 같은 저장장치의 속도를 보완하기 위해 캐시를 사용합니다.<br>
비교적 작은 용량의 캐시에 담겨있는 정보에 CPU가 접근했을 때 Cache Hit가 발생하는 정도에 따라<br>
캐시의 성능이 결정됩니다.<br>

<hr>
</details>

<!-- 동기와 비동기 방식의 차이점에 대해 설명해주세요. -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>동기와 비동기 방식의 차이점에 대해 설명해주세요.</strong></span></summary>
<hr>

**동기(Synchronize)방식**은 메서드 리턴과 결과를 전달받는 시간이 일치하는 명령 실행 방식입니다.<br>또한 함수가 끝나는 시간과 바로 다음의 함수가 시작하는 시간이 같습니다. 설계가 간단하고 직관적이지만, 결과가 주어질 때까지 계속 대기해야한다는 단점이 있습니다.<br></br>
**비동기(Asynchronous)** 방식은 여러 개의 처리가 함께 실행되는 방식으로, 동기 방식에 비해 단위시간 당 많은 작업을 처리할 수 있습니다. 단, CPU나 메모리를 많이 사용하는 작업을 비동기로 처리하게 되면 과부하가 걸릴 수 있습니다. 프로그램의 복잡도도 증가하게 됩니다.

<hr>
</details>


<!-- 스택을 스레드마다 독립적으로 할당하는 이유는 무엇인가요? -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>스택을 스레드마다 독립적으로 할당하는 이유는 무엇인가요?</strong></span></summary>
<hr>

스택은 함수 호출시 전달되는 인자, 함수 내에서 선언되는 지역 변수등이 저장되는 메모리 공간입니다.

스택 메모리 공간이 독립적이라는 것은

독립적인 함수 호출이 가능함을 의미하고 이는 독립적인 실행 흐름이 추가된다는 것입니다.

따라서 스레드의 정의에 따라 독립적인 실행 흐름을 추가하기 위한 최소 조건으로 독립된 스택을 할당합니다.

<hr>
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>교착상태와 기아상태의 해결방법에 대해 설명해주세요.</strong></span></summary>
<hr>
교착상태는 서로 다른 프로세스가 서로 점유하고 있는 자원의 반납을 대기하고있는 상태를 의미합니다.
  
해결 방법으로는 발생조건을 사전에 예방하는 방법과 알고리즘을 데드락이 발생하지 않는 방향으로 작성하는 방법이 있습니다.
  
기아상태는 여러 프로세스가 부족한 자원을 점유하기 위해 경쟁할 때, 특정 프로세스가 영원히 자원을 할당받지 못하는 경우를 의미합니다.<br>
해결 방법으로는 우선순위를 수시로 변경하거나, 오래 기다린 프로세스의 우선순위를 높여주는 작업을 통해 해결할 수 있습니다.

**[정리]<br>**
※ 교착 상태 해결 방법
- 예방 : Dead Lock 발생 조건을 제거해줍니다. (상호배제 제거 / 점유대기 제거 / 비선점 제거 / 환형대기 제거)
- 회피 : 자원할당 알고리즘, 은행원 알고리즘을 사용해서 교착상태를 회피합니다.
- 교착 상태 탐지와 회복 : 교착 상태를 허용하되 탐지 알고리즘을 실행하여 교착 상태를 탐지하면 프로세스 종료 및 자원 선점을 통해 복구하도록 합니다.
- 무시 : 교착상태를 무시하고 특별한 조치를 취하지 않는 방법으로, 교착 상태를 주기적으로 탐지하거나 예방하기 위해서 필요한 오버 헤드보다 교착상태를 무시할 때 이득이 더 큰 경우에 사용합니다.<br>
  
※ 기아 상태를 해결방법
- 프로세스 우선순위를 수시로 변경하여 각 프로세스가 높은 우선순위를 가지도록 기회를 부여합니다.
- 오래 기다린 프로세스의 우선순위를 높이며
- 우선순위가 아닌 요청 순서대로 처리하는 요청 큐를 사용합니다.

<hr>
</details>
