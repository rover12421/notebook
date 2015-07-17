# android build

- Build

``` bash
. build/envsetup.sh
lunch aosp_arm-eng
jdk-switch openjdk7
export USE_CCACHE=1
mkdir -p $(pwd)/.ccache
export CCACHE_DIR=$(pwd)/.ccache
prebuilts/misc/linux-x86/ccache/ccache -M 50G
make -j4
```

- 查看缓冲状态

`watch -n1 -d prebuilts/misc/linux-x86/ccache/ccache -s`

- 编译指定模块

`mmm $(Dir)`

- 重新打包`system.img`

`make snod`

- 启动模拟器

```bash
. build/envsetup.sh
lunch aosp_arm-eng
export PATH=$(pwd)/out/host/linux-x86/bin:$PATH
export ANDROID_PRODUCT_OUT=$(pwd)/out/target/product/generic
emulator -partition-size 1024
```

- 生成idea项目文件

```bash
mmm development/tools/idegen/
./development/tools/idegen/idegen.sh
```

---

参考:
- https://source.android.com/source/building.html
