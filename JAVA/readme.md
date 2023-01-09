<details>
  <summary><span style="border-bottom:0.05em solid"><strong>main 메서드를 override, overload 할 수 있는지</strong></span></summary>

  <hr>

main 메서드는 **override 할 수 없고, overload 할 수 있습니다.**

**main 메서드는 static으로 선언되며**, **static** 메서드는 **컴파일** 시에 어떤 메서드를 실행할지 결정됩니다.
**overriding** 메서드는 **런타임** 시에 어떤 메소드를 실행할지 객체 타입에 따라 결정되기 때문에 override 할 수 없습니다.
**overloading** 메서드는 **컴파일** 시에 어떤 메소드를 실행할지 결정되기 때문에 overload 할 수 있습니다.

static이 아닌 메서드를 static 메서드로 오버라이드 할 수 없습니다. 마찬가지로 컴파일 에러가 발생하게 됩니다.

  <details>
  <summary><span style="border-bottom:0.05em solid"><strong>Static으로 선언되었다면?</strong></span></summary>

객체는 Heap 영역에 할당되고, 객체 변수는 stack에 올라가 주소값을 가지고 있습니다.
하지만 static은 class 영역에 할당되기 때문에 가비지 컬렉터가 관여할 수 없습니다.
자세한 내용은 [JVM의 메모리 구조](https://codedragon.tistory.com/5297)를 참조하시기 바랍니다.

  </details>

  <hr>
</details>
<!-- 클래스는 무엇이고 객체는 무엇인가요? -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>클래스는 무엇이고 객체는 무엇인가요?</strong></span></summary>

  <hr>
  클래스는 객체지향 프로그래밍의 핵심 개념 중 하나로, 객체를 생성하기 위한 템플릿이며, 객체의 상태를 나타내는 필드와 객체의 행동을 나타내는 메소드로 구성되어있습니다.
  
  객체는 클래스에서 정의한 것을 토대로 메모리에 할당된 실체를 말하며, 수명주기동안 상태(필드)와 동작(메서드)를 가지고 다른 객체와 상호작용할 수 있습니다.
  <br></br>
  <details>
  <summary><span style="border-bottom:0.05em solid"><strong>클래스와 객체의 메모리</strong></span></summary>

객체는 클래스의 인스턴스로 메모리의 공간을 차지하여 필드에 상태를 저장하고 메서드로 동작을 표현합니다.

추가적으로 생성된 인스턴스들은 가비지 컬렉터에 의해 수집됩니다.
클래스는 인스턴스를 생성하기 전까지 파일 형태로 저장공간에 저장될 뿐 메모리의 힙 영역을 소모하지 않습니다.

  </details>

  <hr>
</details>
