---
layout: post
title: 인텔리제이 Git 활용법
subtitle: IntelliJ Tip
catalog: true
header-img: 'https://i.imgur.com/avC1Xor.jpg'
tags:
  - IntelliJ
  - Tip
  - Git
thumbnail: 'https://i.imgur.com/6xFlHcv.png'
date: 2018-04-03 00:00:00
---


벡엔드 개발을 할 때 많은 틀을 사용합니다. Source Tree, Postman, Sequel Pro 등등 수없이 개발하다가 해당툴을 사용하기 위해서 왔다 갔다 하는 경우가 많습니다. 하지만 외부 툴을 사용하는 순간 뭔가 개발 흐름이 끊기는 느낌이 있어서 저는 거의 모든 작업을 인텔리제이에서 하는 것을 지향합니다. **이번 포스팅은 Source Tree 즉 Git 관련 툴을 대체하는 방법을 소개하겠습니다.** ***해당 기능의 단축키는 스크린샷 하단에 표시되있습니다.***

## Commit
![](https://i.imgur.com/6xFlHcv.png)

* Diff : 변경 이력이 있는 모든 파일에 대해서 Diff 기능을 제공합니다. Commit을 하기 전에 자신이 변경한 모든 파일에 대해서 한 번 꼼꼼하게 읽어 보는 습관을 갖는 것이 실수를 줄이는 가장 효율적인 방법이라고 생각합니다.
* Before Commit : **인텔리제이로 커밋을 했을 경우 얻을 수 있는 최고의 장점이라고 생각합니다. **간단하게 다루고 이 기능은 추후 포스팅을 통해서 다시 한번 다루겠습니다.
    * Check TODO:  //TODO 메시지가 남아 있을 경우 사용자에게 해당 TODO가 남아 있다고 알려줍니다.
    * Optimize imports : 사용하지 않은 imports를 제거해 줍니다.
    * Reformat Code : 인텔리제이에서 설정한 코드스타일로 변경 해줍니다.

## Push
![](https://i.imgur.com/TzF1dNk.png)
* 커밋한 내용을 레파지토리에 푸쉬 하는 기능입니다.

## Pull
![](https://i.imgur.com/pMhiJPi.png)
* Remote Repository에 변경 내역을 Pull 받는 기능입니다.

## Stash
![](https://i.imgur.com/ZIn63MI.png)

* Stash 기능은 아주 간단하게 소개하면 변경 내역을 임시저장 해놓는 기능입니다. 가령 다른 branch로 변경을 원할 때 변경 내역이 남아 있어 부득이하게 commit을 하는 경우가 있습니다. 그럴 때 stash 임시 저장소에 저장하면 편리하게 branch 간의 이동을 할 수 있습니다.
* 기본 단축키가 지정되있지 않아 `Find Action` 으로 stash 기능을 사용합니다.

## UnStash
![](https://i.imgur.com/kDCYgib.png)
* Stash 저장한 내역을 POP 하는 기능입니다.
* 기본 단축키가 지정되있지 않아 `Find Action` 으로 unStash 기능을 사용합니다.
* 저장한 메시지를 기반으로 선택하고 `Apply Stash`을 클릭하면 변경 내역을 불러옵니다.

## Share Project on Github
![](https://i.imgur.com/bOJ0X8n.png)
* 해당 프로젝트를 Github에 올리는 기능입니다.

## Branch
![](https://i.imgur.com/HJjPhjW.png)
* New branch, Checkout, Compare, Merge, Rebase 등등 다양한 기능들을 제공합니다.
