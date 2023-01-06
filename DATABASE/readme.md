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
  </details>
<hr>
</details>
