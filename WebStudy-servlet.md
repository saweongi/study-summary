# Java Servlet 생성 및 주요 메서드

Java Servlet은 Java EE 스펙의 일부로, 클라이언트의 요청을 처리하고 동적으로 웹 페이지를 생성하는 서버측 프로그램입니다.

## Servlet 생성

Servlet 클래스를 생성하기 위해서는 `javax.servlet.http.HttpServlet` 클래스를 상속받아야 합니다. 그리고 웹 서버에 해당 Servlet을 매핑하기 위해 `@WebServlet` 어노테이션을 사용할 수 있습니다.

```java
import javax.servlet.*;
import javax.servlet.http.*;

@WebServlet("/main")
public class MyServlet extends HttpServlet {
  // 메서드 구현
}
```

## 주요 메서드

### service()

- 클라이언트의 요청을 받아 처리하고 응답을 반환합니다.
- `doGet()` 또는 `doPost()` 등의 메서드를 내부적으로 호출합니다.

### doGet(), doPost()

- HTTP GET 또는 POST 요청을 처리합니다.
- 일반적으로 이 메서드들을 오버라이딩하여 사용자의 요청을 처리합니다.

```java
protected void doGet(HttpServletRequest request, HttpServletResponse response) {
  // 로직
}

protected void doPost(HttpServletRequest request, HttpServletResponse response) {
  // 로직
}
```

### init(), destroy()

- `init()` 메서드는 Servlet이 처음 초기화될 때 호출됩니다.
- `destroy()` 메서드는 Servlet이 종료될 때 호출됩니다.

## @WebServlet("/main")

- 이 어노테이션은 URL 패턴(`/main`)을 해당 Servlet에 매핑합니다.

## Request Encoding

- 요청 데이터의 문자 인코딩을 설정합니다.
  
```java
request.setCharacterEncoding("UTF-8");
```

## Response Encoding

- 응답 데이터의 문자 인코딩을 설정합니다.
  
```java
response.setContentType("text/html; charset=UTF-8");
```

## PrintStream

- `PrintStream`은 바이트 출력 스트림을 텍스트 데이터를 출력할 수 있는 스트림으로 변환해 줍니다.
- Servlet에서는 주로 `PrintWriter`를 사용하여 응답을 작성하게 됩니다, `PrintStream`은 일반적으로 파일이나 콘솔 출력에 더 자주 사용됩니다.

```java
PrintWriter out = response.getWriter();
out.println("<h1>Hello World!</h1>");
```

### 주의사항

- 인코딩 설정은 파라미터 읽기 또는 응답 쓰기 전에 이루어져야 합니다.
- Servlet 생명주기를 정확하게 이해하고 `init()`와 `destroy()` 메서드를 적절히 사용해야 합니다.

이러한 기능과 메서드들은 Servlet 프로그래밍의 기초를 이루며, 이를 통해 동적인 웹 애플리케이션을 구축할 수 있습니다.
