# SDK build

- 编译sdk

```
. build/envsetup.sh
lunch sdk-eng
make sdk
```

- 编译Windows SDK
`sudo apt-get install mingw32 tofrodos`

```
. build/envsetup.sh
lunch sdk-eng
make win_sdk
```
