---
layout: post
title: 액티비티 생명주기 (Activity LifeCycle)
date: 2020-02-25 00:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [액티비티 생명주기 (Activity LifeCycle), 안드로이드 (Android)] # add tag
---

<img src="https://user-images.githubusercontent.com/37543606/75252346-d80a3700-581f-11ea-9ddf-b8b37664425d.gif"/>





#### Activity LifeCycle

#### onCreate()

####  - Activity가 Launch되고 최초 실행



#### onStart()

#### - Activity가 보여지는 단계



#### onResume()

#### - Activity가 foreground로 나와 상호작용함



#### onPause()

#### - 다른 Activity로 이동시 onResume() 단계에서 호출, 다시 Activity로 돌아오면 onResume() 호출



#### onStop()

#### - 해당 Activity가 보이지않으면 onStop()을 호출, 다시 Activity로 돌아오면 onRestart() 거치어 onStart()가 호출

a

#### onDestroy()

#### - 시스템 메모리 부족이나 사용자가 Activity를 Finish() 하는 경우 호출



##### Java

```java
package com.shindorim.study;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.util.Log;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Toast.makeText(this, "시작", Toast.LENGTH_LONG).show();
        Log.d("onCreate", "최초 실행");
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.d("onStart", "Activity가 보여지는 단계");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.d("onResume", "Activity가 foreground로 나와 상호작용함");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.d("onPause", "다른 Activity로 이동시 onResume() 단계에서 호출, 다시 Activity로 돌아오면 onResume() 호출");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.d("onStop", "해당 Activity가 보이지않으면 onStop()을 호출, 다시 Activity로 돌아오면 onRestart() 거치어 onStart()가 호출");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.d("onDestroy", "시스템 메모리 부족이나 사용자가 Activity를 Finish() 하는 경우 호출");
    }
}
```



이미지 출처 : https://www.homeandlearn.co.uk/android/android_activity_lifecycle.html