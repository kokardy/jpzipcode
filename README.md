# jpzipcode
郵便番号から住所を取得するためのライブラリ


## Usage

```python

from jpzipcode import read_csv_file, read_official_URL, OFFICIAL_FILE_NAME
import os

# 日本郵便のサイトからダウンロードして郵便番号を取得
resolver = read_official_URL()
zips = resolver.resolve("5650871")

# ファイルを読み込んで取得
resolver = read_csv_file(os.path.join("ダウンロード", OFFICIAL_FILE_NAME))
zips = resolver.resolve("5650871")

print(zips) # [Zip(zip_code='5650871', address=Address(prefecture='大阪府', city='吹田市', town='山田丘'), address_kana=Address(prefecture='オオサカフ', city='スイタシ', town='ヤマダオカ'))]
```
