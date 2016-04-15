# はじめに

本家様です

[hakobe/anime_recommend](https://github.com/hakobe/anime_recommend)

[今季見るべきアニメを機械学習で推薦する - はこべブログ ♨](http://hakobe932.hatenablog.com/entry/2016/04/15/142756)

何か素晴らしいものが公開されたので利用できるように環境を整えてみた

## 手順

### 1 まず、アニメの情報を蓄えておくフォルダを作成する.

```
mkdir anime_infos
```

### 1.5 Mac ユーザーのみ

※ Mac の場合、以下の現象が起きるので追加作業がある

[backend : TkAgg](http://qiita.com/katryo/items/918667f28301fdec89ba)

```
pushd ~/.matplotlib
echo "backend : TkAgg" > matplotlibrc
popd
```

### 2 仮想環境をつくる

[virtualenv](https://virtualenv.pypa.io/en/latest/) を使う

```
sudo easy_install virtualenv
```

### 3 仮想環境 構築

```
virtualenv ENV --python /usr/local/bin/python3
```

### 4 仮想環境 起動

```
cd ENV
source bin/activate
```

### 5 必要な外部ライブラリを入れる

```
pip install -r packages_ubuntu.txt
```

### 6 作者のコードを順番に実行

```
python eval_animes.py
python collect_anime_infos.py
python convert_to_features.py
python anime_reccomend.py
```

### 7 仮想環境 終了

```
deactivate
```

## 個人的な結果

```
precision    recall  f1-score   support

0       0.88      0.96      0.91        89
1       0.96      0.88      0.92       101

avg / total       0.92      0.92      0.92       190

http://cal.syoboi.jp/tid/1597
http://cal.syoboi.jp/tid/4027
http://cal.syoboi.jp/tid/4083
http://cal.syoboi.jp/tid/4085
http://cal.syoboi.jp/tid/4099
http://cal.syoboi.jp/tid/4136
```

- [けいおん！ - しょぼいカレンダー](http://cal.syoboi.jp/tid/1597)
- [ラクエンロジック - しょぼいカレンダー](http://cal.syoboi.jp/tid/4027)
- [三者三葉 - しょぼいカレンダー](http://cal.syoboi.jp/tid/4083)
- [ハンドレッド - しょぼいカレンダー](http://cal.syoboi.jp/tid/4085)
- [田中くんはいつもけだるげ - しょぼいカレンダー](http://cal.syoboi.jp/tid/4099)
- [美少女戦士セーラームーンCrystal(デス・バスターズ編) - しょぼいカレンダー](http://cal.syoboi.jp/tid/4136)

お、おう…
もう 10 年くらいまで昔のアニメの情報も入れられると面白いかもしれない
