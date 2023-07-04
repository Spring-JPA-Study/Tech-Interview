# 스프링 완전 정복

## 01. 스프링 입문

#### [1. SOLID란 무엇인가?](#1-solid란-무엇인가-1)
#### [2. ](#❕2)
#### [3. ](#)
#### [4. ](#)
#### [5. ](#)
#### [6. ](#)


---
## 모범답안

#### 1. SOLID란 무엇인가?

<details> <summary>1. 모범답안 </summary> <div markdown="1">  


  ```
  Robert Martin이 창시한 소프트웨어 설계 원칙으로 좋은 객체지향 설계를 위한 원칙이다. 
  1. SRP: 단일 책임 원칙
  2. OCP: 개방-폐쇄 원칙
  3. LSP: 리스코프 치환 원칙
  4. ISP: 인터페이스 분리 원칙
  5. DIP: 의존관계 역전 원칙
  ```

  ##### 해설

    1. SRP: 단일 책임 원칙
        - 한 클래스에는 하나의 책임만 가져야 한다
        - 중요한 기준은 변경이다. 변경이 있을 때 파급효과가 적으면 단일 책임 원칙을 잘 따른 것
    2. OCP: 개방-폐쇄 원칙
        - 확장에는 열려있으나 변경에는 닫혀있어야 한다
        - 다형성을 활용하여 역할과 구현을 분리
    3. LSP: 리스코프 치환 원칙
        - 서브 타입은 언제나 기반 타입으로 교체할 수 있어야 한다
    4. ISP: 인터페이스 분리 원칙
        - 특정 클라이언트를 위한 인터페이스 여러개가 범용 인터페이스 하나보다 낫다
    5. DIP: 의존관계 역전 원칙
        - 상위 모듈은 하위 모듈에 의존해서는 안되고 둘 다 추상화에 의존해야 한다

</div> </details>



```java
public class MemberServiceImpl implements MemberService {

    private final MemberRepository memberRepository = new MemoryMemberRepository();

}
```

<details> <summary>1-1. 위 코드는 SOLID원칙중 어떤 원칙을 위반하는가?</summary> <div markdown="1">  


  ```
  DIP(의존관계 역전 원칙) 위반
  ```

  ##### 해설

    MemberServiceImpl은 MemberRepository(인터페이스)와 MemoryMemberRepository(구현체)를 의존한다.
    즉, 추상화에도 의존하고 구체화에도 의존하고 있는 형태이다. 
    이는 추후 변경이 있을 때 문제가 되는 부분으로 DIP를 위반한다.

</div> </details>




<details> <summary>1-2. spring은 DIP를 제공하고 있는데, 왜 DIP가 필요할까?</summary> <div markdown="1">  


  ```
  역할과 구현을 분리하기 위함이다.
  ```

  ##### 해설

    만약 객체에 의존하게 된다면, 그 객체가 수정이 될때마다 바라보고 있는 객체의 코드도 수정해야할 지 모른다. 이는 의존성이 객체로 향해 있기 때문이다.
    하지만 DIP원칙에 따르기 위해 인터페이스를 작성하고 의존성을 그쪽에 향하게 한다면 그 객체의 수정내용에 대해서 알 필요가 없다는 것이다.
    인터페이스가 변경되지 않는 이상 그 객체가 수정되는거에 관여하게 될 일이 없기 때문이다.

</div> </details>

<br>
<br>

#### 2. 스프링 컨테이너란 무엇인가?

<details> <summary>1. 모범답안 </summary> <div markdown="1">  


  ```
  스프링 컨테이너는 스프링에서 자바 객체들을 관리하는 공간을 말합니다.
  ```

  ##### 해설

    자바 객체를 스프링에선 빈(Bean)이라고 하는데, 
    스프링 컨테이너에서는 이 빈의 생성부터 소멸까지를 개발자 대신 관리해주는 곳이라고 할 수 있습니다.

</div> </details>



<details> <summary>1-1. 컨테이너의 종류 두가지를 말하시오</summary> <div markdown="1">  


  ```
  BeanFactory, ApplicationContext
  ```

  ##### 해설

    ApplicationContext컨테이너가 BeanFactory의 기능을 포괄하면서 
    추가적인 기능을 제공하기 때문에 대부분의 경우에는 ApplicationContext를 사용합니다.

</div> </details>




<details> <summary>1-2. 스프링 빈을 등록하는 방법 두가지를 말하시오</summary> <div markdown="1">  


  ```
  컴포넌트 스캔, 스프링 빈 직접 등록 
  ```

  ##### 해설

    1. 컴포넌트 스캔
        @Component 사용
        @Controller, @Service, @Repository 등도 인터페이스로 @Component를 받기 때문에 컴포넌트 등록 가능
    2. 스프링 빈 직접 등록 
        @Configuration, @Bean 어노테이션으로 가능

</div> </details>