# 스프링 완전 정복

## 01. 스프링 입문

### ❔[1. ](#❕1)
### ❔[2. ](#❕2)
### ❔[3. ](#)
### ❔[4. ](#)
### ❔[5. ](#)
### ❔[6. ](#)

---
## 모범답안

### ❕1. 스프링 MVC 에 대해 설명하시오.

<details> <summary>1. 모범답안</summary> <div markdown="1">  


  ```
  1. Model : 데이터 관리 및 비즈니스 로직과 관련되어 있으며 내부 처리에 집중되어있다.
  2. View : 비즈니스 로직 처리 결과를 통해 유저 인터페이스가 표현되는 구간으로 화면을 그리는데 집중한다.
  3. Controller : 사용자의 요청을 처리하고 Model 과 View 를 중개하는 역할을 한다.
  ```

  ##### 해설

</div> </details>


<details> <summary>1-1. Model1 과 Model2 의 특징 및 차이점에 대해 설명하시오.</summary> <div markdown="1">  


  ```
  MVC1 은 모든 클라이언트 요청과 응답을 JSP 가 담당하는데, JSP 가 Controller 와 View 의 기능을 모두 담당한다. 구현이 단순하다는 장점이 있으나 웹이 복잡해질수록 유지보수가 힘들어진다는 단점이 있다.

  MVC2 가 우리가 일반적으로 이야기하는 MVC 모델인데, Controller 와 View 의 역할을 명확히 분리하여 MVC1 의 단점을 보완하고 유지보수 및 확장성이 뛰어나다는 장점이 있다.
  ```

  ##### 해설

</div> </details>



<details> <summary>1-2. 요청이 들어왔을 때 스프링 MVC 는 어떤 흐름으로 요청을 처리하는지 설명하시오</summary> <div markdown="1">  


  ```
  1. DispatcherServlet이 브라우저로부터 요청을 받는다.
  2. DispatcherServlet은 요청된 URL을 HandlerMapping 객체에 넘기고, 호출해야 할 Controller 메소드(핸들러) 정보를 얻는다. 
  3. DispatcherServlet이 HandlerAdapter 객체를 가져와서 해당 객체의 메소드를 실행한다.
  4. Controller 객체는 비즈니스 로직을 처리하고, 그 결과를 바탕으로 view에 전달할 객체를 Model 객체에 저장한다. DispatcherServlet에게 view name을 리턴한다.
  5. DispatcherServlet은 view name을 View Resolver에게 전달하여 View 객체를 얻는다.
  6. DispatcherServlet은 View 객체에 화면 표시를 의뢰한다.
  7. View 객체는 해당하는 뷰를 호출하며, 클라이언트로 보낸다.
  ```

  ##### 해설

    출처 : https://velog.io/@kk1112k/%EB%B0%B1%EC%97%94%EB%93%9C-%EA%B0%9C%EB%B0%9C-%EA%B8%B0%EC%88%A0%EB%A9%B4%EC%A0%91-%EC%A0%95%EB%A6%AC-Spring-%EC%B6%94%EA%B0%80%EC%A4%91

</div> </details>