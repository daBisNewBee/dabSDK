# dabSDK
SDK中间件。


#### jitpack仓库
> 官网： https://jitpack.io

- 特点
    - 在线编译lib，无需提交额外的包（在jitpack的"Log"可以查看编译日志）
    - 支持github仓库
    - 支持aar、jar

- 主要步骤
    - lib
        - 在脚本里添加支持插件（首次）
        - 发布到github仓库
        - 创建release tag(实际：本地创建tag提交也可以，在github手动创建release有点麻烦)
        - 升级：提交代码、提交tag
    - app
        - 在脚本里添加jitpack仓库（首次）
        - 指定lib名字
        - sync

- 一个发布到jitpack的aar文件清单：

```
添加后缀可直接打开对应文件
https://www.jitpack.io/com/github/daBisNewBee/dabSDK/1.1/
build.log
dabSDK-1.1-sources.jar
dabSDK-1.1.aar
dabSDK-1.1.pom
dabSDK-1.1.pom.md5
dabSDK-1.1.pom.sha1

```
- 一个app依赖的lib名字规则：

```
implementation 'com.github.daBisNewBee:dabSDK:1.1'

daBisNewBee: 必须为github的用户名
dabSDK：repo名称
1.1：tag名称

```


#### JCenter仓库和 Maven Central仓库 的比较
- 相同
    - 性质：都属于maven仓库
        - Apache Maven是Apache开发的一个工具，提供了用于贡献library的文件服务器
        - 总的来说，只有两个标准的Android library文件服务器：jcenter 和  Maven Central
    - 作用：都用来提供jar、aar等，上传到哪个取决于开发者
- 不同
    - 由不同的公司维护
        - JCenter： bintray.com
        - Maven Central：sonatype.org
    - 名称不同
        - jcenter()
            - 等同于：maven{ url "http://jcenter.bintray.com" }
        - mavenCentral()
    - 开发者上传lib的难易程度不同
        - mavenCentral：困难
        - jcenter：简单
- 总结
    - jcenter较好。东西多，速度快
    - 全世界最大的Java仓库，因此在Maven Central 上有的，在jcenter上也极有可能有。换句话说jcenter是Maven Central的超集。
    - 上传lib简单
- 举例
    - [腾讯bugly](https://bugly.qq.com/docs/user-guide/instruction-manual-android/?v=20190108103135#_2)
- bugly在两种仓库下的比较：

```
http://jcenter.bintray.com/com/tencent/bugly/crashreport/2.8.6/
crashreport-2.8.6-javadoc.jar
crashreport-2.8.6-javadoc.jar.asc
crashreport-2.8.6-sources.jar
crashreport-2.8.6-sources.jar.asc
crashreport-2.8.6.aar
crashreport-2.8.6.aar.asc
crashreport-2.8.6.pom
crashreport-2.8.6.pom.asc

https://repo1.maven.org/maven2/com/tencent/bugly/crashreport/2.8.6/
crashreport-2.8.6.aar                             2018-12-03 14:40    236336
crashreport-2.8.6.aar.asc                         2018-12-03 14:40       475
crashreport-2.8.6.aar.md5                         2018-12-03 14:40        32
crashreport-2.8.6.aar.sha1                        2018-12-03 14:40        40
crashreport-2.8.6.pom                             2018-12-03 14:40      1102
crashreport-2.8.6.pom.asc                         2018-12-03 14:40       475
crashreport-2.8.6.pom.md5                         2018-12-03 14:40        32
crashreport-2.8.6.pom.sha1                        2018-12-03 14:40        40
```

#### 其他仓库：
- ivy仓库
    - 用的较少
- 私有maven：
    - Twitter的Fabric.io：maven { url 'https://maven.fabric.io/public' }

- 参考
    - [使用步骤-官方](https://jitpack.io/docs/ANDROID/#publish-an-android-library)
    - [中文步骤](https://www.jianshu.com/p/005fe5ac5c84)
    - [Android Studio将项目发布到Maven仓库（3种方式最新最全）:发布到本地仓库、局域网仓库](https://blog.csdn.net/xmxkf/article/details/80674232)
    - 对几种仓库的原理解释的比较好[把自己的库发布到jcenter/maven/jitpack](https://www.cnblogs.com/gccBlog/p/7093978.html)
    - 制作本地maven比较好的一篇[Android Library打造自己的SDK，并Maven发布](https://www.jianshu.com/p/6c1d2688ed2d?from=jiantop.com)