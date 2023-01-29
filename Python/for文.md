# for文の書き方に関してまとめる。

### 基本的な書き方
```python
for i in range(3):
  print(i)

# 出力
# １
# ２
# ３
```

 ### range()関数の使い方
```python
for i in range(3, 10):
  print(i)

# 出力
# 3
# 4
# 5
# 6
# 7
# 8
# 9
```
10は入らない点に注意

```python
for i in range(3,10,3):
  print(i)
# 出力
# 3
# 6
# 9
```
# 参考文献
[Pythonチュートリアル](https://docs.python.org/ja/3/tutorial/controlflow.html)