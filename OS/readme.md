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

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>프로세스와 스레드의 차이점</strong></span></summary>
<hr>
프로세스는 운영체제로부터 자원을 할당 받는 작업의 단위를 말하며, 스레드는 이 프로세스로부터 자원을 할당 받아 실행하는 단위를 말합니다.
  
프로세스는 각각의 독립적인 객체로 기본적으로 메모리를 공유하지 않으며,<br>
스레드는 하나의 프로세스 안에서 Stack영역을 제외한 Code, Data, Heap 영역의 데이터를 공유합니다.
<hr>
</details>
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
