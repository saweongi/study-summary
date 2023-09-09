STS 3.9.17 설치 
java 11 https://adoptium.net/temurin/releases/
시작전 ini 설정 

https://hermeslog.tistory.com/670

## STS (Spring Tool Suite)
STS는 Spring 기반 프로젝트의 개발에 최적화된 Eclipse 기반의 IDE입니다. STS는 Spring 프로젝트 개발을 쉽게 시작할 수 있게 해주며, 다양한 플러그인 및 툴들이 포함되어 있습니다.

### STS 설치 방법
1. [Spring Tool Suite 공식 다운로드 페이지](https://spring.io/tools)로 이동합니다.
2. 적절한 버전의 STS를 선택하여 다운로드 받습니다.
3. 다운로드 받은 파일을 실행하여 설치를 진행합니다.

---

## Maven
Maven은 프로젝트 관리 및 빌드 자동화 도구입니다. 의존성 관리, 라이프사이클 관리 등의 기능을 제공합니다.

### Maven 설치 방법
1. [Maven 공식 다운로드 페이지](https://maven.apache.org/download.cgi)로 이동합니다.
2. 적절한 버전의 Maven을 다운로드 받습니다.
3. 다운로드 받은 압축 파일을 원하는 경로에 압축 해제합니다.
4. 시스템 환경 변수에 Maven의 bin 폴더 경로를 추가합니다.

   ```markdown
   **환경 변수 설정**
   - `M2_HOME` : Maven이 압축 해제된 경로를 지정합니다.
   - `PATH` or `Path` : `%M2_HOME%\bin`을 추가합니다.
   ```

5. 설치가 완료되면, 터미널 혹은 명령 프롬프트에서 `mvn -v` 명령어로 설치를 확인합니다.

---

## Spring MVC 프로젝트 시작하기

STS를 사용하여 Spring MVC 프로젝트를 시작하는 방법은 다음과 같습니다.

1. STS를 실행합니다.
2. `File` > `New` > `Spring Starter Project`를 선택합니다.
3. 필요한 정보와 의존성(Dependencies)을 선택하여 프로젝트를 생성합니다.
4. 생성된 프로젝트에서 `src` 폴더 및 `pom.xml` 파일을 통해 프로젝트 구조와 의존성을 확인할 수 있습니다.

---

이렇게 STS와 Maven을 설정하면, Spring 기반의 웹 애플리케이션 개발을 쉽게 시작할 수 있습니다.
