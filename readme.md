    <!--秒开方案-->
    <!-- app 冷启动时间-->
    <!-- 用户从手机桌面点击app 一直到启动页面的Activity调用onCreate方法之间的这个时间-->
    <!-- 在这段时间内发生了什么呢-->
    <!-- 当打开一个activty的时候如果该Activity所属的Application还没有启动
         那这个系统回味这个activity创建一个进程(每创建一个进程就会调用一次
         所以Application的onCreate()方法会被调用多次）在进程创建和初始化中
         会消耗一些时间在这个事件里WindowManager 会先加载app里主题样式里的
         窗口背景(WindowBackground)作为预览元素然后才真正加载布局如果事件长
         默认的北京又是黑色或者白色这样会给用户造成错觉 ->App 卡不流畅也就
         影响了用户体验  所以我们通过修改默认的windowBackground来达到优化
         或者秒开的效果本质上是没有变化的 只是从视觉感官上有区别-->
    <!--消除启动时的白屏/黑屏 换成指定的背景图或者颜色-->
    <!-- 更换指定颜色 或者背景-->
    <style name="AppWelcome" parent="AppTheme">
        <item name="android:windowBackground">@color/colorAccent</item>
    </style>
    <!--使用此方案 不能继承AppCompatActivity 直接继承Activity就行了-->
    <!--启动时设置成透明造成系统卡顿的假象 真是损啊这招-->
    <!--换成透明色-->
    <style name="AppWelcome1" parent="android:Theme.Translucent.NoTitleBar.Fullscreen" />
    <!--也可以使用layerlist的方式-->
    <!-- 设置Splash-->
    <style name="SplashTheme" parent="Theme.AppCompat.NoActionBar">
        <item name="android:windowBackground">@drawable/background_splash</item>
    </style>