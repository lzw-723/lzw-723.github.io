---
layout: post
title : 解决ListView在ScrollView嵌套下只显示一项的Bug
subtitle:   薛定谔的ListView
date:       2019-8-28
author:     lzw-723                    
catalog:    true
img:        https://s1.ax1x.com/2020/03/21/8finL4.gif                        
tags:                                  
    - Android
---
## Bug发生原因

1.该listview存在于listview的嵌套下
2.该listview存在于scrollview下或者具有scrollview滑动功能的控件下

## Bug发生情景

适配器

![ListView's Adapter](https://i.loli.net/2019/08/28/4QmeJyxVnwfsXDP.png)

onItemClick时显示Adapter数据条数

![onItemClick时显示Adapter数据条数](https://i.loli.net/2019/08/28/QARr5WmV928oD3g.png)

输出

![Logcat](https://i.loli.net/2019/08/28/oKP3DwWrjTNynMp.png)

WTF！？！

![fuckin the bug](https://i.loli.net/2019/08/28/T3hGDfCuAIHrMm9.jpg)

## 解决办法(二选一）

### 1.根据item的高度和list的size来计算高度，然后重新在代码中对listview进行高度的设置

在setAdapter之后调用如下方法即可

```java
ListAdapter listAdapter = listView.getAdapter();
if (listAdapter == null) {
 return;
}
int totalHeight = 0;
 for (int i = 0, len = listAdapter.getCount(); i < len; i++) {
 // listAdapter.getCount()返回数据项的数目
 View listItem = listAdapter.getView(i, null, listView);
 // 计算子项View 的宽高
 listItem.measure(0, 0);
// 统计所有子项的总高度
totalHeight += listItem.getMeasuredHeight();
 }
 ViewGroup.LayoutParams params = listView.getLayoutParams();
params.height = totalHeight + (listView.getDividerHeight() *
(listAdapter.getCount() - 1));
// listView.getDividerHeight()获取子项间分隔符占用的高度
// params.height最后得到整个ListView完整显示需要的高度
 listView.setLayoutParams(params);
}
```

### 2.重写listview，对其禁止滑动

重写listview如下代码，然后在相应的布局中引用即可。

```java
public class MyListView extends ListView {  
     public MyListView(Context context, AttributeSet attrs){
            super(context, attrs);
        }
        // 设置不滚动
        public void onMeasure(int widthMeasureSpec, int heightMeasureSpec)
        {
            int expandSpec = MeasureSpec.makeMeasureSpec(Integer.MAX_VALUE >> 2,
                    MeasureSpec.AT_MOST);
            super.onMeasure(widthMeasureSpec, expandSpec);

        }
}

```
