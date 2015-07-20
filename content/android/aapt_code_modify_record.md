# aapt code modify record

- 不检查文件名是否是关键词

PATH:`frameworks/base/tools/aapt/AaptAssets.h`
```cpp
bool check_valid_symbol_name(const String8& symbol, const SourcePos& pos, const char* label) {
    //[Rover12421]
    return true;
//        if (valid_symbol_name(symbol)) {
//            return true;
//        }
//        pos.error("invalid %s: '%s'\n", label, symbol.string());
//        return false;
}
```

- 不检查框架apk中是否有`AndroidManifest.xml`文件
原先是不检查的,后来加载apk都会通过是否包含`AndroidManifest.xml`文件来判断是否是合法的apk.

PATH:`frameworks/base/libs/androidfw/AssetManager.cpp`
```cpp
//    // Check that the path has an AndroidManifest.xml
//    Asset* manifestAsset = const_cast<AssetManager*>(this)->openNonAssetInPathLocked(
//            kAndroidManifest, Asset::ACCESS_BUFFER, ap);
//    if (manifestAsset == NULL) {
//        // This asset path does not contain any resources.
//        delete manifestAsset;
//        return false;
//    }
//    delete manifestAsset;
```
