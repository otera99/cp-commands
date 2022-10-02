# cp-commands

## なにができるのか

### cp-run

コンパイル(sanitazerも付けれる)，ojによるtest，ライブラリ([otera-cp-library](https://github.com/otera99/otera-cp-library))の自動展開，コードのcopy，テストケースの個別実行などが行える．

### cp-test

ランダム生成したテストケースで愚直解との比較が可能．

## 使い方

### cp-run

以下のコマンドで，コンパイル，ojによるtest，ライブラリの自動展開，クリップボードにコードをcopyが行える．
```
cp-run source -a
```
以下のコマンドで，コンパイル(-DDEBUG option付き)，ojによって生成されたテストケースについてテストの実行が行える．
```
cp-run source --deb {テストケースの番号} 
```

### cp-test

愚直解のコード(```tle.cpp```)と，テストケース生成コード(```gen.cpp```)を用意して，

```
cp-test source
```
とすると良い．

#### option

```
--cnt {テストの回数} 
```

```
--dir {WAになったテストケースを入れるdirectory}
```

## スクリプトの環境設定

```
chmod u+x {path to cp-commands}/cp-run
```
```
chmod u+x {path to cp-commands}/cp-test
```

として、`cp-commands`にPATHを通すと良い.

なお、 https://qiita.com/i_shot1997/items/1699331e526cb90615df を参照すると良い.

また，[atcoder-cli](https://github.com/Tatamo/atcoder-cli)を使う際には，以下のコマンドで，生成されるテストケースのdirectoryの名前を`tests`から`test`に変更しておく．

```
acc config default-test-dirname-format test
```

また，[otera-cp-library](https://github.com/otera99/otera-cp-library)を使いたい場合は，普段使う競技プログラミング用のrepositoryの下に[otera-cp-library](https://github.com/otera99/otera-cp-library)をダウンロードして入れておく．

## 注意
コードのクリップボードへのコピーまでには数秒ほどかかるので(コンパイルやojでテストにかかる時間などで)、実行が終わった(コピーが終わったと出る)までは、コードを提出しないように気をつける.