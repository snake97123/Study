# Color Pickerに関してまとめる

### Color Pickerとは
Color Pickerとは色がグラデーションのように画面に表示されそこから直感的に選択することが可能になっている機能のことである。

### サンプルコード
```swift
import SwiftUI

struct ContentView: View {
    @State private var bgColor1 = Color(.red)
    @State private var bgColor2 = Color(.blue)
    var body: some View {
            NavigationStack {
                bgColor1
                HStack(spacing: 10){
                    VStack {
                        ColorPicker("Select Background Color",selection: $bgColor1)
                        ColorPicker("Select Navigation Bar  Color",selection: $bgColor2)
                    }
                }
                .navigationTitle("Color Picker")
                .toolbarBackground(bgColor2, for: .navigationBar)
                .toolbarBackground(.visible, for: .navigationBar)
            }
    }
    
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

```

### 解説
```swift
 ColorPicker("Select Background Color",selection: $bgColor1)
 ```
 この１行でColorPickerを表示させることが可能である。<br>
 selectionで設定した変数へColorPickerで選択した色をバインドさせます。

 ```swift
@State private var bgColor1 = Color(.red)
 ```
 変数を@Stateを使って設定します。この例では初期値として赤色を設定している。

 ```swift
var body: some View {
            NavigationStack {
                bgColor1
           // 以下省略
 ```
 あとは色を反映したいところで使うと良い。

 # 参考文献
 [公式ドキュメント ColorPicker](https://developer.apple.com/documentation/swiftui/colorpicker)