# QRコードの作り方に関してのまとめ
使うもの
・ ClFilter

以下の記事を参考にして作成した。</br>
[SwiftでQRコードを生成する](https://zenn.dev/mark_1975m/articles/b491bb9e9752c0)

QRコードに読み取らせたいURLの文字列をデータ型としていれる。</br>
データ型に変換する方法：dataメソッドを使用する。</br>
```swift
(例)let data = url.data(using: .utf8)
```
