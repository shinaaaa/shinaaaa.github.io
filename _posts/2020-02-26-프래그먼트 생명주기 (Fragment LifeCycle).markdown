---
layout: post
title: 프래그먼트 생명주기 (Fragment LifeCycle)
date: 2020-02-26 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [프래그먼트 생명주기 (Fragment LifeCycle), 안드로이드 (Android)] # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/75350395-c68d6180-58e9-11ea-8448-03000e4067d8.png"/>





### Fragment LifeCycle

#### onAttach()

- Activity에 attach될 때



#### onCreate()

-  리소스 초기화, UI초기화 불가능



#### onCreateView()

- UI 초기화



#### onActivityCreated()

- Fragment 생성 이후 호출



#### onStart()

- Fragment를 보이도록함



#### onResume()

- Fragmet 상호작용하는 부분



#### onPause()

- 다른 Activity가 foreground되면 호출. backstack 상태로 변환



#### onStop()

- 다른 Activity가 화면을 완전히 가리면 호출. 해당 Activity 복원 가능



#### onDestroyView()

- Fragment와 관련된 view 제거



#### onDestroy()

- onDestroyView()에서 view 제거 후 호출



#### onDetach()

- Fragment가 Activity와 떨어지면 호출



이미지 출처 : https://developer.android.com/guide/components/fragments?hl=ko