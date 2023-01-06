# csv関連についてまとめる

### csvファイルの読み取り
```swift
 func loadCSV(fileName: String) -> [String] {
        if let csvBundle = Bundle.main.path(forResource: fileName, ofType: "csv") {
            do {
                let csvData = try String(contentsOfFile: csvBundle, encoding: .utf8)
                let lineChange = csvData.replacingOccurrences(of: "\r", with: "\n")
                csvArray = lineChange.components(separatedBy: "\n")
                csvArray.removeLast()
            } catch {
                print("error")
            }
        }
        return csvArray
    }
```

### 解説
```swift
if let csvBundle = Bundle.main.path(forResource: fileName, ofType: "csv)
```
このコードによってファイルパスが取得される。

BundleとはSwiftでは以下のように説明されている
>A representation of the code and resources stored in a bundle directory on disk

ディスク上のバンドルディレクトリに格納されているコードとリソースを表現したもの。<br>

XcodeでいうところのTARGET → Build Phase → Copy Bundle Resources に含まれるものである。

基本的には Bundle Classはいくつかコンストラクターを持っているがよく使うのはmainである。このmain Bundleは現在実行されているコードを含むバンドルディレクトリを表現している。

最後にpathメソッドを使用してpathnameを取得する。<br>
forResourceでresource fileにファイル名をofTypeに検索するファイルの拡張子を指定する。

---

```swift
do {
                let csvData = try String(contentsOfFile: csvBundle, encoding: .utf8)
                let lineChange = csvData.replacingOccurrences(of: "\r", with: "\n")
                csvArray = lineChange.components(separatedBy: "\n")
                csvArray.removeLast()
            } catch {
                print("error")
            }
```
このコードはデータの読み取りを行なっている。
```swift
String(contentsOfFile: csvBundle, encoding: .utf8)
```
contentsOfFileでファイルへのパスを指定して、encodingで文字コードを指定する。

replacingOccurrencesメソッドは対象文字列の出現箇所を別の文字列に置き換えた新しい文字列を返す。
componentsメソッドはseparatedByで指定したもので文字列を分割する。

# 参考文献
[公式ドキュメント path](https://developer.apple.com/documentation/foundation/bundle/1409670-path)<br>
[公式ドキュメント Bundle](https://developer.apple.com/documentation/foundation/bundle)<br>
[公式ドキュメント init(contensOfFile:encoding:)](https://developer.apple.com/documentation/swift/string/init(contentsof:encoding:))<br>
[公式ドキュメント replacingOccurrences](https://developer.apple.com/documentation/foundation/nsstring/1412937-replacingoccurrences)<br>
[公式ドキュメント components](https://developer.apple.com/documentation/foundation/nsstring/1413214-components)