# anime_recommend

## はじめに

本家様です

[hakobe/anime_recommend](https://github.com/hakobe/anime_recommend)

[今季見るべきアニメを機械学習で推薦する - はこべブログ ♨](http://hakobe932.hatenablog.com/entry/2016/04/15/142756)

何か素晴らしいものが公開されたので利用できるように環境を整えてみた

## 手順

初歩的なところは記憶が曖昧なので多分これでいけるはず…

### 1 まず、アニメの情報を蓄えておくフォルダを作成する.

```
mkdir anime_infos
```

### 1.5 Mac ユーザーのみ

※ Mac の場合、以下の現象が起きるので追加作業がある

[Python 3.3でmatplitlibとpylabを使おうとしたら RuntimeError: Python is not installed as a frameworkというエラーが発生したときの解決方法 - Qiita](http://qiita.com/katryo/items/918667f28301fdec89ba)

```
pushd ~/.matplotlib
echo "backend : TkAgg" > matplotlibrc
popd
```

### 2 Python をインストール

Mac なので [Homebrew](http://brew.sh/index_ja.html) を使ってます

Windows の場合はいい感じにしてください

```
brew install python3
```

### 3 pip のインストール

```
sudo easy_install pip
```

### 4 仮想環境をつくる

[virtualenv](https://virtualenv.pypa.io/en/latest/) を使う

```
sudo pip install virtualenv
```

### 5 仮想環境 構築

Python は python3 を使うように指定

```
virtualenv ENV --python /usr/local/bin/python3
```

### 6 仮想環境 起動

```
cd ENV
source bin/activate
```

### 7 必要な外部ライブラリを入れる

```
pip install -r requirements.txt
```

### 8 作者のコードを順番に実行

```
python eval_animes.py
python collect_anime_infos.py
python convert_to_features.py
python anime_reccomend.py
```

### 9 仮想環境 終了

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
もう 10 年くらい昔のアニメの情報も入れられると面白いかもしれない

### 2016/04/18

更新されたので再度挑戦
全部見てんだよなぁ…

- [ジョジョの奇妙な冒険 ダイヤモンドは砕けない - しょぼいカレンダー](http://cal.syoboi.jp/tid/4100)
- [けいおん！ - しょぼいカレンダー](http://cal.syoboi.jp/tid/1597)
- [ふたりはプリキュア - しょぼいカレンダー](http://cal.syoboi.jp/tid/322)
