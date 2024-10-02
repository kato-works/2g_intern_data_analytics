# データをクレンジングする

## 本練習の目的

- データのクレンジングについて学ぶ
- 異常データを探せるようになる

## 以下を実行して結果を確認してみましょう

pets_allowed にどのようなデータが存在するか確認する

```python
df['pets_allowed'].value_counts()
```

Monthly, 823はデータがおかしいので消す

```python
df = df[(df['pets_allowed'] != '823') & (df['pets_allowed'] != 'Monthly')]
df['pets_allowed'].value_counts()
```

Cats,Dogs,None は、Cats,Dogsに修正

```python
df.loc[df['pets_allowed'] == 'Cats,Dogs,None', ['pets_allowed']] = 'Cats,Dogs'
df['pets_allowed'].value_counts()
```

家賃が未入力の物件の削除

```python
df['price'] = df['price'].fillna(-1)
df = df[df['price'] >= 0]
```

price_type が Monthly 以外のものを削除

```python
df = df[df['price_type'] == 'Monthly']
```

クレンジングが完了したデータを保存する

```python
df.to_csv('../data/cleansed_apartment_data.csv', index=False)
```
