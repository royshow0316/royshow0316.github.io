---
layout: post
title:  "將NumberPicker放入字串"
date:   2016-09-05 13:49:31 +0800
categories: Android
---

## 介紹
此篇將介紹，如何在NumberPicker裡面放入字串。

## 設置NumberPicker
先設定NumberPicker，將字串加入到NumberPicker，以NumberPicker的方式呈現。

{% highlight xml %}
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/activity_main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="com.royshow.gsontest.MainActivity">

    <NumberPicker
        android:id="@+id/showNumberPicker"
        android:layout_width="200dp"
        android:layout_height="wrap_content"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_marginLeft="60dp"
        android:layout_marginTop="40dp" >
    </NumberPicker>
</RelativeLayout>
{% endhighlight %}

先將NumberPicker放入字串，並初始值。
{% highlight java %}
public class MainActivity extends AppCompatActivity {

    private NumberPicker showNumProjectPicker;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        numberPicker = (NumberPicker) findViewById(R.id.showNumberPicker);

        String[] items = {"test1", "test2", "test3", "test4"};
        numberPicker.setMinValue(0);
        numberPicker.setMaxValue(items.length - 1);
        numberPicker.setDisplayedValues(items);
        numberPicker.setWrapSelectorWheel(false);
        numberPicker.setDescendantFocusability(NumberPicker.FOCUS_BLOCK_DESCENDANTS);
            }
}
{% endhighlight %}

## 執行結果
![Result](/image/NumberPicker/Result.png){:class="img-responsive" height="500px" width="300px"}



[程式碼已放上Github](https://github.com/royshow0316/NumberPickerTest){:target='_blank'}

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
