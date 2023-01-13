# lsコマンドに関してまとめる

## lsコマンドとは
lsコマンドはフォルダ内のファイルを表示したりするコマンドのことである。

### ファイルサイズを表示する
```bash
ls -lh
```

### 表示するファイル数を制限する。
```bash
ls [ファイルまたはディレクトリ名] | head -10
```

### ディレクトリ数を調べる
```bash
ls -l | grep ^d | wc -l
```

# 参考文献
[@IT lsコマンド](https://atmarkit.itmedia.co.jp/ait/articles/1606/27/news018.html)<br>
[ディレクトリ数を調べる](https://linux.just4fun.biz/?%E9%80%86%E5%BC%95%E3%81%8DUNIX%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89/%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E6%95%B0%E3%82%92%E8%AA%BF%E3%81%B9%E3%82%8B)