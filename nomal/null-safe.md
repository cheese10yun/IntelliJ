![](/assets/intellij-null.png)

인텔리제이의 설정을 통해서 `null`을 허용하지 매개변수, 리턴 타입에 대해서 어노테이션 `@NonNull`을 통해서 위 그림처럼 방지할 수 있습니다.

![](/assets/spring-null-safe.png)


1. `Preferences` 설정 단축키 `cmd + ,`
2. `Compiler` 텝에서  `Configure annotations...` 클릭
3. `Nullable`, `NotNull` 탭에서 각각 `+` 버튼 클릭 이후 `Nunllable` , `NonNull` 어노테이션 추가
   * **반드시 `org.springframework.lang` 어노테이션을 추가해야합니다.**
4. 인텔리제이 재부팅
