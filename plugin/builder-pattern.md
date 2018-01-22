---
layout: post
title: 인텔리제이로 Builder Pattern 쉽게 구현하기
catalog: true
date: 2018-01-18 01:25:21
subtitle:
header-img:
tags:
- IntelliJ
- Builder Pattern
---

이미 많은 분들이 빌더 패턴 관련해서 포스팅을 잘 정리해주셔서 빌더 패턴에 대해서 설명 해주기 보다는 인텔리제이 플러그인을 활용해서 좀 쉽게 사용할 수 있는 팁을 포스팅을 해보겠습니다.
물론 Lombok을 활용해서 빌더를 손쉽게 사용할 수있지만 Lombok을 사용하지 않고도 쉽게 만들 수 있는 방법을 소개해드리겠습니다.


## Builder Generator 플러그인 설치
![](https://i.imgur.com/qlSmnIG.png)

**Preferences -> Plugins -> Browse Repositories -> Builder Generator 검색 및 설치**

## 빌더클래스 생성 방법
![](https://i.imgur.com/vj6km1L.gif)

* `command + n` 키를 눌러 Builder 를 선택합니다.
* 위 화면처럼 Builder 클래스를 생성합니다.


## 빌더 패턴 간단 소개

### Member 객체
```java
public class Member {

    private String name; //mandatory
    private String email; //mandatory
    private String mobile; //optional
    private String address; //optional
    private String password; //optional
    private String state; //optional
    private int age; //optional

    //Getter, Setter, Constructor
}
```


### 문제점
```java
Member member = new Member(name, email, mobile ....)
```
* 객체를 생성할 때 어떤 값이 필수 값인지 옵션 값인지 인지 하기 어렵다.
* `Member member = new Member(name, email, mobile ....)` 생성자로 객체를 생성 할 경우 반드시 순서를 맞추야 한다.
* `Setter`로 생성할 경우 Setter 메소드를 많이 작성해야한다.

### 해결
* 빌더 패턴을 사용해서 필수 값은 생성자로 옵션 값은 빌더 클래스로 작성한다.


### MemberBuilder.class

```java
public final class MemberBuilder {
    private final String name; //mandatory
    private final String email; //mandatory
    private String mobile; //optional
    private String address; //optional
    private String password; //optional
    private String state; //optional
    private int age; //optional

    private MemberBuilder(String name, String email) {
        this.name = name;
        this.email = email;
    }

    public static MemberBuilder aMember(String name, String email) {
        return new MemberBuilder(name, email);
    }

    public MemberBuilder withMobile(String mobile) {
        this.mobile = mobile;
        return this;
    }

    public MemberBuilder withAddress(String address) {
        this.address = address;
        return this;
    }

    public MemberBuilder withPassword(String password) {
        this.password = password;
        return this;
    }

    public MemberBuilder withState(String state) {
        this.state = state;
        return this;
    }

    public MemberBuilder withAge(int age) {
        this.age = age;
        return this;
    }

    public Member build() {
        Member member = new Member();
        member.setName(name);
        member.setEmail(email);
        member.setMobile(mobile);
        member.setAddress(address);
        member.setPassword(password);
        member.setState(state);
        member.setAge(age);
        return member;
    }
}
```

* 필수 맴버 필드인 `name, email`에 `final`을 추가합니다.
* 생성자 파라미터에 `name, email` 추가합니다.
* 자동으로 만들어준 `name, email`의 `with` 메소드를 제거 합니다.


### 객체 생성

```java
Member member = MemberBuilder
                .aMember("Yun", "cheese10yun@gmail.com")
                .withAddress("address")
                .withAge(20)
                .withMobile("010-XXXX-XXXX")
                .build();
```

![](https://i.imgur.com/lNLW4dh.png)
* 필수 값은 생성자로 넘겨 필수 값을 넘겨 필수 값을 인지 하기 쉽습니다.
* 옵션 값들은 순서에 상관 없이 .`with...()` 메소드로 이어나갑니다.

## 결론
객체를 안전하게 생성하고 쉽게 생성할 수 있다는 장점이 있습니다. 개념도 그렇게 어렵지 않아 가장 만만하게 도입해 볼만한 디자인 패턴인거 같습니다.
