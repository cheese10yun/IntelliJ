---
layout: post
title: 인텔리제이 Live Template
subtitle: IntelliJ Tip
catalog: true
header-img: https://i.imgur.com/avC1Xor.jpg
tags:
  - null
thumbnail: https://i.imgur.com/H4qR4aa.png
date: 2018-03-18
---

## IntelliJ Live Template

IntelliJ Live Template 이란 코드 템플릿을 미리 지정해서 편하게 코드를 작성할 수 있는 기능입니다. 등록 방법은 아래와 같습니다.

## Template 등록
![](https://i.imgur.com/H4qR4aa.png)
1. IntelliJ Preferences
2. template 검색
3. 등록할 스타일 작성 (Markdown template를 등록할 경우 Markdown 항목에 추가)
4. Abbreviation: Template key 등록, Description: 간단한 설명 작성
5. 추가 하고 싶은 Template 등록
6. **하단의 Define에 사용할곳 반드시 정의** (Markdown 파일에서 사용할 것임으로 Markdown 선책)

## Template 사용법

![](https://i.imgur.com/mZuDMdU.gif)
* 위에서 작성한 `key`값을 입력하면 Template 불러옵니다.


## Template
```
---
layout: post
title: $END$
subtitle:
catalog: true
header-img: https://i.imgur.com/avC1Xor.jpg
thumbnail:
date: $date$
tags:
  -
---
```
* `$END$` :  Template 을 보시면 코드가 완성되고 포커싱이 `title : ` 쪽으로 가시는 것 볼 수 있씁니다. 키워드를 사용하면 Template 작성후 커서가 자동 이동 됩니다.
* `$date$` : 현재 시간을 자동으로 입력하게 합니다. (IntelliJ에서 작성하면 표시나 WebStorm 에서는 표시가 안되네요)

## 자주사용하는 Template
![](https://i.imgur.com/iQ40QYK.gif)

제가 가장 많이 사용하는 Template 입니다. `TODO` 입니다. 코드를 작성하면 추가적으로 필요한 작업, 기타등등 작업들은 모두 TODO로 적어 놓습니다. 해당 날짜와 작성인이 자동으로 작성되는 것을 확인할 수 있습니다.
