---
layout:     post
title:      Aide笔记
subtitle:   
date:       2020-04-18
author:     BY gsyx
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
truetags:
    - Android
    - 笔记
---

****

## 目录

* [取消标题](#取消标题)

### 取消标题

只能放在setContentView或super.onCreate(savedInstanceState);的前面。
实例代码:
```
import android.app.Activity;
import android.os.Bundle;
import android.view.Window;

public class MainActivity extends Activity 
{
    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
		requestWindowFeature(Window.FEATURE_NO_TITLE);
        setContentView(R.layout.main);
    }
}
```

