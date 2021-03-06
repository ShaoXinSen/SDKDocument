# Gradle集成

### 导入SDK的aar

在SDK文件下的  `附件/libs`目录下存在4个aar文件：

1. gamesamba-sdk-3.3.4.aar（GameSamba SDK）
2. library-facebook.aar （Facebook SDK）
3. library-android-inapp-billing-v3.aar （谷歌支付 SDK）
4. library-samsung-inapp-v5.aar（三星商店 SDK）

将以上4个aar文件导入到主工程`libs` 目录下

### 配置主工程的  build.gradle

在主工程的 build.gradle 文件中，添加 dependencies。 根据自己项目的需求，添加不同的依赖即可。

```java
dependencies {
	compile fileTree(dir: 'libs', include: '*.jar')
	
	// 添加依赖。注意，版本号必须一致。
	// SDK基础功能 (必需)
	compile(name: 'gamesamba-sdk-3.3.4', ext: 'aar')
	// Facebook模块 (必需)
	compile(name: 'library-facebook', ext: 'aar')
	// Google支付模块 (必需)
	compile(name: 'library-android-inapp-billing-v3', ext: 'aar')
	// 三星商店支付模块（必需）
	compile(name: 'library-samsung-inapp-v5', ext: 'aar')
	
	// 腾讯bugly统计模块
    compile 'com.tencent.bugly:crashreport:latest.release'
    // Android支持模块
    final support_library_version = '25.3.1'
    compile "com.android.support:appcompat-v7:$support_library_version"
    compile "com.android.support:recyclerview-v7:$support_library_version"
    compile "com.android.support:cardview-v7:$support_library_version"
    compile "com.android.support:customtabs:$support_library_version"
    compile "com.android.support:support-annotations:$support_library_version"

    compile 'com.parse.bolts:bolts-android:1.4.0'
    // Google模块
    compile 'com.google.android.gms:play-services-auth:11.0.4'
    compile 'com.google.android.gms:play-services-analytics:11.0.4'
    compile 'com.google.android.gms:play-services-ads:11.0.4'
    // 网络请求模块
    compile 'com.squareup.okhttp3:okhttp:3.4.1'
    compile 'com.google.code.gson:gson:2.7'
}
```

**Note**: 如果你使用 `Gradle 3.0.0 或者更高版本`, 务必使用 `implementation` 关键字替代 `compile` 如下:

```java
dependencies {
	implementation fileTree(dir: 'libs', include: '*.jar')
	
	// 添加依赖。注意，版本号必须一致。
	// SDK基础功能 (必需)
	implementation(name: 'gamesamba-sdk-3.3.3', ext: 'aar')
	// Facebook模块 (必需)
	implementation(name: 'library-facebook', ext: 'aar')
	// Google支付模块 (必需)
	implementation(name: 'library-android-inapp-billing-v3', ext: 'aar')
	// 三星商店支付模块（必需）
	implementation(name: 'library-samsung-inapp-v5', ext: 'aar')
	
	// 腾讯bugly统计模块
    implementation 'com.tencent.bugly:crashreport:latest.release'
    // Android支持模块
    final support_library_version = '25.3.1'
    implementation "com.android.support:appcompat-v7:$support_library_version"
    implementation "com.android.support:recyclerview-v7:$support_library_version"
    implementation "com.android.support:cardview-v7:$support_library_version"
    implementation "com.android.support:customtabs:$support_library_version"
    implementation "com.android.support:support-annotations:$support_library_version"

    implementation 'com.parse.bolts:bolts-android:1.4.0'
    // Google模块
    implementation 'com.google.android.gms:play-services-auth:11.0.4'
    implementation 'com.google.android.gms:play-services-analytics:11.0.4'
    implementation 'com.google.android.gms:play-services-ads:11.0.4'
    // 网络请求模块
    implementation 'com.squareup.okhttp3:okhttp:3.4.1'
    implementation 'com.google.code.gson:gson:2.7'
}
```

{% hint style="info" %}
 注意：依赖包中名称和文件名称必须一致。
{% endhint %}



