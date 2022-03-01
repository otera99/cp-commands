# cp-commands

## なにができるのか

AtCoderの場合、[atcoder-cli](https://github.com/Tatamo/atcoder-cli)で生成したファイル下にコードで書き、`cp-run source -aca`とすることで、コンパイル、[online-judge-tools](https://github.com/online-judge-tools/oj)によるテスト、[otera-cp-library](https://github.com/otera99/otera-cp-library)の展開、提出用コードのクリップボードへのコピーを一度に行える.

Codeforcesの場合もAtCoderと同様に問題ごとのファイルを作り、[online-judge-tools](https://github.com/online-judge-tools/oj)でテストケースをダウンロードしておけば、あとはコードを書いた後、`cp-run source -cfa`とすることで、コンパイル、[online-judge-tools](https://github.com/online-judge-tools/oj)によるテスト、[AtCoder Library (ACL)](https://github.com/atcoder/ac-library)と[otera-cp-library](https://github.com/otera99/otera-cp-library)の展開、提出用コードのクリップボードへのコピーを一度に行える.

なお、現時点では、C++以外の言語には対応していない.

## 使い方

競技プログラミング用のrepositoryを作って、そこの下に[otera-cp-library](https://github.com/otera99/otera-cp-library)をダウンロードして入れる.

作った競技プログラミング用のrepositoryに、`atcoder`, `codeforces`, `yukicoder`のファイルを新たに作る.
`atcoder`, `codeforces`, `yukicoder`ファイル下では、各コンテストごとにまたファイルを作り、そのコンテストごとのファイル下に、さらに各問題ごとのファイルと作り、その下で問題に対応したコードを書くと良い.
([online-judge-tools](https://github.com/online-judge-tools/oj)と[atcoder-cli](https://github.com/Tatamo/atcoder-cli)という神ツールがあるので、そちらの使用を想定している.)

## スクリプトの動かし方

```
chmod u+x {path to cp-commands}/cp-run
```

として、`cp-commands`にPATHを通すと良い.

なお、 https://qiita.com/i_shot1997/items/1699331e526cb90615df を参照すると良い.

## 更新履歴
2022.02.23: 提出用コードのクリップボードへのコピー機能を追加

2022.03.01: ディレクトリの構成に依存せずに展開できるような実装に書き換えた.

## TODO
コンパイル時に参照するライブラリのpathを`lib_serach.find_otera()`で見つけたものにするように書きかえる.(2022.03.01に追加済み)

`lib_serach.find_otera()`の修正

ojコマンドのoptionを使えるようにする

AtCoderにコードを提出する時、`const int inf = 1'000'000'007;`などとすると、コメントと判定されてコードが読みにくくなるので、後ろに`//'`などとつけて展開してくれる機能があると嬉しい(2022.03.01に追加済み)

コンパイルに失敗したら、ojコマンドなどは実行しないで欲しい.

printでmessageを出してるけど、loggingとかを使うべき.

C++以外(Python)のコードにも対応する.

## 注意
コードのクリップボードへのコピーまでには数秒ほどかかるので(ojでテストにかかる時間などで)、実行が終わった(コピーが終わったと出る)までは、コードを提出しないように気をつける.