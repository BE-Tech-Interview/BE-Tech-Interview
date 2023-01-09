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
