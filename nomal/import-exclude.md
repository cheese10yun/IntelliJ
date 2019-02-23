# 특정 Import 제외하기

인텔리 제이에서는 자동 `Import`설정을 지원해주고 있습니다. `Import` 대상이 여러 개 일 경우에는 개발자가 직접 선택하아합니다.

![](/assets/import-setting.png)

위 그림처럼 있을 경우 `javax.transaction`를 `Import`할 수도 있습니다. 한번 전체 검색으로 `javax.transaction`을 찾아보는 것도 좋을 거 같습니다.

이런 경우에 특정 `Import`를 제외할 수 있습니다.

![](/assets/import-exclude.png)

1. Auto Import 탭으로 이동
2. `+` 버튼 클릭해서 사용하지 않을 Import 추가
3. 제외 대상 추가

```
import javax.transaction.Transactional; // 제거 대상 이라면 import, ;를 제거하고 추가한다

javax.transaction.Transactional
```

![](/assets/import-result.png)

자동완성 시 `javax.transaction.Transactional` 제외가 된 것을 확인할 수 있습니다.
