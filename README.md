# CSVの回帰分析と予測

CSVをアップロードし、3種類の回帰モデルを比べてから、目的変数が空欄の行を予測するStreamlitアプリです。

## 起動

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
streamlit run 1-3.py
```

Windows PowerShellでは、次のコマンドで仮想環境を有効にします。

```powershell
.\.venv\Scripts\Activate.ps1
```

## CSVの形式

- 1列目に予測する値、2列目以降に予測に使う数値を置きます。
- 学習用の行は値を埋め、予測したい行は1列目を空欄にします。
- CSVはShift-JISで読み込みます。

## アプリの処理

データのプレビューと相関確認のあと、Linear Regression、SVR、Random Forestのスコアを比較します。テスト用に分けたデータでスコアを確認し、スコアが最も高いモデルで空欄の値を予測します。結果は画面で確認でき、CSVでも保存できます。

`cardata.csv` は自動車価格データのサンプルです。`IMG.JPG` はアプリ画面に表示する画像です。
