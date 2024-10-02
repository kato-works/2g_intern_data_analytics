# データを検索してみる

## 本練習の目的

- データの検索を行い、好きなデータを取り出せるようになる
- 絞り込んだデータを保存して、ファイルのロード時間を短くする

## 以下を実行して結果を確認してみましょう

カリフォルニア（CA）のデータのみ抽出する

```python
df_ca = df[df['state'] == 'CA']
df_ca
```

行番号を振りなおす

```python
df_ca = df_ca.reset_index(drop=True)
df_ca
```

家賃が$1,000-以下の物件を検索する

```python
df[df['price'] < 1000]
```

カリフォルニアで家賃が$1,000-以下の物件を検索する

```python
df[(df['state'] == 'CA') & (df['price'] < 1000)]
```

絞り込んだデータに対して、列を指定して保存する

```python
df_tmp = df[(df['state'] == 'CA') & (df['price'] < 1000)][['cityname', 'price', 'square_feet', ]]
df_tmp.to_csv('filtered_data.csv', index=False)
df_tmp
```

読み込んでみる（早いはず）

```python
pd.read_csv('filtered_data.csv')
```
