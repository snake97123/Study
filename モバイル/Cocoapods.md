# Cocoapodsに関してまとめる。

### Cocoapodsとは
Cocoapodsはライブラリの管理ツールのことである。

インストール方法
```
sudo gem install cocoapods
```

cocoapodsのセットアップ
```
pod setup
``` 
ここでSetup completedと表示されたらOKです。

### Cocoapodを使用してライブラリをインストールする。

プロジェクトファイルに移動して、以下のコマンドを入力する
```
pod init
```
するとPodfileが作成される。<br>
以下のコマンドを入力してPodfileを開く
```
open Podfile
```

Podfileの中身は以下のようになっているためPods for プロジェクト名の下にインストールしたいライブラリ名を記入する。
```
# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'プロジェクト名' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for プロジェクト名
  pod インストールしたいライブラリ名
end
```

入力が完了したら以下のコマンドを入力する。
```
pod install
```
すると新しくPodfile.lock, Pods, quiz.xcworkspaceが作成される。

# 参考文献
[Cocoapods](https://cocoapods.org/)