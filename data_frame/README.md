# データフレームの取り扱いに慣れる

## 本練習の目的

- Pandas DataFrameの扱いに慣れる

## 以下を実行して結果を確認してみましょう

行数の取得

```python
len(df)
```

列の取り出し

```python
df['state']
```

行の取り出し

```python
df.iloc[2]
```

範囲での行の取り出し

```python
df.iloc[10:15]
```

行・列指定でのデータの抽出

```python
df.iloc[10:15, [0,2,3]]
```

ラベルで行・列を指定（ilocではなく、loc）

```python
df.loc[10:15, ['state', 'cityname']]
```

列のユニークな値を数える

```python
df['state'].value_counts()
```

ユニークな値を一覧で取得

```python
list(df['state'].value_counts().keys())
```
