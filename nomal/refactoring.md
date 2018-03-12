---
layout: post
title: 인텔리제이 리팩토링
subtitle: Intellij Refactoring
catalog: true
header-img:
tags:
 - IntelliJ
 - Refactoring
date: 2018-03-11
---

## 인텔리제이 리팩토링 기능

![](https://i.imgur.com/Dq0m2Pf.png)

인텔리제이의 리팩토링 기능을 이용해서 비교적 쉽게 리팩토링을 할 수 있습니다. 대표적인 리팩토링 기능들을 하나 하나 천천히 살펴 보도록 하겠습니다.

**해당 기능의 단축키는 스크린샷 하단 녹색으로 표시되어있습니다. 단축키 환경이 다른 사용자들은 해당 그림 처럼 Find Action 창에서 리팩토링 키워드를 검색하면 원하는 기능을 쉽게 찾을 수 있습니다. 위 예제는 `Extract Method` 검색한 이미지 입니다.**


## Extract Method : 함수 수출 기능

![](https://i.imgur.com/8uhaWJF.png)

```java
if(age > 19){
    //메소드 수출전
    System.out.println("성인 입니다.");
}

if(isSenior(age)){
    //메소드 수출후
    System.out.println("성인 입니다.");
}

private boolean isSenior(int age) {
    return age > 19;
}

```

메소드로 수출하는 기능으로 가장 많이 사용하는 리팩토링 기능입니다. 단순히 `age > 19` 으로 구분하는 것보다 `isSenior` 메소드를 이용해서 묻는 것이 가독성 및 유지보수에서도 좋다고 생각합니다.
저는 테스트 코드를 통과하는 코드를 최대한 빠르게 만들고 인텔리제이의 리팩토링 기능을 통해서 클린코드 작업을 진행합니다.

## Change Signature : 메소드 파라메터 추가, 삭제 및 변경
![](https://i.imgur.com/bsAUiSX.png)

```java
//리팩토링 전
public void printName() {
    printName("Yun");
}

private String printName(String firstName) {
    return firstName;
}

//리팩토링 후
public void printName() {
    printName("Yun", "kim");
}

private String printName(String firstName, String lastName) {
    return firstName + lastName;
}
```

메소드에 파라미터가 추가되는 일은 빈번하게 만나게 됩니다. 이 때 유용하게 사용할수 있는 기능이 `Change Signature` 기능입니다.  또한 메소드에 추가된 파라메터는 해당 메소드를 호출하는 곳에 일괄적용 됩니다.

## Rename : 이름 변경

![](https://i.imgur.com/N4RVP73.png)

```java
public void test() {
    printName("Yun", "kim");
}

//리팩토링전
private String printName(String firstName, String lastName) {
    return firstName + lastName;
}

//리팩토링후
private String printFullName(String firstName, String lastName) {
    return firstName + lastName;
}
```
클래스, 메소드, 변수 등등 이름을 변경하는 기능입니다. 정말 많이 사용 하는 기능중에 하나입니다. 이름이 변경되면 참조되는 모든 곳에서 일괄 변경 됩니다.

## Extract Variable : 변수 수출 기능
![](https://i.imgur.com/gIBsKZ8.png)

```java
// 리팩토링 전
public void printFullName() {
    printFullName("Yun", "kim");
}

//리팩토링 후
public void printFullName() {
    final String yun = "Yun";
    printFullName(yun, "kim");
}
```

특정 값을 변수로 수출하는 기능입니다. 기본적으로 `final` 키워드로 변수가 할당됩니다.변수는 생각보다 변수보다 상수로 사용을 많이 됩니다. 즉 한번 할당된 값을 변경하는 생각보다 흔하지는 않습니다.  그렇기 때문에 저는 일단 상수로 선언하고 나중에 값을 변경할 이유가 생기면 그때 `final` 키워드를 제거하는 방향으로 사용하고 있습니다.  `final` 키워드는 상수로 할당된 값이 변경되지 않는다고 명시적으로 선언함으로써 코드를 이해하는데 좋은 역활을 한다고 생각합니다.

## Extract Filed : 맴버 필드 수출 기능

![](https://i.imgur.com/OFRC3sm.png)

변수 수출 기능과 거의 동일 합니다. 특정 값을 멤버 필드로 할당됩니다.

## Extract Constant

![](https://i.imgur.com/09d6IB8.png)

변수 수출 기능과 거의 동일 합니다. 특정 값을 static 영역에 할당합니다.

## Pull Members up

![](https://i.imgur.com/8UDFcwU.png)

```java

public interface AttackStrategy {
}

public class MissileStrategy implements AttackStrategy{
    public void attack() {
        System.out.println("미사일 공격");
    }
}
```

위와 같은 코드일 경우 `attack()` 메소드를 상위 인터페이의 추상 메소드로 올리는 기능 입니다. 하위 클래스에서는 `@Override` 어노테이션이 자동으로 추가됩니다.

## Push Members down

Pull Members up 기능의 반대 기능입니다. 상위 클래스의 있는 메소드를 하위 클래스의 메소드로 내려줍니다.


## 결론

위에서 소개한 기능으로 레거시한 코드들을 리팩토링하는 것은 현실적으로 어렵습니다. 하지만 리팩토링을 너무 거창하고 어렵게 시작하는 것보다 반복 적인 코드를 효과적으로 줄이고 코드를 유지보수 및 가독성 좋은 코드를 작성하는 것도 좋은 리팩토링 이라고 생각합니다.






