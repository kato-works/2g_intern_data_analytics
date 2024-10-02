# CSVファイルに保存してみる

## 本練習の目的

- データの保存・ロードを自由に行えるようになる
- 様々な保存形式を試してみる

## 以下を実行して結果を確認してみましょう

インデックスをつけずにファイルを保存する

```python
df.to_csv('export_test.csv', index=False)
```

インデックスをつけてファイルを保存する（どう違うか見てみる）

```python
df.to_csv('export_test_with_index.csv')
```

Excelでファイルを保存する

```python
df.to_excel('export_text.xlsx', index=False)
```

HTML形式で保存する

```python
df.to_html('export_text.html', index=False)
```
