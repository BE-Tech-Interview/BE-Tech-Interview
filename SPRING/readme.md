<!-- Filter와 Interceptor의 차이에 대해서 설명해주세요. -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>Filter와 Interceptor의 차이에 대해 설명해주세요.</strong></span></summary>
<hr>
Filter는 Java가 지원하는 기술로, Spring Context 외부에서 동작하며 Dispatcher Servlet에 요청이 전달되기 전/후에 url 패턴에 맞는 모든 요청에 대해 부가 작업을 처리할 수 있도록 합니다. Dispatch Servlet 이전에 WAS 내에서 Application Context에 등록된 필터가 실행됩니다.
<br></br>
Interceptor는 Spring이 제공하는 기술로써, Spring Context 내부에서 동작하며 Dispatcher Servlet이 Controller를 호출하기 전 / 후에 인터셉터가 끼어들어 요청과 응답을 참조하거나 가공할 수 있는 기능을 제공합니다.
<br></br>

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>번외</strong></span></summary>
    <img src="./images/filter-vs-interceptor.png">

    필터는 전후처리를 doFilter로 공통적으로 처리합니다.

    인터셉터는 preHanlde()과 postHandle() 메소드로 분기가 명확하게 나누어져 있습니다.

    [작동 순서]
    Servlet Request ➡ doFilter ➡ Dispatch Servlet ➡ preHandler ➡ Controller ➡ Service

    Service ➡ Controller ➡ postHandler ➡ Dispatch Servlet ➡ doFilter ➡ Servlet Response

  </details>
<hr>
</details>

<!-- Spring Bean Scope의 종류와 각각의 범위에 대해서 설명해주세요. -->
<details>
  <summary><span style="border-bottom:0.05em solid"><strong>Spring Bean Scope의 종류와 각각의 범위에 대해서 설명해주세요.</strong></span></summary>
<hr>

**Spring Bean의 Scope는 빈이 존재할 수 있는 생명 주기(범위)를 뜻하며,**<br>
**Singleton, Prototype, Request, Session, Application, Websocket 등이 있습니다.**

**Singleton은** 기본값으로 스프링 컨테이너의 시작과 종료까지 **단 하나의 객체만** 생성됩니다.<br>
**Prototype은** 빈의 생성부터 의존관계 주입까지만 관여하며 스프링 컨테이너에게 빈을 요청할 때마다 매번 새로운 객체가 생성됩니다.<br>
**Request는** 요청이 들어와서 나갈때까지 각각의 HTTP Request마다 **단 하나의 객체만** 생성됩니다.<br>
**Session은** HTTP Session과 동일한 생명주기를 가지며 각 세션당 **단 하나의 객체만** 생성됩니다.<br>
**Application은** ServletContext와 동일한 생명주기를 가지며 각 Application당 **단 하나의 객체만** 생성됩니다.<br>
**WebSocket은** WebSocket과 동일한 생명주기를 가지며 각 WebSocket당 **단 하나의 객체만** 생성됩니다.<br>

<br>

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>IoC(Inversion of Control)</strong></span></summary>

**IoC(Inversion of Control)란** "제어의 역전" 이라는 의미로 <br>
**메소드나 객체의 호출작업을 개발자가 직접 하는 것이 아니라, 외부에서 대신하는 것을 말합니다.**

IoC는 제어의 역전이라고 말하며, 간단히 말해 "제어의 흐름을 바꾼다"라고 합니다.
**객체의 의존성을 역전시켜 객체 간의 결합도를 줄이고 유연한 코드를 작성할 수 있게 하여**
**가독성 및 테스트, 코드 중복, 유지 보수를 편하게 할 수 있게 합니다.**

  </details>

<hr>
</details>
