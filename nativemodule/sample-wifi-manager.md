# 呼叫原生模組範例：使用 Toast

## 初始化專案 - 新增樣板與專案

### Native module 架構說明

一個支援 Android / iOS 雙平台的 Native Module 專案內應該會包含以下結構：

```markdown
.
├──android
├──ios
├──index.js
├──package.json
└──README.md
```

### 建立 RN 專案

首先，在開始製作 Native Module 之前，要先手動新建一個 React Native 專案。

```bash
# 建立 React Native 專案
$ react-native init ProjectToast
```

### 產生樣板




#### 指令參數

`react-native-create-library` 支援選項參數，可以用來指定產生的 module 名稱以及 package 名稱等相關資訊。

```bash
Usage: react-native-create-library [選項] <名稱>

Options:

  -h, --help                                顯示說明
  -V, --version                             顯示版本號
  -p, --prefix <prefix>                     指定 library prefix (預設: `RN`)
  --module-prefix <modulePrefix>            指定 library 的 module prefix(預設: `react-native`)
  --package-identifier <packageIdentifier>  (Android only!) Android module 的 package name (預設: `com.reactlibrary`)
  --namespace <namespace>                   (Windows only!) The namespace for the Windows module
   (Default: The name as PascalCase)
  --platforms <platforms>                   工具將會產生哪些平台的樣板 (使用 `,` 逗號分隔; 預設: `ios,android,windows`)
```

預設的 module prefix 是 `react-native`，預設的 library prefix 則是 `RN`，如果給予的名稱是駝峰式命名，則將會自動將大寫與小寫轉換成 `-` 連結。

本教學將製作一個叫做 `MyAndroidToast` 的 module，如果套用預設的參數，那就會產出：

- module name：`react-native-my-android-toast`

這個名稱會作為 npm 套件的 package name 使用，也就是 ***React Native 專案將要 import/reqire 的來源套件名稱***。

- library name：`RNMyAndroidToast`

這個名稱則會 ***作為 native module 被 export 的對象物件***，同時也是 ***React Native 專案將要 import/require 之後的物件名稱***。

例如：

```javascript
// 亦即 import {library_name} from {module_name}
import MyAndroidToast from  'react-native-my-android-toast';
```

> #### 注意！

這裡要非常注意一點，所有的 `prefix` 與樣板內 Android/iOS 專案內所有的 class name 都是依據 `name` 參數產生，所以盡量第一次就決定好名稱，**事後要修改會非常麻煩**。

### 透過指令產生樣板

```bash
# 我們要建立一個叫做 MyAndroidToast 的 module，只有 Android 平台
$ react-native-create-library MyAndroidToast --platforms android

# 結果
➜  root react-native-create-library MyAndroidToast
While `RN` is the default prefix,
  it is recommended to customize the prefix.

📚  Created library MyAndroidToast in `./MyAndroidToast`.
🕘  It took 20ms.
➡️  To get started type `cd ./MyAndroidToast`

# 完成之後，記得要 yarn install
$ cd ./MyAndroidToast && yarn install
```


## Android Studio


## 參考
- [How to access a shared folder in VirtualBox? - Ask Ubuntu](https://askubuntu.com/questions/161759/how-to-access-a-shared-folder-in-virtualbox)