# React Native 原生模組

> 轉載請標明出處。

## 前言

> **[info] 原生模組（Native Module）與原生橋接（Native Bridge）為不同概念。**
>
> 前者將 Android/iOS 中由 Java/Swift/Obj-C 所撰寫的原生功能帶進 React Native 中，後者則可以將 React Native 程式整合進現有的 Android/iOS 專案中。

主要由 Facebook 開發的 **React Native** 技術框架經歷數年的發展，目前已經涵蓋了大多數的 Native App 功能，諸如地圖、相機、或是 GPS 應用等都有了良好的套件支援。

但即使如此，仍然有一部分原生功能沒有被放進 React Native API 中，同時經由特殊硬體構成的應用也沒辦法透過現成的 API 或第三方套件解決。

此時，我們就會需要透過 React Native 提供的**原生模組（Native Module）**機制來突破困境。

## 目標

暸解 Native Module 的**適用情境與優勢**，以及如何進行**開發流程與專案架構**；其次暸解如何透過 Native Module 機制**呼叫原生程式碼函式**，與如何**將原生端程式產生的結果回傳**到 React Native App 端。

最後會有幾個練習，作為透析 Native Module 範例的延伸。

## Sample Repo

- [iamcxa/sample-react-native-native-module](https://github.com/iamcxa/sample-react-native-native-module)