# CSVデータを読み込んで表示してみよう

## 本練習の目的

- CSVデータを読み込む
- データの表示の仕方に慣れる

## 以下を実行して結果を確認してみましょう

CSVファイルを読み込む

```python
import pandas as pd

file_path = '../data/apartment_for_rent_classified.csv'
df = pd.read_csv(file_path)
```

データフレームを表示する

```python
df
```

先頭10行を表示する

```python
df.head(10)
```

列の一覧を取得する

```python
df.columns
```

データの構造を取得する

```python
df.info()
```

データの統計情報を表示する

```python
df.describe()
```

特定の列だけ表示する

```python
df[['state', 'price', 'price_type']]
```

1行だけ取り出す

```python
df.iloc[10]
```
