---

### Eclipse에서의 Dynamic Web Project 구조

Dynamic Web Project를 생성한 후에는 왼쪽의 Project Explorer 창에서 다음과 같이 생성된 폴더들을 확인할 수 있습니다. 
![설명1](https://github.com/leeapgil/study-summary/blob/master/img/web1.PNG)

#### 1) proj
- **설명**: 방금 생성한 프로젝트를 나타냅니다.

#### 2) Java Resources
- **설명**: 자바 전용 폴더입니다.
- **내용**: 자바 파일(.java)이 저장됩니다.

  ##### 2-1) src/main/java
  - **설명**: 이 폴더에 자바 파일들을 배치합니다. 해당 폴더 안에 있는 자바 파일만 컴파일을 수행합니다.
  - **참고**: `src` 폴더에서는 소스 컴파일을 수행하며, 실행은 `WebContent`에서 이루어집니다.

#### 3) WebContent (Eclipse IDE 2022 버전에서는 webAbb)
- **설명**: 이 폴더에는 JSP 파일이나 HTML 파일과 같이 컴파일이 필요 없는 파일들을 넣어줍니다.
- **내용**: `META-INF`와 `WEB-INF` 폴더가 들어있습니다.

#### 4) WEB-INF
- **설명**: 이 폴더 안에는 확장 라이브러리와 배포 서술자가 들어있습니다.
- **내용**: 확장 라이브러리를 위한 `lib` 폴더와 배포 서술자인 `web.xml` 파일이 들어있습니다.

#### 5) Servers
- **설명**: 설정을 마친 톰캣 서버가 들어있습니다.

---
### JSP (JavaServer Pages)의 주요 목적과 사용 예시

#### JSP의 주요 목적
- JSP는 웹 브라우저에 띄울 HTML 파일을 생성하는 것이 주된 목적입니다.
- 서블릿과의 차이: 서블릿은 UI 요소가 없으며, 제어나 기타 처리를 담당합니다.

#### JSP 예시 코드
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%!
String str1 = "JSP";
String str2 = "안녕하세요..";
%>
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Hello, JSP</title>
</head>
<body>
  <h2>처음 만들어보는 <%= str1 %></h2>
  <p>
    <%
    out.println(str2 + str1 + "입니다. 열공합시다! ^^");
    %>
  </p>
</body>
</html>
```

#### 추가된 요소들
- JSP 파일은 일반적인 HTML 파일에 몇 가지 요소가 추가되어 있습니다.
- 이 추가된 요소들은 크게 **지시어(Directives)**와 **스크립트 요소(Script Elements)**로 분류할 수 있습니다.

물론입니다! 다음은 Markdown 형식으로 정리한 내용입니다:

---

### 지시어 (Directive)에 대한 설명

#### 지시어의 역할
- 지시어는 JSP 페이지를 Java(서블릿) 코드로 변환하는데 필요한 정보를 JSP 엔진에 알려주는 역할을 합니다.
- 주로 스크립트 언어나 인코딩 방식 등을 설정합니다.

####  지시어의 기본 구문
```jsp
<%@ 지시어 종류 속성1="값1" 속성2="값2" ...%>
```

#### 지시어의 종류
- `page` 지시어
- `include` 지시어
- `taglib` 지시어

#### page 지시어
- 문서의 타입, 에러 페이지, MIME 타입 등을 설정합니다.

#### page 지시어의 속성들
##### language, contentType, pageEncoding 속성
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
```
- `language`: 스크립팅 언어를 지정합니다.
- `contentType`: 생성할 응답 문서의 MIME 타입을 지정합니다.
- `pageEncoding`: 인코딩을 지정합니다.

#####  import 속성
- 외부 클래스를 임포트하기 위해 사용합니다.

####  import 속성을 이용한 날짜 표시 페이지
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ page import="java.text.SimpleDateFormat" %> 
<%@ page import="java.util.Date" %> 
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Today is? | page 지시어 - import 속성 예제</title>
</head>
<body>
  <%
  Date today = new Date();
  SimpleDateFormat dateformat = new SimpleDateFormat("yyyy-MM-dd");
  String dateStr = dateformat.format(today);
  out.println("오늘 날짜 : " + dateStr);
  %>
</body>
</html>
```

- `SimpleDateFormat` 클래스와 `Date` 클래스를 임포트하여 오늘 날짜를 출력합니다.
- 이 클래스들은 `java.lang` 패키지에 속하지 않으므로, `import` 속성을 사용해야 합니다.

---

