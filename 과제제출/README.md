# 스프링 완전 정복

## 01. 스프링 입문

### ❔[1. SpringFramework AOP의 개념 및 사용 사례를 설명해주세요.](#❕1)

### ❔[2. ](#❕2)

### ❔[3. ](#)

### ❔[4. ](#)

### ❔[5. ](#)

### ❔[6. ](#)

---

## 모범답안

### ❕[1. SpringFramework AOP의 개념 및 사용 사례를 설명해주세요.](#❔1)

<details> <summary>1. 모범답안</summary> <div markdown="1">  

```

AOP(Aspect Oriented Programming)는 관심사의 분리를 구현하기 위한 패러다임이며 OOP(Object Oriented Programming)의 한계를 보완하기 위해 등장한 개념 입니다.
횡단 관심사를 정의하고 모듈화하는데 중점을 두는데, 횡단 관심사란 여러 모듈에서 공통적으로 사용되는 기능을 의미하며, 이를 적절하게 분리하지 않으면 코드의 중복, 낮은 유지보수성 등의 문제를 초래할 수 있습니다.
로깅, 트랜잭션 관리 등의 기능이 이에 해당됩니다.
스프링에서는 AOP를 지원하기 위해 Proxy 패턴을 기반으로 AOP를 구현하며, 이를 통해 횡단 관심사를 모듈화하고 핵심 비즈니스 로직에서 분리합니다.
이를 통해 코드의 가독성과 유지보수성을 향상시킬 수 있지만 성능에서 약간의 손해를 보게 되는데, 이는 Proxy 패턴을 사용하기 때문입니다.

```

##### 해설


</div> </details>


<details> <summary>1-1. AOP 사례로 트랜잭션 처리 예시를 들었는데 어떤 방식으로 처리되는지 알고 있나요?</summary> <div markdown="1">  

```

스프링에서 트랜잭션 관리는 주로 @Transactional 어노테이션을 통해 선언적으로 사용됩니다.
@Transactional 애노테이션이 선언된 메서드는 스프링의 TransactionInterceptor라는 AOP Advice에 의해 감싸져 실행되며, 이 Advice는 메서드의 실행 전후에 트랜잭션을 시작하고 커밋 또는 롤백하는 역할을 수행 합니다.
메서드가 호출되면 TransactionInterceptor는 트랜잭션 시작 전에 먼저 실행됩니다. 이 때 PlatformTransactionManager를 사용하여 트랜잭션을 시작합니다. 그 후, 실제 메서드가 실행되고, 메서드 실행이 끝나면 TransactionInterceptor는 메서드 실행 결과에 따라 트랜잭션을 커밋하거나 롤백합니다.  
예외가 발생하지 않았다면 트랜잭션은 커밋되고, 그렇지 않다면 롤백됩니다. 만약 @Transactional 애노테이션이 클래스 레벨에 선언되었다면, 해당 클래스의 모든 public 메서드는 이와 같은 트랜잭션 관리 로직이 적용됩니다.

```

##### 해설


</div> </details>



<details> <summary>1-2. PointCut과 Advice의 차이를 설명해주세요.</summary> <div markdown="1">  

  ```

Pointcut: Pointcut은 어떤 메소드를 Advice(보조 기능)가 적용될 지 대상을 지정하는 표현식입니다.
이 표현식에 의해 선택된 메소드가 실행될 때, 연결된 Advice가 실행됩니다.
이를 통해 어떤 메소드에 대해 보조 기능을 적용할 것인지 세밀하게 설정할 수 있습니다.

Advice: Advice는 Pointcut에 의해 선택된 메소드에 추가로 실행되는 코드입니다.
AOP에서 보조 기능을 담당하며, 언제 어떻게 실행될지에 따라 여러 종류로 나눠집니다.
그 중에는 메소드 실행 전에 실행되는 Before Advice, 메소드 실행 후에 실행되는 After Advice, 메소드에서 예외 발생 시에 실행되는 After Throwing Advice 등이 있습니다.

  ```

##### 해설


</div> </details>

<br>

### ❕[2. ](#❔2)

<details> <summary>2. 모범답안</summary> <div markdown="1">  

  ```
  어쩌구저쩌구 입니다
  ```

##### 해설

    어쩌구저쩌구 입니다 

</div> </details>


<details> <summary>2-1. 어쩌구저쩌구?</summary> <div markdown="1">  

  ```
  어쩌구저쩌구 입니다
  ```

##### 해설

    어쩌구저쩌구 입니다

</div> </details>



<details> <summary> 2-2. 어쩌구저쩌구?</summary> <div markdown="1">  

  ```
  ~~~
  ```

##### 해설

    어쩌구저쩌구

</div> </details>
