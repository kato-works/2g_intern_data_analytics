# 環境構築手順

## 1. Gitのインストール

### 1.1 Git公式サイトからインストーラーをダウンロード

1. Git公式サイトにアクセスし、Windows用のGitインストーラーをダウンロードします。  
  [Git公式サイト](https://git-scm.com/)
2. ダウンロードが完了したら、インストーラーを実行します。

### 1.2 Gitのインストール手順

1. **インストーラーを起動**すると、セットアップ画面が表示されます。「Next」をクリックして進みます。
2. **インストールするコンポーネントの選択**画面では、デフォルト設定で問題ありません。「Next」をクリックします。
3. **エディターの選択**画面では、好みのエディターを選択します。特に指定がなければデフォルトの「Vim」を選択し「Next」をクリックします。
4. **PATH環境変数への追加設定**では、「Git from the command line and also from 3rd-party software」を選択して「Next」をクリックします。
5. **HTTPS接続でのプロトコルの選択**では、「Use the OpenSSL library」を選択し「Next」をクリックします。
6. **改行コードの扱い**では、「Checkout Windows-style, commit Unix-style line endings」を選択し「Next」をクリックします。
7. **その他の設定**はデフォルトのままで「Next」をクリックし、インストールが完了するまで待ちます。

### 1.3 インストール確認

1. コマンドプロンプトを開き、以下のコマンドを実行して、Gitが正しくインストールされたか確認します。

```bash
git --version
```

2. 正しくインストールされていれば、Gitのバージョンが表示されます。

### 1.4 リポジトリのクローン

```bash
cd 作業場所のフォルダ
git clone 
```

## 2. JupyterLabのインストール

### 2.1 Pythonのインストール

JupyterLabはPythonの環境が必要なので、Pythonがインストールされていない場合は以下の手順でインストールします。

1. Python公式サイトにアクセスして、Windows用のPythonインストーラーをダウンロードします。  
  [Python公式サイト](https://www.python.org/downloads/windows/)
2. インストーラーを実行し、「Add Python to PATH」にチェックを入れてから「Install Now」をクリックしてインストールします。

### 2.2 pipのバージョン確認

1. インストールが完了したら、コマンドプロンプトを開き、pipがインストールされているか確認します。  

```bash
pip --version
```

2. pipのバージョンが表示されれば問題ありません。

### 2.3 JupyterLabのインストール

1. 以下のコマンドをコマンドプロンプトに入力し、JupyterLabをインストールします。

```bash
python -m venv .venv
.venv\Scripts\activate.bat
pip install -r requirements.txt
```

2. 起動するには作業ディレクトリで以下のコマンドを実行します。

```bash
.venv\Scripts\activate.bat
jupyter-lab
```

2. ブラウザが自動で開き、JupyterLabのインターフェースが表示されます。

## データのダウンロード

カリフォルニア大学アーバイン校が様々なオープンデータを提供しておりダウンロードすることが出来ます。

Jupyter-Lab で download_apartment_for_rent_classified.ipynb を開いて、"Run"-"Run All Cells"とすると、データをダウンロードして、dataフォルダ以下にCSVファイルとして保存します。

```python
from ucimlrepo import fetch_ucirepo 
  
# データのダウンロード
apartment_for_rent_classified = fetch_ucirepo(id=555) 
  
# Pandas DataFrame型でのデータ取得
df = apartment_for_rent_classified.data.features 

# データフレームの表示
display(df)

# データのCSV保存
df.to_csv('data/apartment_for_rent_classified.csv', index=False)
```
