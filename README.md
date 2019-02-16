# dabSDK
SDK中间件。


#### jitpack
> 官网： https://www.jitpack.io/#daBisNewBee/dabSDK/1.0

- 特点
    - 在线编译lib，无需提交额外的包
    - 支持github仓库
    - 支持aar、jar

- 主要步骤
    - lib
        - 在脚本里添加支持插件（首次）
        - 发布到github仓库
        - 创建release tag
    - app
        - 在脚本里添加jitpack仓库（首次）
        - 指定lib名字
        - sync

- 一些使用jitpack作为sdk仓库的注意点
- [使用步骤-官方](https://jitpack.io/docs/ANDROID/#publish-an-android-library)
