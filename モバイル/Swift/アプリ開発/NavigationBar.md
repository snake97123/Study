# NavigationBarに関してまとめる。

### NavigationBarを隠したり表示したりする。
```swift
func scrollViewDidScroll(_ scrollView: UIScrollView) {
        let defaultOffset = view.safeAreaInsets.top
        let offset = scrollView.contentOffset.y + defaultOffset

        navigationController?.navigationBar.transform = .init(translationX: 0, y: min(0, -offset))
    }
```

### 解説
defaultOffset変数に画面のセーフエリアの上部からのオフセット値を格納する。その後にoffset変数にスクロールされたコンテンツのオフセットにdefaultOffsetの値を足したものを格納する。<br>
最後にtransformプロパティを使用して、y軸方向の移動量を選択する。