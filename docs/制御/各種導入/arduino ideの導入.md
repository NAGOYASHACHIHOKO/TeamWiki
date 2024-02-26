---
layout: default
title: arduino ideの導入
parent: 各種導入
grand_parent: 制御
nav_order: 2
---
# arduino ideの導入  
NAGOYASHACHIHOKOでは組込み用のIDEとしてArduino IDE 2.3.1を使用しています。(2024/2月現在)  
制御班は全員、他の人も出来ればインストールしておきましょう。  

## Arduino IDEの導入  
arduinoの[ダウンロードページ](https://www.arduino.cc/en/software)に飛びます。  
<img src='img/arduino ideの導入_2024-02-18-01-23-27.png' width='350'>  
DOWNLOAD OPTIONから`Windows Win 10 and newer, 64 bits`を選択しダウンロードします。  
色々聞かれますが、JUST DOWNLOADを選択します。(たまには寄付してあげても良いのかも)  
<img src='img/arduino ideの導入_2024-02-18-01-27-34.png' width='350'>  

あとはインストーラの説明に沿ってインストールを進めていきます。  
インストールを完了するとArduino IDEが実行されます。初回起動時はWindowsセキュリティの警告が表示されるので、アクセスの許可を行います。  

基本設定を変更するため、メニューバーからファイル->基本設定...を選択します。  
<img src='img/arduino ideの導入_2024-02-18-01-31-22.png' width='180'>  
<img src='img/arduino ideの導入_2024-02-18-01-31-50.png' width='450'>  

上のようなウィンドウが表示されるので以下のように変更します。  
- エディター言語->日本語に変更  
- より詳細な情報を表示する->コンパイル,書き込み両方にチェック  

これで基本的な設定は完了です。  

## teensyの環境の設定  
SHACHIHOKOでメインで用いているteensyをArduino IDEに追加するため、Teensyduinoを導入します。  
[公式チュートリアル](https://www.pjrc.com/teensy/td_download.html)もあるので、こちらも参考にしよう  

まずは先ほどのファイル->基本設定...から基本設定ウィンドウを開きます。  
<img src='img/arduino ideの導入_2024-02-18-01-50-22.png' width='400'>  
追加のボードマネージャのURLに以下のURLを追加しOKを押下して設定を閉じます。  
`https://www.pjrc.com/teensy/package_teensy_index.json`  
次にボードマネージャを開きます。  
<img src='img/arduino ideの導入_2024-02-18-02-02-28.png' width='200'>  
ウィンドウ左側のボードアイコンを選択して開きます。  
検索欄に`teensy`と入力して、出てきたボードをインストールします。  
<img src='img/arduino ideの導入_2024-02-18-02-03-42.png' width='350'>  

これのインストールが完了すればteesnyの導入は完了です。  

## 各ライブラリの導入  
現在のプログラムで用いている追加が必要なライブラリを紹介します。  
ライブラリは先ほどのボードアイコンの下にあるライブラリアイコンからライブラリマネージャを開きます。  
<img src='img/arduino ideの導入_2024-02-18-02-06-12.png' width='200'>  
ボードと同様にライブラリ名を入力してインストールを行うことで導入できます。  

- Adafruit_BNO055  
    現在、メインで使っているgyroのライブラリです。依存関係を聞かれるので全てインストールしてください。  
- MsTimer2  
    タイマ割込み用のライブラリです。timer2(時間関係)を使うので多少他との干渉があったりします。  

恐らくこの2つ以外は標準で大丈夫なはず。。。  
足りないものがあれば制御班に報告してください。  

## 各プログラムの導入  
現状、運用されているプログラムを手元にcloneします  
変更等の作業を行う場合は[GitHubフローに従って](https://docs.github.com/ja/get-started/using-github/github-flow#github-%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AB%E5%BE%93%E3%81%86)ください  
RMUL2023プログラム(v6基板搭載のStandard Mk2プログラム)  
```
git clone https://github.com/RM-NAGOYASHACHIHOKO/RMUL2023_Program
```  
RM2024 歩兵プログラム  
```
git clone https://github.com/RM-NAGOYASHACHIHOKO/Mecanum_Standard
```  
RM2024 英雄プログラム  
```
git clone https://github.com/RM-NAGOYASHACHIHOKO/Mecanum_Hero
```  
RM2024 哨兵プログラム  
```
git clone https://github.com/RM-NAGOYASHACHIHOKO/Omni_Sentry
```  

gitの導入が済んでない人は[git,githubの導入](https://rm-nagoyashachihoko.github.io/TeamWiki/docs/%E5%88%B6%E5%BE%A1/%E5%90%84%E7%A8%AE%E5%B0%8E%E5%85%A5/git,github%E3%81%AE%E5%B0%8E%E5%85%A5.html)へ  