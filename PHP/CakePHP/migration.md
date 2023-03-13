# Migrationに関してまとめる。

### 既存のデータベースをMigrationファイルにする。
```sql
bin/cake bake migration_snapshot Initial
```
これを実行することで、YYYYMMDDHHMMSS_Initial.phpと呼ぶマイグレーションファイルが作成される。

### 2つのデータベース間の状態の差分を生成する。
```sql
bin/cake bake migration_diff NameOfTheMigrations
```

### ステータスの確認
```sql
bin/cake migrations status
```

### マイグレーションを戻す。
```sql
bin/cake migrations rollback
```

### マイグレーションを実行する。
```sql
bin/cake migrations migrate 
```

# 参考文献
[CakePHP Cookbook](https://book.cakephp.org/migrations/2/ja/index.html)