1. Cannot run program "/xx/build-tools/xx/aapt": error=2, No such file or directory

全新的Ubuntu14.04.1（64位）搭建好Android开发环境，编译出错：

    Error:Execution failed for task ':facebookSDK:processReleaseResources'.> Java.io.IOException: Cannot run program "/opt/sdk/build-tools/20.0.0/aapt": error=2, No such file or directory

我的sdk被放在了/opt目录下，aapt文件静静的躺在那里，权限也够，怎么会找不到呢？
原来是64位系统搞的鬼。
解决的方案就是安装几个32位的兼容库，如下：

    $ sudo apt-get install -y libc6-i386 lib32stdc++6 lib32gcc1 lib32ncurses5 lib32z1  

重新clean编译，问题不见了！
