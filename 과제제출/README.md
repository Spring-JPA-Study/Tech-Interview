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
