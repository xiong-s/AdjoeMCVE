# Adjoe MCVE(Minimal Complete Verifiable Example)

Adjoeの16KB Page Sizes未対応問題を再現できる最小限のサンプルです。  

このサンプルプロジェクトは以下の手順で作成されました。

- Unity 2021.3.48f1で新規プロジェクト作成
- プロジェクトのTarget PlatformをAndroidに変更
- Player Settings
  - Android
  - Identification
    - Minimum API Level = 24
    - Target API Level = 35
  - Configuration 
    - Scripting Backend = IL2CPP
    - Api Compatibility Level = .NET Framework
    - Target Architectures
      - ARMv7 = true
      - ARM64 = true
- OpenUPMで[EDM4U](https://github.com/googlesamples/unity-jar-resolver)を導入
- [Adjoe](https://docs.adjoe.io/rewarded-solutions/integration/playtime-sdk-for-android/get-started#step-3.-add-the-playtime-sdk-dependency)の.unitypackageを導入
- EDMでForce Resolve

このプロジェクトをビルドして、バイナリ（.apk）をAndroid Studio 2025.1.1のAnalyze APKで解析すれば16KB未対応の警告が出ます。

## English

This is a minimal sample that can reproduce the issue of Adjoe's 16KB Page Sizes not being supported.

This sample project was created following the steps below.

- Created a new project in Unity 2021.3.48f1
- Changed the project's Target Platform to Android
- Player Settings
  - Android
  - Identification
    - Minimum API Level = 24
    - Target API Level = 35
  - Configuration 
    - Scripting Backend = IL2CPP
    - Api Compatibility Level = .NET Framework
  - Target Architectures
    - ARMv7 = true
    - ARM64 = true
- Import [EDM4U](https://github.com/googlesamples/unity-jar-resolver) from OpenUPM
- Import the .unitypackage from [Adjoe Setup Guide](https://docs.adjoe.io/rewarded-solutions/integration/playtime-sdk-for-android/get-started#step-3.-add-the-playtime-sdk-dependency)
- Force Resolve in EDM

Build this project and analyze the binary (.apk) with Analyze APK in Android Studio 2025.1.1, and a warning will appear.
