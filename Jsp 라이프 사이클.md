# JSP 라이프 사이클  

JSP도 servlet 이므로 servlet객체가 생성된다.  

0. 브라우저가 웹서버에 jsp에 대한 요청 정보를 전달

1. 요청이 오면 jsp로 작성된 코드가 서블릿 코드로 변환되어 컴파일되어 servlet 클래스가 로딩되어 servelt 인스턴스가 생성된다.  (최초 요청시에만)

- 변환된 servlet에 _jspservice메소드 안에 jsp의 내용이 들어가 있다. 

2. 서버는 _jspinit() 메소드를 호출하여 servlet을 초기화하고 (첫 요청인 경우)

3. _jspservice() 메소드를 호출하여 servlet이 브라우저의 요청을 처리  (첫 요청이 아니라면 service만)

4. _jspservice() 메소드는 http요청을 처리하는 메소드 doget dopost 등을 호출  

5. 서버는 _jspdestroy() 메소드를 호출하여 servlet을 제거 (서블릿이 수정된 경우) 

서버를 다시 실행하면 _jspinit() 부터 다시 실행된다. (destroy -> init -> service)


<%! %> 를 이용하면 _jspservice메서드 안에 말고 다른 메서드나 다른 필드를 선언할 수 있다.

```
<%!
	public void jspInit(){
		// 실행 내용
	}

	public void jspDestroy(){
		//실행내용
	}
%>
```