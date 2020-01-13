---
layout: post
title: 리액트 생명주기(React LifeCylcle)
date: 2020-01-13 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [리액트 생명주기(React LifeCylcle), 리액트 (React) # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/72235415-71391180-3615-11ea-922b-2ef336aa294d.png" />

#### React LifeCycle



#### 컴포넌트가 초기 렌더링일 경우

|       Initial Render       | 설명                                                         |
| :------------------------: | ------------------------------------------------------------ |
| getDerivedStateFromProps() | 컴포넌트의 프로퍼티 값을 통해 상태를 업데이트<br />컴포넌트가 처음 렌더링될 때, 새로운 프로퍼티 값을 수신할 때 호출 |
|             ↓              |                                                              |
|          render()          | 컴포넌트로부터 엔더링될 콘텐트를 반환<br />컴포넌트가 DOM에서 처음 마운트될 때, 새로운 프로퍼티를 받을 경우, setState()를 사용할 경우 호출 |
|             ↓              |                                                              |
|    conponentDidMount()     | 컴포넌트가 DOM에 마운트된 후 호출<br />데이터를 가져오는 것과 같은 컴포넌트 초기화 작업을 수행 |



#### 컴포넌트가 업데이트될 때마다

|           Update           | 설명                                                         |
| :------------------------: | ------------------------------------------------------------ |
| getDerivedStateFromProps() | 컴포넌트의 프로퍼티 값을 통해 상태를 업데이트<br />컴포넌트가 처음 렌더링될 때, 새로운 프로퍼티 값을 수신할 때 호출 |
|             ↓              |                                                              |
|   shoudComponentUpdate()   | 현재의 상태 또는 프로퍼티 값과 새로운 상태, 프로퍼티 값을 비교<br />컴포넌트를 재 렌더링할 필요가 없다면 false을 리턴<br />컴포넌트를 더욱 효율적으로 만드는데 사용 |
|             ↓              |                                                              |
|          render()          | 컴포넌트로부터 엔더링될 콘텐트를 반환<br />컴포넌트가 DOM에서 처음 마운트될 때, 새로운 프로퍼티를 받을 경우, setState()를 사용할 경우 호출 |
|             ↓              |                                                              |
| getSnapshotBeforeUpdate()  | 실제로 DOM에 커밋되기 전에 컴포넌트의 DOM 요소에 직접 작업을 수행<br />render()와 달리 비동기적이지 않음<br />render()를 사용하면 호출될 때와 변경 사항이 DOM에 실제로 적용될 때의 사이에 DOM 구조를 변경 |
|    conponentDidMount()     | 컴포넌트가 DOM에 마운트된 후 호출<br />데이터를 가져오는 것과 같은 컴포넌트 초기화 작업을 수행 |



이미지 출처 : https://blog.bitsrc.io/react-16-lifecycle-methods-how-and-when-to-use-them-f4ad31fb2282