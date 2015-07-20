# aapt build

- **linux 平台**

```
. build/envsetup.sh
lunch sdk-eng
make aapt
```

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
