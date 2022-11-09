<h1> JSP </h1>

<h2> WWW(World Wide Web) </h2>

> <pre> www = 전 세계를 연결한 거미줄과 같은 인터넷 망에서의 정보 공유 </pre>
> 클라이언트 - 서버 구조로 이루어져 있음
> HTTP 프로토콜 사용
> <pre>웹 브라우저 = 웹 정보를 탐색하는 프로그램 
> 웹 서버 = 클라이언트의 요청에 응답을 하는 프로그램 
> 정적 웹 서비스 = 서버의 특정 폴더에 HTML이나 다양한 미디어의 자원 파일을 저장 
>                > 클라이언트 요청에 그대로 파일을 서비스함
> 동적 웹 서비스 = 같은 요청이라도 클라이언트에 따라 다른 결과의 서비스
> </pre>

<h2> 인터넷 프로그래밍 </h2>

> - VBSScript / JavaScript 두가지 언어가 존재
> <pre>
> CGI = 동적인 웹 구축을 위해 처음으로 개발된 프로그래밍 방식으로 일반적 언어 사용
> ASP = HTML 페이지에 VBScript의 소스를 내장한 프로그래밍 방식 
> PHP = C언어와 유사한 언어를 사용하며 적은 명령어로 가능한 프로그래밍 방식 
> JSP = 자바 기반의 서블릿을 먼저 개발해 CGI 대체 > 이를 활용하기 위해 개발한 프로그래밍 방식 </pre>
> - 플랫폼에 독립적인 기술 방식 , 웹 서버에서 실행 시 자바 모듈을 이해하는 자바 엔진 필요

<h2> 서블릿과 JSP 엔진 </h2>

> <pre>
> 서블릿 = 자바를 이용한 확장된 CGI 방식의 서버 프로그래밍 방식 
> JSP 엔진(컨테이너) = JSP 소스에서 서블릿 소스 및 서블릿 클래스 생성을 처리하는 서버 모듈
> JSP 라이프 사이클 = _jspInit() > _jspService() > _jspDestroy()로 이어지는 주요 메소드 존재
> </pre>

<h2> JSP 운영/개발 환경</h2>

> <pre>
> JSP 운영 환경 = 웹 서버와 JSP 엔진이 필요함 ( 톰캣은 둘 다 있으므로 한번에 사용 가능)
> JSP 개발 환경 = JDK > 톰캣 > Eclipse 사용
> </pre>

<h2> eclipse 구성 </h2>

> <pre>
> 퍼스펙티브 = 이클립스 기본 화면
> 뷰 = 퍼스펙티브를 구성하는 각각의 창
> 설정은 Preferences 대화상자에서 가능 > 폰트 수정 / 브라우저 실행 등 설정 가능
> 탬플릿으로 JSP 소스 탬플릿 생성 가능
> </pre>

<h2> JSP 템플릿 </h2>

> ```javascript
> <@ page language="java" contentType="text/html; charset=${encoding}" pageEncoding="${encoding}"%>
> <html>
> <head>
> <meta http-equiv="Content-Type" content="text/html; charset=${encoding}">
> <title></title>
> </head>
> <body>
> ${cursor}
> </body>
> </html>
> ```

<h2> JSP 기본 문법 </h2>

> JSP 태그 방식은 ``스크립트`` / ``액션`` / ``커스텀`` 태그로 나뉨
> <pre>
> 스크립트 태그
> 지시어 - <%@  %> (JSP 페이지의 속성 지정)
> 선언 - <%!  %> (소속변수 선언과 메소드 정의)
> 표현식 - <%=  %> (변수, 계산식, 함수 호출 결과를 문자열 형태로 출력)
> 스크립트릿 - <%  %> (자바 코드를 기술)
> 주석 - <%-- --%> (JSP 페이지의 설명 추가)
> </pre>
>
> 액션 태그
>```javascript
> <jsp:include page=" " /> (현재 jsp 페이지에서 다른 페이지를 포함)
> <jsp:forward page=" " /> (현재 jsp 페이지의 제어를 다른 페이지에 전달)
>```
>
> 커스텀 태그
> ```javascript
> <tag=printData dbname="mydb" table="memb" />
> ```
> jsp 스크립트 요소
> <pre>
> 설명을 기술하는 주석
> </pre>

<h2>스크립트릿</h2>

> 자바 코드 삽입
> ```javascript
> <% code fragment %>
> ```
> 변수나 객체 / 문자열의 출력 표현 = 객체 ``out``의  ``print() / println()``메소드 사용
> ```javascript
> <% out.print("스크립트릿 태그"); %>
> ```
> 여러 문장을 한번에 출력
> ```javascript
> <% 
>   String str = "스크립트릿 태그";
>   out.print(str);
>  %>
> ```
> ``<br>`` 태그를 이용하지 않으면 줄바꿈 불가능함<br><br>
> 
> 표현식 (변수 설정 / 사용)
> ```javascript
> <%= 변수 / 계산식 / 함수 호출 결과 %> (문자열 형태로 출력, out 객체를 통해 클라이언트로 전달)
> ```
> 예제
> ```javascript
> <% String exp = "표현식"; %>
> <%= exp %>
> 
> <% int a == 100; %>
> <%= a %>
> ```

<h2>서블릿 변환과 오류 점검</h2>

- 톰캣 JSP 엔진은 JSP 소스인 `*.jsp`를 서블릿 소스 `*_jsp.java`로 자동 생성해 서블릿 클래스를 실행함
- 서블릿으로 변환한 이후 생기는 오류는 문법 오류임
- 변환된 서블릿을 실행한 이후에도 오류가 발생하는데, 이 오류는 컴파일할 때는 발생하지 않음

<h2>선언과 주석</h2>

> 선언
> <pre>
> 선언 태그 = <%!  %>를 사용해 소속 변수를 선언하거나 메소드를 구현하는 태그
> - 이 때 선언되는 변수는 소속 변수이며, 스크립트릿에서 선언되는 변수는 지역 변수임
> </pre>
> ```javascript
> <% int i = 0; %> - 지역 변수 ( 변수를 선언한 문장 이후에서 참조 가능, 이전 값이 남지 않음 )
> <%! int memi = 0; %> - 소속 변수 (변수를 선언한 문장 이전에도 참조 가능, 이전 값이 남음 )
> ```
> 주석
> ```javascript
> <!-- HTML 주석, 웹의 소스 보기에서 보임 -->
> <%-- JSP 주석, 웹의 소스 보기에서 안보임 --%>
> /* 일반 자바 주석, 웹의 소스 보기에서 안보임 */
> ```

<h2>지시자</h2>

> - 지시자 = 태그 형태를 이용해 JSP 페이지에 대한 속성이나 특별한 지시 사항을 지정하는 태그<br>
> - 지시어 `directives` / 속성 `property` 모두 대소문자를 구분하고 속성 값은 반드시 따옴표를 이용해 둘러싼다
> ```javascript
> <%@ page property="property-value" %> - JSP page에 대한 속성 지정 (page)
> <%@ include file ="file-name" %> - 태그 부분에 지정한 페이지를 정적으로 삽입 (include)
> <%@ taglib uri="uri-value" prifix="pfx-value" %> - 새로운 태그를 정의하여 사용 (taglib)
> ```
> 페이지 지시자
> ```javascript
> <%@ page language="java" contentType="text/html; charset=EUC-KR" pageEncoding="EUC-KR"%>
> <%@ page language="java" %> - language 속성 ( 대부분 java만 지원하나 향후 확장을 위해 만듬 )
> <%@ page contentType="text/html" %> - contentType 속성 (지정하지 않으면 "text/html"이 기본)
> <%@ page contentType="text/html; charset=ISO-8859-1" %> - 구분자 세미콜론으로 문자셋 지정이 가능
> <%@ page contentType="text/html; charset=EUC-KR" %> - 한글 지원을 위해 EUC-KR 지정
> <%@ page pageEncoding ="ISO-8850-1" %> - JSP의 문자 인코딩 방식을 기술하는 속성
> <%@ page pageEncoding ="EUC-KR" %> - 한글 지원을 위해 EUC-KR로 지정
> <%@ page info="JSP 페이지에 대한 설명이나 정보" %> - JSP 페이지 전체에 대한 정보를 문자열로 기술
> <%@ page import="java.util.*" %> - 자바의 import를 대체하는 속성으로, 이용할 클래스를 지정
> <%@ page import="java.util.Date, java.sql.*" %> - 콤마를 이용해 여러 클래스 지정 가능
> <%@ page isErrorPage="true" %> - JSP 페이지가 오류를 처리하는 페이지인지 지정 (기본값 False)
> <%@ page errorPage="exception.jsp" %> - JSP 페이지에서 발생한 오류를 처리하는 JSP 페이지 기술
> <%@ page isThreadSafe="false" %> - 동시 사용자 접속 처리에 대한 지정 방법 (true가 기본값)
> <%@ page isELIgnored="true" %> - 표현 언어인 EL의 사용 여부를 지정하는 방법
> <%@ page buffer="16kb" %> - JSP 페이지의 출력 버퍼링 메모리 크기를 지정하는 방법
> <%@ page buffer="none" %> - 버퍼링(어느정도 자료를 모아 입출력을 처리하는 방법)을 하지 않겠다는 의미
> <%@ page autoFlush = "true" %> - 버퍼가 모두 찼을 때 자동으로 출력하는지를 지정하는 방법 (true가 기본)
> <%@ page session="false" %> - JSP 페이지에서 세션의 사용 여부 지정 (true가 기본 값)
> ```
> `include` 지시자
> ```javascript
> <% include file="file_name" %> - 태그를 기술한 위치에 지정한 파일을 삽입하는 속성
> ```
> - `include` 지시자는 삽입되는 파일의 JSP 지시자에 해당하는 부분을 그대로 삽입하지 않으며<br>
    처리 단계를 거쳐 HTML 또는 일반 텍스트만 삽입됨 (삽입되는 파일은 구조적 HTML 태그 생략 가능)

<h2>내장 객체</h2>

> - JSP 페이지의 스크립트릿과 표현에서 선언 없이 이용할 수 있는 객체 변수 (9개가  존재)
>> `out` = 출력 스트림 <br>
>> `request` = 클라이언트의 요청에 의한 폼 양식 정보 처리 <br>
>> `response` = 클라이언트의 요청에 대한 응답 <br>
>> `session` = 클라이언트에 대한 세션 정보 처리 <br>
>> `application` = 웹 애플리케이션 정보 처리 <br>
>> `config` = 현재 JSP 페이지에 대한 환경 처리 <br>
>> `exception` = 예외처리를 위한 객체 <br>
>> `page` = 현재 JSP 페이지에 대한 클래스 정보 <br>
>> `pageContext` = 현재 JSP 페이지에 대한 페이지 컨텍스트
>> - 내장 객체는 JSP 서블릿의 _jspService() 메소드의 내부에서 이용할 수 있는 <br>
  지역 / 매개 변수이므로 JSP 선언에서는 이용 불가 <br>
> 
> - `request` <br>
> 클라이언트가 서버에게 전송하는 관련 정보를 처리하는 객체, HTML 폼에 입력해 값을 전송할 때 사용<br>
> 여러 메소드를 상속받아 이용 가능
> ```javascript
> <% request.setCharacterEncoding(String env) %> - 요청 페이지에 env의 인코딩 방법 적용
> <% request.getParameter(String name) %> - name의 요청 인자 값 반환(없으면 NULL, 여러개면 1번 값 반환)
> <% request.getParameterValues(String name) %> - name의 요청 인자 값을 문자열 배열로 반환(없으면 NULL)
> <% request.getParameterNames() %> - 모든 인자 값을 Enumeration으로 변환
> <% request.getProtocol() %> - 사용중인 프로토콜을 반환
> <% request.getRemoteAddr() %> - 클라이언트의 IP 주소를 반환
> <% request.getRemoteHost() %> - 클라이언트의 호스트 이름을 반환
> <% request.getServerName() %> - 요청된 서버의 호스트 이름을 반환
> <% request.getServerPort() %> - 요청된 서버의 포트 번호를 반환
> ```
> - 반환값<br>
> `setCharacterEncoding` = void<br>
> `getparameter` = String - 값을 1개만 반환 받음<br> 
> `getparameterValues` = String[] - 값을 여러 개 반환 받음<br>
> `getparameterNames` = Enumeration<br>
> `getProtocol` = String<br>
> `getRemoteAddr` = String<br>
> `getRemoteHost` = String<br>
> `getServerName` = String<br>
> `getServerPort` = String<br>
> 
> HTML 폼 정보 > jsp 전송시
>```html
> <form method = "post" action="전송할파일.jsp">
>   <input type="입력 방식" 입력형식="입력 변수"><p>
>   <select>
>    <option SELECTED value="선택할 대상">선택할 대상</option>
>    <option value="선택할 대상2">선택할 대상2</option>
>   </select></p>
></form>
> ```
> - 여러개 입력 받을 때는 `select` 태그의 옵션을 `multiple`로 지정하고<br>
> `getparameterValues()`에 저장시킴 이때 저장되는 배열명을 출력하려면 `for`문 사용
> ```javascript
> for (int i=0; i < 배열변수명.length; i++)
>       out.println(배열변수명[i] + " ");
> or
> for ( String each변수명 : 배열변수명 )
>       out.println(eachmajor + " ");
> ```
> 
> - 태그 `input` 속성 `type`은 `checkbox`인 경우 다중 선택이 가능<br>
> `radio`인 경우는 단일 선택만 가능
> 
> 받은 jsp 코드
> ```javascript
> <% request.setCharacterEncoding("euc-kr"); %>
> 
> <% String 입력 변수 = request.getparameter("변수");
> 
> 결과
> 출력 변수명: <%= 입력 변수%><p>
> ```
> request의 자료유형인 인터페이스 HttpServletRequest의 메소드
> ```javascript
> <% request.getCookies() %> - 클라이언트에 보내진 쿠키 배열 반환
> <% request.getQueryString() %> - URL에 추가된 Query 문자열을 반환
> <% request.getRequestURI() %> - 클라이언트가 요청한 URI 반환
> <% request.getRequestURL() %> - 클라이언트가 요청한 URL 반환
> <% request.getSession() %> - 현재의 세션 반환 (세션이 없으면 만들어 반환)
> <% request.getMethod() %> - 요청 방식인 get, post 중의 하나를 반환 
> ```
> - 인자의 이름 전달 메소드 `getParameterNames()` <br>
> 반환값이 `Enumeration` 유형, 요청 페이지의 모든 인자 이름이 저장된 목록을 반환함 <br><br>
> - 일반화 유형 `Enumeration<string>`을 이용하면 `e.nextElement()`에서<br> `String`으로 자료 유형 변환이 필요 없이 반환 값을 `String` 유형 변수 `name`에 저장 가능 
> <br> + 요청된 인자의 이름을 직접 알지 못해도 인자의 이름을 알 수 있음

<h2>한글처리</h2>

> `post` 방식 = 전송 자료 크기의 제한 없이 사용자가 입력한 내용을 공개하지 않고 전송하는 방식
> - request 객체 사용시 html 파일에 `<form method = "post">`로 사용
> - jsp 파일에서 `'euc-kr'` 설정을 해줘야함
> 
> `get` 방식 = 전송 자료 크기에 제한이 있으며 사용자가 입력한 내용을 공개하여 전송
> - JSP 엔진 서버 설정 파일 `server.xml`에서 사용하는 `connecter` 속성에 `[URIEncoding="euc-kr"]` 추가
> - URL 부분에 전송 자료가 `[name1=값1&name2=값2]` 형식으로 추가되는 특징이 있음 (질의 문자열)

<h2>내장 객체 response와 out</h2>

> 내장객체 `response` = 서버가 클라이언트에게 요청에 대한 응답을 보내기 위한 객체
> ```javascript
> <% response.addCookie(Cookie cookie) %> - 쿠키 데이터 기록
> <% response.addHeader(String name, String value) %> - response 헤더 내용 기록
> <% response.sendRedirect(String location) %> -저장된 location 페이지로 이동
> <% response.setBufferSize(int size) %> -버퍼 크기 지정
> <% response.setContentType(String type) %> - Content Type 지정
> <% response.getBufferSize(int size) %> - 버퍼 크기 반환
> ```
> - 반환값<br>
> `addCookie` = void<br>
> `addHeader` = void<br>
> `sendRedirect` = void<br>
> `setBufferSize` = void<br>
> `setContentType` = void<br>
> `getBufferSize` = int <br>
>
>메소드 `sendRedirect()` = 원하는 페이지로 이동
> ```javascript
> <%
>   String URL = "원하는 페이지";
>   response.sendRedirect(URL);
> ```
> `out` = 클래스 `javax.servlet.jsp.JspWriter` 자료유형으로 JSP 페이지 출력을 위한 객체
> ```javascript
> <% out.print(자료값) %> - 여러 자료 유형 출력
> <% out.println(자료값) %> - 여러 자료 유형을 출력하고 현재 줄 종료
> <% out.clearBuffer() %> - 버퍼의 현재 내용물을 제거
> <% out.flush() %> - 버퍼 크기 지정
> <% out.clear() %> - 버퍼의 내용물 제거
> <% out.close() %> - 스트림을 닫음
> <% out.getBufferSize() %> - 버퍼의 전체 크기를 반환
> <% out.getRemaining() %> - 버퍼의 남아 있는 크기를 반환
> <% out.isAutoFlush() %> - 현재 autoFlush 상태를 반환
> ```
> - 반환값<br>
> `print` = void<br>
> `println` = void<br>
> `clearBuffer` = void<br>
> `flush` = void<br>
> `clear` = void<br>
> `close` = void<br>
> `getBufferSize` = int<br>
> `getRemaining` = int<br>
> `isAutoFlush` = boolean<br>
> 
> 버퍼링 = 페이지 지시자에서 `autoFlush`가 `false`이면 `overflow` 전에 `flush()`를 호출해 출력을 수동으로 해야함
> ```javascript
> <%@ page autoFlush="false" buffer= "1kb" %>
> <%
>   for (int i = 1; i < 100; i++){
>       out.println("남은 출력 버퍼 크기(out.getRemaining()) : " + out.getRemaining() + "<br>");
>       }
> %>
> ```
> jsp는 `autoFlush`의 기본이 `true`이므로 버퍼가 가득 차기 전에 `flush()`를 호출함<br>
> 그러나 `false`일 경우 메소드 `out.getRemaining()`을 이용해 `flush()`를 수동 호출 해야함

<h2>application / exception</h2>

> `application` = 내장 객체 `application`은 `javax.servlet.ServletContext` 인터페이스 자료 유형으로<br>
> 웹 애플리케이션에서 유지 관리되는 여러 환경 정보를 관리함
> ```javascript
> <% application.getServerInfo() %> - JSP 컨테이너의 이름과 버전 반환
> <% application.getAttribute(String name) %> - 웹 응용에서 지정된 이름의 속성을 반환
> <% application.log(String msg) %> - 지정된 msg의 로그를 저장
> <% application.setAttribute(String name, Object object) - 웹 응용에서 지정된 이름으로 object 저장
> <% application.removeAttribute(String name) - 웹 응용에서 지정된 이름의 속성을 삭제
> ```
> - 반환값<br>
> `getServerInfo` = String<br>
> `getAttribute` = Object<br>
> `log` = void<br>
> `setAttribute` = void<br>
> `removeAttribute` = void<br>
> 
> 조회 수 관리 = `getServerInfo()`로 웹 응용에서 이용하는 JSP 컨테이너 이름과 버전 확인
> - `SetAttribute`로 `count` 추가 > 조회수 관리 가능
> ```javascript
> <%=application.getServerInfo() %><p> - 서버 컨테이너 정보
> 
> String scount = (string) application.getAttribute("count");
> if (scount != null) {
>   count = Integer.paresInt(scount);
> } else {
>   count = 0;
> }
> -조회수 관리 기능
> ```
> 
> `exception` = 페이지 지시자에서 `isErrorPage="true"`로 지정한 경우 이용 가능한 내부 객체
> - 지정한 예외 처리 페이지에서 적절한 예외 처리를 구현함
> ```javascript
> <% exception.getMessage() %> - 예외를 표시하는 문자열 반환
> <% exception.toString() %> - 예외 자체 문자열을 반환
> <% exception.printStackTrace() %> - 표준 출력으로 스택 추적 정보 출력
> ```
> 
> 예외 발생 시 `error.jsp`로 이동하여 실행되는데 이때 적절한 메시지를 출력함

<h2>내부 객체</h2>

> 클래스 `PageContext` = 자료 유형 클래스 `javax.servlet.jsp.PageContext`로<br>
> JSP 페이지에 관한 정보와 다른 페이지로 제어권을 넘겨줄 때 이용되는 메소드를 제공함
> ```javascript
> <% pageContext.forward(String) %> - 다른 서블릿 혹은 JSP로 요청을 이동
> <% pageContext.include(String) %> - 지정된 페이지를 현재의 위치에 삽입
> <% pageContext.getException() %> - Exception 객체를 반환
> <% pageContext.getPage() %> - page 객체를 반환
> <% pageContext.getOut() %> - JspWriter 객체를 반환
> <% pageContext.getRequest() %> -ServletRequest 객체를 반환
> <% pageContext.getResponse() %> -ServletResponse 객체를 반환
> <% pageContext.getServletConfig() %> -ServletConfig 객체를 반환
> <% pageContext.getServletContext() %> - ServletContext 객체를 반환
> <% pageContext.getSession() %> - HttpSession 객체를 반환
> <% pageContext.findAttribute(String) %> - page, request, session, application 범위 내의
>                                           사용 가능한 속성의 값 반환
> <% pageContext.removeAttribute(String) %> - 지정한 이름의 속성 객체를 제거
> <% pageContext.getAttribute(String) %> -page 범위 내에서 특정한 이름에 해당하는 속성 개체를 반환
> <% pageContext.setAttribute(String, Object) %> - pageContext 객체 안에 지정한 이름과 연관된
>                                                  속성 객체 저장
> ```
> 
>- 반환값<br>
> `forward` = void<br>
> `include` = void<br>
> `getException` = Exception<br>
> `getPage` = Object<br>
> `getOut` = JspWriter<br>
> `getRequest` = ServletRequest<br>
> `getResponser` = ServletResponse<br>
> `getServletConfig` = ServletConfig<br>
> `getServletContext` = ServletContext<br>
> `getSession` = HttpSession<br>
> `findAttribute` = Object<br>
> `removeAttribute` = void<br>
> `getAttribute` = Object<br>
> `setAttribute` = void<br>
>
> `pageContext` = 8개의 다른 내부 객체를 얻을 수 있는 메소드 제공
> ```javascript
> PageContext pageContext = null;
> ```
> - 내장 객체 `pageContext`의 메소드를 이용, 내장 객체 변수에 각각의 객체를 저장해 내장 객체를 설정함
> 
> `page`= jsp 페이지 자체를 나타내는 객체
> ```javascript
> Object page = this; - 자기 자신을 나타내는 키워드 this로 사용
> ```
> - 메소드 `getServletInfo()`를 제공, JSP 페이지 지시자의 속성 `info`에 저장한 값 반환
> 
> `session` = 세션 관리를 위한 내부 객체, 클라이언트의 지속성 서비스를 위해 사용<br>
> 
> `config` = 자료유형 `javax.servlet.ServletConfig` 인터페이스로, <br>
서블릿이 초기화되는 동안 JSP 컨테이너가 환경 정보를 서블릿으로 전달할 때 사용하는 객체

<h2>액션 태그의 유형</h2>

> `XML` 스타일 태그 = `XML` 스타일의 태그로 기술하며 특정한 동작 기능을 수행함<br>
> `<`와 접두어 `jsp:` 그리고 `forward, include, param`과 같은 고유한 태그 키워드로 구성된 <br>
> `<jsp:forward`와 같은 시작 태그로 시작, 속성 값을 지정하며 마지막 종료 태그는 `/>`로 종료한다.
> ```javascript
> <jsp: 태그키워드 태그속성="태그값" />
> ```
> 액션 태그에서 매개 변수 지정과 같은 내용이 있다면 시작 태그와 종료 태그 사이에 `param`태그를 기술함

> ```javascript
> <jsp: 태그키워드 태그속성="태그값" >
>       매개변수 지정과 같은 다른 내용
> </jsp: 태그 키워드>
> 
> <jsp: 태그키워드 태그속성1="태그값1" >
>   <jsp:param 태그속성2="태그값2" value="밸류값" />
> </jsp: 태그키워드>
> ```
> 액션 태그의 종류 = `foward`,`param`,`include`,`plugin` 등

<h2>액션 태그 include</h2>

> 태그 `<jsp:include page="filename" />` = 현재 jsp 페이지에서 속성 `page`에 기술된 <br> 
> 다른 jsp 페이지를 호출해 그 결과를 `include` 태그 위치에 삽입시키는 역할
> ```javascript
> <jsp:include page="jsp페이지" />
> ```
> - 지시자 `include`와 액션 태그 `include` <br>
> 지시자는 소스 코드 형태로 삽입, 액션 태그는 처리 결과를 삽입한다. <br>
> 지시자는 중복된 소스가 있는 경우 주의가 필요함 (변수 선언 중복시 오류 발생)
> 액션 태그는 결과 값이 포함되기 때문에 중복 선언 문제 X

<h2>액션 태그 forward</h2>

> 태그 `<jsp:forward page="filename" />` = 지정한 페이지 호출 시 `forward` 태그가 있는 현재 페이지의 <br>
> 작업은 모두 중지되고 버퍼링 내역도 전부 사라져 출력되지 않으며, 모든 제어가 `page`에 지정한 파일로 이동함
> - `forward`와 `include`의 차이<br>
> `include` = `page` 속성에 지정된 페이지의 처리가 끝나면 다시 현재 페이지로 돌아와 처리를 진행<br>
> `forward` = `page` 속성에 지정된 페이지로 제어가 넘어가면 현재 페이지로 돌아오지 않고 이동된 페이지에서 실행 종료<br>
> 
> 내장 객체 `pageContext`의 메소드 `forward()` = 액션 태그 `forward`와 같은 기능 수행 (in 서블릿 소스)

<h2>액션 태그 Param</h2>

> 패라미터 태그 `<jsp:param ... />` = `page`에 지정된 페이지로 필요한 패라미터의 이름과 값을 전송<br>
> *내장객체 `request`와 전달되는 내용 이름이 같아 충돌시 태그 `param` 값이 전달됨<br>
> 다른 액션 태그와 주로 같이 이용되며 혼용시 다른 태그의 마지막이 `/>`에서 `>`로 바뀜 <br><br>
> 태그 `include`에서 지정된 인자의 전송
> ```javascript
> <jsp:include page="페이지명" >
>   <jsp:param name="name" value="value" />
> </jsp:include>
> ```
> `include`에서 삽입되는 페이지는 `param`을 인자로 전송받음과 함께 <br>
> 내장객체 `request.getParameter()`에 의한 인자도 함께 전송받음 <br><br>
> 
> 태그 `forward`에서도 같은 형식으로 사용 가능하다

<h2>액션 태그 Plugin</h2>

> 태그 `<jsp:plugin ... >` = 웹 브라우저에서 자바 빈즈 또는 애플릿을 플러그인하여 실행하는 태그<br>
> 액션 태그 `plugin`에서 플러그인 가능한 객체는 자바 빈즈와 애플릿 뿐임<br><br>
> 내부에 서브 태그로 사용되는 `<params>` 태그는 플러그인 객체에 패라미터 값을 전달함<br>
> (패라미터가 1개일 경우 태그 `params`에 직접 속성 `name`과 `value`를 함께 기술하여 종료함)

> `<jsp:fallback>` = 웹 브라우저가 플러그인을 지원하지 못하는 경우, 출력하는 메시지를 보여주기 위해 사용

<h2>웹의 비연결 특성</h2>
> 웹은 한 페이지의 요청과 그 요청에 대한 응답이 있을 때만 클라이언트와 서버가 연결(connection)될 뿐<br>
> 그 이후에는 연결이 자동으로 종료됨. >> 웹을 지원하는 HTTP 통신 규약은 비연결(무상태) 특성을 지님
> <br><br>
> 비연결성은 서버의 부담이 적고 자원을 효율적으로 쓸 수 있으나 <br>
> 정보를 지속적으로 유지 관리하는 것에 어려움이 있음<br><br>
> 
> 이를 보완해 지속성 서비스를 제공하기 위한 것이 쿠키(cookie)와 세션(session)임
> <pre>
> 쿠키 = 클라이언트의 사용자 컴퓨터에 사용자 정보를 저장 관리<br>
> 세션 = 클라이언트 사용자 별로 페이지 이동을 인식하고<br>
>       필요 정보를 서버에 저장/조회할 수 있는 방법과 세션 관리 방법 제공<br>
>
> -웹 서버가 종료되면 쿠키는 조회 가능하지만 세션 정보는 자동으로 삭제된다.
> </pre>

<h2>쿠키</h2>
> `쿠키` = 서버에서 만들어진 작은 정보의 단위 <br>
> 이름과 값으로 구성된 자료를 저장, 이외에 추가적인 정보 저장 가능<br>
> ```javascript
>   response.addCookie(Cookie cookie) - 쿠키 생성
>   request.getCookies() - 저장된 쿠키를 서버로 전달하여 조회
> ```
> - 쿠키는 개당 4K Byte 크기로 제한되고 각 웹사이트당 20개 허용<br>
> 모든 웹 사이트를 합쳐 최대 300개 허용되며 클라이언트 당 최대 용량은 1.2M Byte임<br><br>
> 
> 쿠키 추가 = 문자열의 인자 2개 (이름, 값)의 쌍 정보를 입력해 생성함 (알파벳 + 숫자로만 구성)
> ```javascript
>   Cookie cookie = new Cookie("name", "value");
> ```
> 생성된 쿠키는 메소드 `setMaxAge()`로 유효기간(초) 지정 가능<br>
> 초가 0이면 쿠키의 삭제를 의미하며, 음수 지정 시 브라우저가 종료되면 쿠키도 삭제된다.<br>
> ```javascript
>   cookie.setMaxAge(2 * 60); -초 단위: 2분
>   response.addCookie(cookie); - 클라이언트 컴퓨터에 파일 형식으로 저장
> ```
><br><br>
> 쿠키 조회 = 내장객체 `request`의 `getCookies()` 메소드 사용<br>
> 반환값은 저장된 모든 쿠키의 배열 (쿠키가 없으면 NULL값)이다.
> ```javascript
>   Cookie[] cookies = request.getCookies();
> ```
> `for each` 문과 Cookie의 `getName()`, `getValue()` 메소드를 이용해 각 쿠키의 이름과 값 얻기 가능
> ```javascript
>   for (Cookie c : cookies) {
>               out.println("쿠키 이름(name) : " + c.getName() + ", " );
>               out.println("쿠키 값(value) : " + c.getValue() + "<br>" );
>   }
> ```
 
<h2>세션</h2>
> 세션 = 클라이언트의 브라우저마다 각기 다른 정보를 서버에 저장하는 것 <br>
> 사용자 별로 여러 페이지 이동을 인식, 필요한 정보를 저장하고 조회할 수 있는 방법과 세션 관리 방법 제공
> <br><br>
> 내장 객체 `session` = 패키지 `javax.servlet.http`에 속하는 인터페이스 `HttpSession`임<br>
> 세션 자체의 식별자와 생성시간 정보를 제공하는 메소드인 `getId()`,`getCreationTime()` 등 제공<br>
> 세션이 유지에 필요한 속성 값은 `session` 객체의 `setAttribute(String name, objectvalue)`로 저장<br>
> 저장된 속성 값은 `getAttribute(String name)` 메소드로 조회 가능 > 반환값 유형이 Object라 <br>
> 저장한 객체로 다시 저장하려면 자료형 변환이 필요함<br><br>
> 세션의 주요 정보 조회<br>
> 세션은 클라이언트의 브라우저가 서버에 접속하는 순간 생성되며 기본값 30분 동안 유지됨<br>
> 30분 이상 반응이 없으면 종료되며 이 시간을 지정 가능함 <br>
> 세션 생성 시간을 시간정보로 출력하려면 `getCreationTime()` 메소드로 밀리세컨드로 반환하거나, <br> 
> 연월일로  출력시 클래스 `java.util.Date`의 생성자 `Date(long mseconds)` 사용해야함
>
> ```javascript
>   long mseconds = session.getCreationTime();
>   Date time = new Date(mseconds);
> ```
> 한번 생성된 세션은 새로고침시에도 동일한 세션이지만, <br>
> 브라우저를 바꾸거나 서버를 재시작하면 세션 ID와 생성 시간이 바뀐다.
> <br><br>
> 세션에 주요 값 저장과 조회
> 내장 객체 `session` 메소드 `setAttribute(String name, Object value)` = 세션쌍 저장 메소드
> ```javascript
>   session.setAttribute("name","value");
> ```
> 세션에 저장된 자료는 다시 `getAttribute(String name)` 메소드를 사용해 조회 가능<br>
> 이때 반환 값이 `Object` 유형이므로 저장된 객체로 자료유형 변환이 필요함
> ```javascript
>   String value = (String) session.getAttribute("name");
> ```
> 세션의 속성으로 지정한 이름을 모두 알기 위해서는 `getAttributeNames()` 메소드 사용<br>
> 반환값은 인터페이스 `Enumeration`으로 패키지 `java.util`에 속함. <br>
> 그러므로 페이지 지시자의 `import` 속성을 이용해야 JSP에서 사용 가능
> ```javascript
>   <%@ page import="java.util.Enumeration, java.util.Date" %>
>   ...
>   Enumeration<String>e = session.getAttributeNames();
> ```
> ㄴ 메소드의 반환 값을 저장할 객체 e의 자료유형은 `Enumeration<String>`임<br>
> 이렇게 일반화 유형으로 선언 시, `e.nextElement()`의 반환 값 저장에 자료유형 변환이 필요없는 장점 존재<br>
> 이 때, e는 일반화 유형이 아닌 단순 `Enumeration`으로도 선언 가능
> ```javascript
>   Enumeration e = session.getAttributeNames();
> ```
> 세션 `timeout` 시간 설정 = 메소드 `setAttribute()`를 이용해 ID와 생성 시간 저장이 가능<br>
> `setMaxInactiveInterval(값)` 메소드를 이용하면 값초 이상 반응 없을 시 세션 무효화도 가능
> ```javascript
>   session.setAttribute("Id",session.getId());
>   session.setAttribute("time", new Date(session.getCreationTime()));
>   session.setMaxInactiveInterval(5);
> ```
> 세션 속성 삭제 = `removeAttribute("id")` 메소드로 속성 이름을 인자로 호출함<br>
> 세션이 새로 만들어진 것인지 판별 => `isNew()` = boolean 유형으로 판별하는 메소드
> ```javascript
>   if ( session.isNew() ){
>       session.setAttribute("Id",session.getId());
>       session.setAttribute("time", new Date(session.getCreationTime()));
>       session.setMaxInactiveInterval(5);
>   } else {
>       session.removeAttribute("id");
>   }
> ```
> 클래스 `Date`의 메소드 `getTime()`을 이용해 세션 시간 계산
> ```javascript
>   long nowtime = new Date().getTime();
>   <% long sessiontime = nowtime - session.getCreationTime(); %>
>   <%! long beforetime = new Date().getTime(); %>
>   <% long inactiveinterval = nowtime - beforetime; %>
>   서버에 반응을 보이지 않은 시간 : <%=inactiveinterval/1000 %>초
>   <% beforetime = nowtime; %>
> ```
> 세션 ID 와 생성 시간이 세션의 속성 값으로 설정되고 조회되어 출력됨<br>
> 세션 유효시간을 기준으로 시간 이전에 새로고침하면 세션 ID를 삭제시키거나<br>
> 시간 이후 새로고침하면 새로운 세션 생성이 가능

<h2>쿠키와 세션 이용</h2>
> 이미 생성된 쿠키의 삭제 = `setMaxAge(0)` 호출해 쿠키를 새로 저장함 <br>
> 이미 생성된 세션의 삭제 = `removeAttribute("세션명")` 메소드 호출해 삭제함
