# CustomToast

Android 11 中将禁止使用自定义 View 的 Toast，本控件通过在 DecorView 中动态添加删除 View，加入淡入、淡出、滑动的动画效果，实现自定义 View 的 Toast 效果。

+ 普通 Toast 样式：CustomToast、SimpleToast
+ 类似系统通知的横幅效果：NotificationToast

### 引入依赖

```groovy
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

```groovy
dependencies {
    implementation 'com.github.hanjx-dut:CustomToast:Tag'
}
```



### 使用，需传入 Activity

```Java
// SimpleToast 底部 Toast，类似原生文字 Toast
SimpleToast.toastShort(this, textView);
// SimpleToast.toastLong(this, textView);
// SimpleToast.toastTime(this, textView, 1000);

// CustomToast 可自定义位置，持续时长，动画时长
new CustomToast()
        .setMargin(0, 0, 0, 900)
        .setShowTime(2000)
        .setShowAnimTime(300)
        .setDismissAnimTime(300)
        .setGravity(Gravity.CENTER_HORIZONTAL | Gravity.BOTTOM)
        .toastView(this, textView);

// NotificationToast 通知样式 Toast，可在任意方向弹出 Toast
new NotificationToast()
        .setGravity(Gravity.CENTER_HORIZONTAL | Gravity.BOTTOM)
        .setMargin(0, 0, 0, 600)
        .setSlideOffset(100)
        .setOrientation(NotificationToast.BOTTOM)
        .setShowTime(2000)
        .setShowAnimTime(400)
        .setDismissAnimTime(400)
        .toastView(this, textView2);
```

### 效果

![image](https://github.com/hanjx-dut/CustomToast/blob/master/demo.gif)