# proguard
Android 混淆

例如：
cmbkeyboard.jar 已经做了混淆，集成的APP混淆后可能对SDK调用有影响，有两种解决办法（自选一种）：
1、APP里不再对cmbkeyboard.jar做混淆
2、增加如下混淆配置：

-keepclasseswithmembers class cmb.pb.util.CMBKeyboardFunc {
    public <init>(android.app.Activity);
    public boolean HandleUrlCall(android.webkit.WebView,java.lang.String);
    public void callKeyBoardActivity();
}	
