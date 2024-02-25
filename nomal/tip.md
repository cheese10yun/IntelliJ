# IntelliJ Tip

## Database Global

![](/assets/a002.png)

IntelliJ에서는 MySQL, Oracle, PostgreSQL, Redis, Mongo DB 등을 포함한 다양한 데이터베이스에 대한 지원을 제공해주고 있습니다. **이를 통해서 동일한 도구를 이용해서 다양한 데이터베이스에 대한 작업을 수행할 수 있습니다.**

![](/assets/a001.png)

해당 Database 설정은 Project Data Sources을 통해서 프로젝트 단위로 설정할 수 있습니다. 만약 다양한 프로젝트에서 이 설정을 공유해서 사용하고 싶다면 빨간색 박스 버튼을 누르면 **Project Data Sources를 Global로 설정할 수 있습니다.**


## Database DateTime Format

![](/assets/a003.png)

데이터베이스에서 DateTime이 UTC 기준으로 저장되어 있을 때, 특정 지역의 시간대로 설정하여 데이터 조회를 보다 편리하게 할 수 있습니다. 이 설정은 Data Editor and Viewer에서 `Display temporal data in time zone` 옵션을 통해 원하는 지역의 시간대로 변경할 수 있습니다.


![](/assets/a004.png)

해당 설정을 한 이후 조회 쿼리를 실행하여 결과를 확인 해보면 `Asia/Seoul` 기준으로 출력되는 것을 확인할 수 있습니다.


## Live Template

![](/assets/a005.png)

```kotlin
// TODO: xxxx 2024-11-25 by yun.cheese
```

Live Template에서 TODO를 설정 하여 코드 작성시 자동으로 주석을 추가할 수 있습니다. 이런 경우 TODO 작성시 $END$를 통해 커서를 이동시킬 수 있습니다. 또한 작성 날짜를 추가하고 싶다면 `Edit variables`를 통해 `Date`를 추가할 수 있습니다. Data Formatter을 `yyyy-MM-dd`와 같이 설정할 수 있습니다.
