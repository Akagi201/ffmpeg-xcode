# ffmpeg-xcode

ffmpeg xcode project

## build steps

### step 1 编译 ffmpeg

* `tar xvf ffmpeg-3.0.2.tar.bz2`
* `cd ffmpeg-3.0.2`
* `./configure --enable-debug`
* `make -j8`

### step 2 新建一个空的 xcode 项目

* Create a new Xcode project
* 新建一个空的 xcode 项目
![step2-1](assets/step2-1.png)
![step2-2](assets/step2-2.png)
* 项目保存路径与`ffmpeg-3.0.2`同级.
![step2-3](assets/step2-3.png)

### step 3 添加 `ffmpeg-3.0.2` 源码目录进 `ffmpeg-xcode` 项目中

* 拖进去
![step3-1](assets/step3-1.png)
* 不要勾选下面这个选项
![step3-2](assets/step3-2.png)
* 接着一点要选 `ffmpeg-xcode`, 否则看代码时, 不可以跳转. 写代码时不会有提示.
![step3-3](assets/step3-3.png)

### step 4 添加头文件搜索路径

* 到这里就可以实现头文件跳转了. 要等待处理完毕才可以点击头文件或者类来查看代码.
![step4](assets/step4.png)

### step 5 添加一个 target

* `File -> New -> Target -> OS X -> Other -> External Build System`
![step5-1](assets/step5-1.png)
* target 命名为 `ffmpeg-make`
![step5-2](assets/step5-2.png)
* target 切换到 `ffmpeg-make`
![step5-3](assets/step5-3.png)

### step 6 修改 `ffmpeg-make` 源码路径配置

* 修改 `ffmpeg-make` 源码路径
![step6](assets/step6.png)

### step 7 修改 `ffmpeg-make` 命令行参数

* 修改命令行参数
![step7-1](assets/step7-1.png)
* 修改可执行命令
![step7-2](assets/step7-2.png)

### step 8 添加断点(ffplay.c->main函数), 点击 run

![step8](assets/step8.png)
