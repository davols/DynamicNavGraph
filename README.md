Dummy project to try out DynamicNavHost - Want to use a dynamic features own included navigation graph. 

Following https://developer.android.com/guide/navigation/navigation-dynamic and reading https://medium.com/google-developer-experts/exploring-dynamic-feature-navigation-on-android-c803bdbbca9b

Quick links:
* [nav_graph_feature.xml](https://github.com/davols/DynamicNavGraph/blob/master/featurea/src/main/res/navigation/nav_graph_feature.xml)
* [activity.main.xml](https://github.com/davols/DynamicNavGraph/blob/master/app/src/main/res/layout/activity_main.xml) with  `android:name="androidx.navigation.dynamicfeatures.fragment.DynamicNavHostFragment"`
* [nav_graph.xml](https://github.com/davols/DynamicNavGraph/blob/master/app/src/main/res/navigation/nav_graph.xml) main graph with `<include-dynamic`
* [app/build.gradle](https://github.com/davols/DynamicNavGraph/blob/master/app/build.gradle) with `api` for deps.

It crashes but it should work?

```
2020-07-22 09:53:03.113 27187-27187/com.example.myapplication E/AndroidRuntime: FATAL EXCEPTION: main
    Process: com.example.myapplication, PID: 27187
    android.content.res.Resources$NotFoundException: com.example.featurea:navigation/nav_graph_featurea
        at androidx.navigation.dynamicfeatures.DynamicIncludeGraphNavigator.replaceWithIncludedNav(DynamicIncludeGraphNavigator.kt:95)
        at androidx.navigation.dynamicfeatures.DynamicIncludeGraphNavigator.navigate(DynamicIncludeGraphNavigator.kt:79)
        at androidx.navigation.dynamicfeatures.DynamicIncludeGraphNavigator.navigate(DynamicIncludeGraphNavigator.kt:40)
        at androidx.navigation.NavController.navigate(NavController.java:1049)
        at androidx.navigation.NavController.navigate(NavController.java:935)
        at androidx.navigation.NavController.navigate(NavController.java:868)
        at androidx.navigation.NavController.navigate(NavController.java:854)
        at androidx.navigation.NavController.navigate(NavController.java:842)
        at com.example.myapplication.StartFragment$onViewCreated$1.onClick(StartFragment.kt:16)
        at android.view.View.performClick(View.java:7125)
        at com.google.android.material.button.MaterialButton.performClick(MaterialButton.java:967)
        at android.view.View.performClickInternal(View.java:7102)
        at android.view.View.access$3500(View.java:801)
        at android.view.View$PerformClick.run(View.java:27336)
        at android.os.Handler.handleCallback(Handler.java:883)
        at android.os.Handler.dispatchMessage(Handler.java:100)
        at android.os.Looper.loop(Looper.java:214)
        at android.app.ActivityThread.main(ActivityThread.java:7356)
        at java.lang.reflect.Method.invoke(Native Method)
        at com.android.internal.os.RuntimeInit$MethodAndArgsCaller.run(RuntimeInit.java:492)
        at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:930)
2020-07-22 09:53:03.124 27187-27187/com.example.myapplication I/Process: Sending signal. PID: 27187 SIG: 9

```
