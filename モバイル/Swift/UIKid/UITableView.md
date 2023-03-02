# UITableViewに関してまとめる。

### UITableViewとは
テキストなどのデータを行単位で出力することができるようにするものである。

### 基本的な実装方法
1. Xcodeで新しいprojectを作成する。作成すると以下のようなコードが生成される。
```swift

import UIKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()   
    }
}
```

2. 以下のように記述する。
```swift
import UIKit

class ViewController: UIViewController {
    
    var items: [String] = ["item1", "item2", "item3", "item4", "item5"]
    
    private let sampleTable: UITableView = {
        let table = UITableView()
        table.register(UITableViewCell.self, forCellReuseIdentifier: "cell")
        return table
    }()

    override func viewDidLoad() {
        super.viewDidLoad()
        
        sampleTable.frame = view.frame
        view.addSubview(sampleTable)
        sampleTable.dataSource = self
    }
    
}

extension ViewController:UITableViewDataSource {
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return items.count
    }
    
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = UITableViewCell()
        cell.textLabel?.text = items[indexPath.row]
        return cell
    }
}
```
buildすると以下の画像のように表示される。
![スクリーンショット 2023-03-02 15 27 07](https://user-images.githubusercontent.com/73522198/222348428-9c5bdf84-399b-481e-ad80-7c2782f9bd9f.png)

3. 解説
```swift
 private let sampleTable: UITableView = {
        let table = UITableView()
        table.register(UITableViewCell.self, forCellReuseIdentifier: "cell")
        return table
    }()
```

UITableView型のオブジェクトの作成を行い、registerメソッドを使用して、Table内で表示するCellの登録をしています。その後はreturnでtableをかえします。

```swift 
        sampleTable.frame = view.frame
        view.addSubview(sampleTable)
        sampleTable.dataSource = self
```

作成したUITableViewの大きさを指定し、UIViewControllerのインスタンスであるselfを代入します。

```swift 
extension ViewController:UITableViewDataSource {
    func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return items.count
    }
```
ここでtableViewの各セクションに表示されるセルの数を指定します。

```swift
    func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = UITableViewCell()
        cell.textLabel?.text = items[indexPath.row]
        return cell
    }
}
```
ここでは表示されるCellを生成します。

# 参考文献
[Apple Document](https://developer.apple.com/documentation/uikit/uitableview)<br>
[UITableViewの使い方](https://qiita.com/abouch/items/3617ce37c4dd86932365)