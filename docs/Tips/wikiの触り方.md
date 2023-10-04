---
layout: default
title: wikiの触り方
nav_order: 3
parent: Tips
has_children: true 
---
# wikiの触り方  
基本的な流れはリポジトリにmarkdownを追加->gh-pagesブランチにpush->github actionがビルドしてくれるといった流れ  
前提条件  
- gitの導入
- githubのアカウント持っている
- wikiリポジトリのコントリビュータになっている

## ページの作成  
### トップレベルのページ作成  
機械や回路などの他のページの配下に入らないページのmarkdownには以下のように記述する  
```
---
layout: default
title: 機械
nav_order: 2
has_children: true 
---
```
layoutはdefaultを基本的に選択  
titleはページタイトル  
nav_orderにはページの表示順を(機械はTopPageに次いで2番目)  
has_childrenをtrueにすることで配下にページを作成できるようになる  

### 配下ページの作成
```
---
layout: default
title: 過去機体
parent: 機械
nav_order: 1
---
```
layout、title、nac_orderはトップと同じ  
parentには親となるページのタイトルを入力(ファイル名ではない)  

孫ページを作成する場合はgrand_parentも設定する
```
---
layout: default
title: SimulatorX
parent: シミュレータ
grand_parent: Tips
nav_order: 3
---
```

## 基本的な記法  
markdown。
[チュートリアル](https://qiita.com/ozin/items/0be04ada3e66eb88175d)とかを見ながら書きましょう。  
既存のページを参考にしてもらうのが良いと思います。  
[Jekyll の Markdown について](https://jekyll.otti.xyz/misc/markdown.html)  

## Tips
- プレビュー表示  
    [VSCodeでマークダウンのプレビューを右側に出す](https://qiita.com/_s_/items/b14ef34bb6d63719d92c)  
    記法が正しいかやレイアウトを見れるのでおススメ  
    基本的にこだわりが無ければVSCodeでの作成を推奨します  
- 画像の貼り付け  
    [Markdownでスクショ画像をペーストする](https://zenn.dev/ktechb/articles/968ff79f8f9c46a26ee5)  
    Shift+Win+sとかで撮ったスクショを張り付けたり出来る。とても便利  
    Insert Patternのおススメの設定はこれ  
    `<img src='img/${imageFileName}' width='100%'>`  
    画像のサイズとか変更出来る  
