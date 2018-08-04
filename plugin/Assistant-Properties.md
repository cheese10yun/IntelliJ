# Assistant Properties 


<p align="center">
    <img src = "https://i.imgur.com/X6giEx5.gif"> 
</p>

위 그림처럼 유자가 추가한 properties 속성들도 자동 완성을 지원합니다.

<p align="center">
    <img src = "https://i.imgur.com/AmkyrnX.gif"> 
</p>

또 Properties 속성이 코드에 바인딩 되는지 확인 할 수 있어 아주 유용합니다.

## Properties 
```yml
sample:
  email: "yun@test.com"
  name : "yun"
  age: 27
  auth: true
```

```java
@Configuration
@ConfigurationProperties(prefix = "sample")
public class SampleProperties {
    private String email;
    private String name;
    private int age;
    private boolean auth;

    // getter, setter 
}
```
Properties 속성값과 바인딩 될 객체입니다.


## Plugin 추가

<p align="center">
    <img src = "https://i.imgur.com/rVX7XJz.png"> 
</p>

**대부분 이미 설치가 되어있을 겁니다.**


## 의존성 추가

### maven
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-configuration-processor</artifactId>
    <optional>true</optional>
</dependency>
```

### gradle
```
dependencies {
    optional "org.springframework.boot:spring-boot-configuration-processor"
}
```

## Intellij 설정

<p align="center">
    <img src = "https://i.imgur.com/Gojvv1c.png"> 
</p>

`Settings > Build, Execution & Deployment > Compiler > Annotation Processors` 에서 `Enable annotation processing`를 체크