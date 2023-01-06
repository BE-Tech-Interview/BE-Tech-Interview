<details>
  <summary><span style="border-bottom:0.05em solid"><strong>데이터베이스에서 인덱스를 사용하는 이유 및 장단점에 대해 설명해주세요.</strong></span></summary>
<hr>
데이터베이스에서 인덱스를 사용하는 이유는 검색 성능을 향상시키기 위함입니다.

조회 속도가 빠르다는 장점이 있지만,
정렬된 상태를 계속 유지시켜줘야하기 때문에 데이터를 삽입, 수정, 삭제 시에 성능 저하가 발생할 수 있습니다.
또한, 인덱스를 관리하기 위해서는 데이터베이스에 추가적인 저장 공간이 필요합니다.
<br></br>

  <details>
    <summary><span style="border-bottom:0.05em solid"><strong>인덱스를 사용하면 좋은 경우</strong></span></summary>
    
    (1) 규모가 작지 않은 테이블에서

    (2) INSERT / UPDATE / DELETE가 자주 발생하지 않는 컬럼,

    (3) 혹은 JOIN / WHERE / ORDER BY에 자주 사용되는 컬럼,

    (4) 혹은 데이터의 중복도가 낮은 컬럼

  </details>
  <details>
    <summary><span style="border-bottom:0.05em solid"><strong>인덱스 테이블</strong></span></summary>
    B+Tree 형식으로 정렬되어 있는 INDEX 테이블을 이용하여 조회 속도를 향상시킬 수 있습니다.

    🔎 밸런스 트리(Balanced Tree)란?
    트리의 노드가 한 방향으로 쏠리지 않도록,
    노드 삽입 및 삭제 시 특정 규칙에 맞게 재정렬되어 왼쪽과
    오른쪽 자식 양쪽 수의 밸런스를 유지하는 트리이다.

    항상 양쪽 자식의 밸런스를 유지하므로,
    무조건 O(logN)의 시간 복잡도를 가지게 된다.

    하지만, 노드 삽입 및 삭제 시 발생하는 재정렬 작업 때문에
    탐색을 제외한 작업에서는 일반 Tree보다 성능이 좋지 않다.

  </details>
<hr>
</details>

<details>
  <summary><span style="border-bottom:0.05em solid"><strong>트랜젝션에 대해 설명해주세요.</strong></span></summary>
<hr>
트랜잭션이란 데이터베이스의 상태를 변화시키는 하나의 논리적인 작업 단위입니다.
원자성, 일관성, 독립성, 지속성의 특징을 가지고 있습니다.
<br></br>

  <details>
    <summary><span style="border-bottom:0.05em solid"><strong>트랜젝션의 4가지 특징</strong></span></summary>
  
    [원자성] A(Atomic)
    원자성은 Transaction을 구성하는 연산들이 모두 정상적으로 실행되거나 하나도 실행되지 않아야 한다는
    all-or-nothing방식을 의미합니다. 수행중에 한작업이라도 실패하면 전부를 rollback하고 모두 성공해야 commit합니다.
    [일관성] C(Consistency)
    Transaction이 성공적으로 수행된 후에도 데이터베이스가 일관된 상태를 유지해야 함을 의미합니다.
    Transaction이 수행되는 과정에서는 일관되지 않을 수 있어도 Transaction이 완료되면 데이터베이스가 일관된 상태를 유지해야됨을 의미합니다.
    [격리성] I(Isolation)
    현재 수행 중인 Transaction이 완료될 때까지 Transaction이 생성한 중간 연산 결과에 다른 Transaction들이 접근할 수 없음을 의미합니다.
    [지속성] D(Durability)
    데이터베이스에 반영한 수행결과는 어떠한 경우에도 손실되지 않고 영구적이어야 함을 의미합니다.
    시스템 장애가 발생하더라도 Transaction작업 결과는 없어지지 않고 데이터베이스에 그대로 남아있어야 한다는 의미입니다.
    장애 발생시 데이터베이스를 원상태로 복구하기 위함입니다.

  </details>
<hr>
</details>
