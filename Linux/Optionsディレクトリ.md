# Optionsディレクトリの書きかたに関してまとめる。

## 基本的な記述方法
```bash
< Directory /var/www/>
    Options[+|-]オプション[[+|-]オプション]
</Directory>
```
## 代表的なオプション
１.All・・・MultiViews以外の全ての機能を有効にする。
２.None・・・すべての機能を無効にする。
３.FollowSymLinks・・・シンボリックリンクをたどることを許可する。
４.Indexes・・・ファイル一覧の表示を行う。

## 記入例
### ディレクトリ一覧表示の無効化
```bash
< Directory /var/www/>
    Options -Indexes 
</Directory>
```
これでディレクトリ一覧表示が行われなくなる。

## 注意点
変更をおこなったあとにはApacheなどの再起動を忘れずに行うようにする。

