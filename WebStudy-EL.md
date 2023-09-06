## JSP의 EL(Expression Language)

### **1. EL 사용의 이유**
JSP에서는 초기에 Java 코드를 직접적으로 스크립트릿 형식으로 삽입하여 사용하였습니다. 그러나 이러한 방식은 다음과 같은 문제점이 있었습니다:

- 코드와 프레젠테이션의 혼합으로 가독성 저하
- 유지보수의 어려움
- 코드의 재사용성 저하

이를 해결하기 위해 EL(Expression Language)가 도입되었으며, EL을 사용하면:

- 코드와 프레젠테이션을 분리하여 가독성 향상
- 코드의 간결성과 효율성 향상
- 객체의 속성에 쉽게 접근 가능

### **2. EL의 도입 버전**
EL은 JSP 2.0부터 공식적으로 지원되기 시작했습니다.

### **3. EL의 사용 방법**

```jsp
<%@ page isELIgnored="false" %>
```

EL은 `${...}` 형식으로 데이터를 참조하거나 표현하는 데 사용됩니다.

**기본 문법:**

- `${expression}`: 값을 평가하고 출력
- `.` 또는 `[]`: 객체의 속성에 접근

**예제:**

- **기본 사용법**
  ```jsp
  ${userName}
  ```

- **배열 또는 리스트 접근**
  ```jsp
  ${userList[0].name}
  ```

- **맵(Map) 접근**
  ```jsp
  ${userMap["key"].name}
  ```

## JSTL (JSP Standard Tag Library)

### **1. 개요**
JSTL은 JSP의 기능을 향상시키기 위해 도입된 태그 라이브러리입니다. JSP 1.2와 함께 도입되었으며, 2002년에 JSTL 1.0이 처음 발표되었습니다. 이 라이브러리를 사용하면 JSP 페이지에서 자바 코드를 직접 작성하지 않고, 태그를 사용하여 일반적인 작업을 수행할 수 있습니다. 이로 인해 코드의 가독성이 향상되고, 유지 관리가 더 쉬워집니다.

### **2. 사용 방법**

**태그 라이브러리 선언:**
```jsp
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
```

#### **주요 태그와 예제**

- **c:forEach** - 반복 처리
  ```jsp
  <c:forEach var="item" items="${list}">
      <p>${item}</p>
  </c:forEach>
  ```

- **c:if** - 조건 처리
  ```jsp
  <c:if test="${user.loggedIn}">
      <p>로그인 되었습니다.</p>
  </c:if>
  ```

- **c:set** - 변수 설정
  ```jsp
  <c:set var="userName" value="${user.name}" />
  ```

- **c:choose, c:when, c:otherwise** - 다중 조건 처리
  ```jsp
  <c:choose>
      <c:when test="${score >= 90}">
          <p>A 등급</p>
      </c:when>
      <c:when test="${score >= 80}">
          <p>B 등급</p>
      </c:when>
      <c:otherwise>
          <p>C 등급</p>
      </c:otherwise>
  </c:choose>
  ```

### **3. EL(Expression Language)과의 연계**
EL과 JSTL은 함께 사용되어 JSP 페이지의 로직을 더욱 간결하고 효과적으로 만들어줍니다. EL은 `${...}` 형태로 표현되며, 데이터를 참조하거나 표현하는 데 사용됩니다.

---
