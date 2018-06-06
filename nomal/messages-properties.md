---
layout: post
title: 인텔리제이 다국어 message properties
subtitle: Intellij Tip
catalog: true
header-img: 'https://i.imgur.com/avC1Xor.jpg'
tags:
  - Intellij
  - message properties
thumbnail: 'https://i.imgur.com/1rPFIE1.png'
date: 2018-06-06 00:00:00
---


인텔리제이의  다국어 message properties 기능을 소개하려 합니다.


## messages.properties 생성
![](https://i.imgur.com/qLq9yRu.png)

원하는 디렉터리에서 파일을 생성하실 때 Resource Bundle 선택합니다.

## Locales 추가
![](https://i.imgur.com/cx4BUD0.png)

하단의 + 버튼을 눌러서 원하는 Locales를 추가합니다. 추가하실 때는 [ISO_639](https://ko.wikipedia.org/wiki/ISO_639) 표준을 따르는 것을 추천해 드립니다. Alpha-3, Alpha-2 둘 중 선택하되 일괄되게 적용 하는 것이 좋다고 생각합니다.
본 예제에서는 kr, en을 추가했습니다.

## 추가된 messages.properties 파일
![](https://i.imgur.com/CqePrKL.png)

디폴트 messages.properties 및 위에서 추가시킨 kr, en 파일들도 같이 생성된 걸 확인할 수 있습니다.

## message 작성
![](https://i.imgur.com/1rPFIE1.png)

1. 아무 messages.properties 선택하시고 하단의 Resource Bundle를 클릭 합니다.
2. messages.properties의 key 값을 입력합니다.
3. 오른쪽 messages.properties 알맞는 메시지를 추가합니다.


Resource Bundle 탭에서 에서는 여러 곳에 있는 messages.properties 쉽게 추가, 삭제, 변경 작업을 쉽게 할 수 있습니다.