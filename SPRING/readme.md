<details>
  <summary><span style="border-bottom:0.05em solid"><strong>Filter와 Interceptor의 차이에 대해 설명해주세요.</strong></span></summary>
<hr>
Filter는 Java가 지원하는 기술로, Spring Context 외부에서 동작하며 Dispatcher Servlet에 요청이 전달되기 전/후에 url 패턴에 맞는 모든 요청에 대해 부가 작업을 처리할 수 있도록 합니다. Dispatch Servlet 이전에 WAS 내에서 Application Context에 등록된 필터가 실행됩니다.
<br></br>
Interceptor는 Spring이 제공하는 기술로써, Spring Context 내부에서 동작하며 Dispatcher Servlet이 Controller를 호출하기 전 / 후에 인터셉터가 끼어들어 요청과 응답을 참조하거나 가공할 수 있는 기능을 제공합니다.
<br></br>

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>번외</strong></span></summary>
    <img src="https://velog.velcdn.com/images/soyeon207/post/ad97e02f-4023-4b9c-87b2-7b73474094da/image.png">

    필터는 전후처리를 doFilter로 공통적으로 처리합니다.

    인터셉터는 preHanlde()과 postHandle() 메소드로 분기가 명확하게 나누어져 있습니다.

    [작동 순서]
    Servlet Request ➡ doFilter ➡ Dispatch Servlet ➡ preHandler ➡ Controller ➡ Service

    Service ➡ Controller ➡ postHandler ➡ Dispatch Servlet ➡ doFilter ➡ Servlet Response

  </details>
<hr>
</details>
