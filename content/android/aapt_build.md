# aapt build

- **linux 平台**

```
. build/envsetup.sh
lunch sdk-eng
make aapt
```

目前最新版本的代码,linux版本的aapt已经支持x86_64位,再64位系统编译默认为64位.
如果需要编译成x86版本,请添加参数`LOCAL_32_BIT_ONLY=true`
```
. build/envsetup.sh
lunch sdk-eng
make LOCAL_32_BIT_ONLY=true aapt
```

最新版本需要一个依赖库`libc++.so`,可以和bin文件放在同一个目录.
x86也可以放在`lib`目录下,x86_64可以放在`lib64`目录下.

使用`ccache`加快编译
```
export USE_CCACHE=1
export CCACHE_DIR=$(pwd)/.ccache
prebuilts/misc/linux-x86/ccache/ccache -M 50G
```

监控缓存状态
`watch -n1 -d prebuilts/misc/linux-x86/ccache/ccache -s`

- **windows 平台**

windows平台的文件也是再linux下生成的.
安装依赖包
`sudo apt-get install mingw32 tofrodos`

```
. build/envsetup.sh
lunch sdk-eng
USE_MINGW=1 make aapt
```

windows平台目前只有x86版本

- **mac ox 平台**

```
. build/envsetup.sh
lunch sdk-eng
make aapt
```

使用`ccache`加快编译
```
export USE_CCACHE=1
export CCACHE_DIR=$(pwd)/.ccache
prebuilts/misc/darwin-x86/ccache/ccache -M 50G
```
