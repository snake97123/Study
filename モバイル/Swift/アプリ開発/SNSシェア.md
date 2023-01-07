# SNSでシェアする機能に関してまとめる

コード例
```swift 
        let activityVC = UIActivityViewController(activityItems: [Any], applicationActivities: [UIActivity]?)
        self.present(activityVC, animated: true)
```

### 解説
UIActivityViewControllerは標準的なサービス（SNSへのコンテンツ投稿やメールやSNSでのアイテム送信など）を提供する。アプリはカスタムサービスを提供することができる。<br>
activityItemsにはアクティビティを実行するためのデータオブジェクトの配列が入る。

 # 参考文献
 [公式ドキュメント UIActivityViewController](https://developer.apple.com/documentation/uikit/uiactivityviewcontroller)<br>
 [SNSへのシェア機能の実装方法](https://ios-docs.dev/swiftui-uiactivityviewcontroller/)