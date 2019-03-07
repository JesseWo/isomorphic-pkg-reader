# isomorphic-pkg-reader
npm仓库中的官方版本更新不及时，有BUG，所以fork过来并在 `package.json` 中增加 `files` 字段.
在项目中直接通过以下方式进行依赖：
```json
...
"dependencies": {
    "isomorphic-pkg-reader": "git+https://github.com/JesseWo/isomorphic-pkg-reader.git",
    
  },
...
```

新增: node环境支持 withIcon
```javascript
const PkgReader = require('isomorphic-pkg-reader');
const reader = new PkgReader(pkgPath, extension, {
    withIcon: true,
    iconType: 'buffer',  // 'buffer' or 'base64', default value is 'buffer'
    searchResource: true
});
reader.parse(function (err, pkgInfo) {
  if (err) {
    console.error(err);
    return;
  }
  console.log('pkg info:', pkgInfo);   
});
```
---
Read IOS/Android package's(.apk/.ipa ) manifest info, for NodeJS/Webpack/Browserify.

## Introduction
For `.apk`, parse the `AndroidManifest.xml` and `resources.arsc` files, read all values listed in AndroidManifest.xml(both primitive and reference type), also you can get and show the icon of the apk file directly from the parsed result.

For `.ipa`, parse the `info.plist` and `embedded.mobileprovision` files, read all basic information in info.plist file, including the icon of the ipa file(already handled the crushed pngs).

## Removed

This repository have been moved to [here](https://github.com/TencentWSRD/isomorphic-pkg-reader) and will be maintained by our team there, please check that out.

This repository here under my personal account won't be updated or accept any PR anymore.
