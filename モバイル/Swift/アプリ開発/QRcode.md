# QRコードの作り方に関してのまとめ
使うもの
・ ClFilter

以下の記事を参考にして作成した。</br>
[SwiftでQRコードを生成する](https://zenn.dev/mark_1975m/articles/b491bb9e9752c0)<br>
[すいすいswift](https://swiswiswift.com/2018-03-07)

QRコードに読み取らせたいURLの文字列をデータ型としていれる。</br>
データ型に変換する方法：dataメソッドを使用する。</br>
```swift
let url = "http://example.com"
let data = url.data(using: .utf8)
```

QRcodeの生成
```swift
let qr = CIFilter(name: "CIQRCodeGenerator", parameters: ["inputMessage": data, "inputCorrectionLevel": "M"])!
let sizeTarnsform = CGAffineTransform(scaleX: 10, y: 10)
let qrImage = qr.outputImage!.transformed(by: sizeTransform)
let context = CIContext()
let cgImage = context.createCGImage(qrImage, form: qrImage.extent)
let uiImage = UIImage(cgImage: cgImage!)
```
### 解説
CIFilterとはCore Image filterを設定するために使用するプロパティのことであり、nameに指定して設定することができる。CIQRCodeGeneratorはQRコードを作るためのプロパティである。inputMessageではORコードにする値を指定し、inputCorrectionLevelは誤り訂正レベルを指定する。詳しくは以下の記事を参考にする。<br>
[Core Image Filter Reference](https://developer.apple.com/library/archive/documentation/GraphicsImaging/Reference/CoreImageFilterReference/index.html#//apple_ref/doc/filter/ci/CIQRCodeGenerator)<br>

CGAffineTransformメソッドは2Dグラフィックスを描くときに用いるアフィン変換行列のことである。アフィン変換とは画像の拡大、回転などを行列を使って座標変換することである。<br>
transformed(by:)は元の画像のアフィン変換後の画像を返す。これによってqrImageにアフィン変換後の画像が格納される。<br>
CIContextは画像処理結果をレンダリングしたり、画像解析を行うための評価コンテキストをしたりするためのクラスである。<br>
createCGImageはCore Image イメージオブジェクトの領域からQuartz 2Dイメージを作成する。

---
QRコードの表示
```swift
let qrImageView = UIImageView()
qrImageView.contentMode = .scaleAspectFit
qrImageView.frame = self.view.frame
qrImageView.image = uiImage
self.view.addSubview(qrImageView)
```
### 解説
qrImageView.contentMode = .scaleAspectFitにすることで、アスペクト比を維持した状態でビューのサイズにあうようにコンテンツを拡大縮小してくれる。