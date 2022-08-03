# how-to-flush-jetson-agx-xavier-nx

公式に書いてあるmicroSDカードにJetpackをFlushする方法です。
今回、試した、対象のエッジデバイスはJetson Xavier NX Developer Kitです。
エッジデバイス裏面に記載してある「Model P3518」はモデルを指しておりJetson Xavier NX Developer Kitにあたります。

### 必要な物

* Jetson Xavier NX Developer Kit
* micro-B USB
* ネイティブPC（Ubuntu 20.04）
* SDK Managerの環境

## インストール方法

### Jetson Nano Developer Kit SD Card Image  のダウンロード

NVIDIA Jetson Download Center

```  
https://developer.nvidia.com/embedded/downloads 
```  
 
該当するイメージファイル、Jetson NX Developer Kit SD Card Imageの対象のバージョンのImageを取得してください。
microSD Cardに対してimageを書きこみます。

Getting Started With Jetson Xavier NX Developer Kit

```  
https://developer.nvidia.com/embedded/learn/get-started-jetson-xavier-nx-devkit#intro
```  

「Write Image to the microSD Card」の項目を順番に実行してください。
macbookで実行する場合は「Command Line Instructions」を参考にすることをお勧めします。（EtcherというFlush用のソフトがありますがうまくできませんでした）

### NXを起動する

HDMIケーブルをNXに繋ぎ、電源を入れます。
その後、OSが起動して正常に起動できることを確認してください。
正常に起動できればOSのFlushは完了です。

### Jetson SDK Componentsをインストールする

Jetson SDK ComponentsはDeepstreamなどが含まれているAI系のコンポーネント群です。
Deepstream SDKなどを使用してビジョンAIを動かすにはSDK MangerからAI系のコンポーネント群をインストールさせる必要があります。
公式のインストールガイドは

```  
https://docs.nvidia.com/sdk-manager/install-with-sdkm-jetson/index.html
```  

をご確認ください。
SDK ManagerがインストールされているPCを起動し、microB USB経由でNXを繋いでください。
SDK Managerを起動してください。
### SDK Manager Step1
対象デバイスはJetson Xavier NX Developer Kitを選択してください。

Hostのチェックを外しDeepstreamにチェックを入れてください。

### SDK Manager Step2
OSのチェックを外してください。
Jetson SDK Componentsにチェックを入れてください。
インストールを実行してください。