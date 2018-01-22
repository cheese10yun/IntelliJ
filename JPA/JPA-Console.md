---
title: 인텔리제이 JPA Console
catalog: true
subtitle: JPA Console
header-img:
tags:
 - IntelliJ
 - JPA
 - JPA Console
---

![](https://i.imgur.com/oJqtQpV.gif)

**JPA를 시작하면서 크게 불편했던 점이 쿼리 실행 결과를 바로바로 확인할 수 없는 점이었는데 `IntelliJ JPA Console` 기능으로 확인해볼 수 있습니다.**


## DataBase 연동

### Data Source
![](https://i.imgur.com/7Uaibtf.png)
* 사용 중인 데이터베이스를 선택합니다.

### Database 정보 입력
![](https://i.imgur.com/Lt9fDab.png)

* `Name`, `Host`, `Database`, `User`, `Password`를 입력합니다.

## JPA 연동

### JPA Module 추가
![](https://i.imgur.com/hnAQEtJ.png)

1. `Project Structure` 설정
2. `Modules` 탭이동
3. 상단 `+` 클릭 이후 `JPA` 추가
4. 하단 `+` 클릭 이후 `Hibernate` 추가

### Persistence 추가
![](https://i.imgur.com/q8l4Pkr.png)
1. 위의 작업을 완료했으면 왼쪽 탭에 `Persistence` 추가됩니다.
2. `Assign Data Sources….`를 클릭합니다.
3. `Assign Data Sources` 에서 `Data Source` 항목에 위에 추가해 `Data Source` 항목을 추가합니다.

## JPA Console

### JPA Console 연결
![](https://i.imgur.com/230LRUi.png)
1. `entityManagerFactory`를 클릭합니다.
2. `Console`를 클릭합니다.
3. `JPA Console`를 선택합니다.

### Query
![](https://i.imgur.com/oJqtQpV.gif)
JPQL 쿼리를 통해서 결과를 출력했습니다. 다음 포스팅에는 구체적인 사용법을 진행해 보겠습니다
