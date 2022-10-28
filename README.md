Kaggle script build system template
===================================

Goal is to develop code normally, separating it into modules,
and then package it into a single script for kaggle script submission.

To create a submission, run ``./build.py``, this would
compress the whole package into a script in ``./build/script.py``,
which you can then submit into a kaggle script
(most convenient way is via file upload).

Example kaggle script created in this way:
https://www.kaggle.com/lopuhin/kaggle-script-template

Adjustment:

- if you want to rename the package from ``easy_gold`` (not sure why?)
  then you need to change ``build.py``, ``setup.py`` and
  ``script_template.py``.
- if you want to adjust the entry point (currently ``easy_gold/main.py``),
  or run several commands, change ``script_template.py``.

This is quite basic, feel free to adjust to your needs.

License is MIT.


## 想定するワークロード
1. 管理できるようにgithubリポジトリを作成する
2. kaggleで気になったノートブックをGitHubリポジトリに接続する
3. 英語の場合は、colabだと翻訳できるのでそっちで動かすために、githubからクローンする。
  1. 他にこれを実現するには、ダウンロードして、それをcolabに上げて確認する。
  
※3を実現したいが、今回のこの記事はあまり関係ないかも。。。




## 参考、参照リンク

[Kaggleでのソースコード管理の手助け←初めに見たもの](https://qiita.com/wakame1367/items/a41708c970932c2c724f#git%E7%AD%89%E3%81%A7%E7%AE%A1%E7%90%86%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E6%A7%8B%E9%80%A0%E3%82%92%E3%81%9D%E3%81%AE%E3%81%BE%E3%81%BE%E4%BD%BF%E3%81%86)

[合わせてGitHubからcolabへのクローン](https://qiita.com/kurilab/items/f6f4374d7b1980060de7)




# はじめに
再掲しますが「Gitでコード管理しているのに、KaggleのNotebook提出用に別のコードを用意するのが面倒だ」。この不満、心当たりがある方が多いのではないでしょうか。

今回書く記事はその不満を解消できる方法を発見しましたので共有し、その方法について解説するというのが趣旨になります。

また記事内容ですが主にこちらのKaggle Kernel - lopuhin/imet-2019-submissionの内容を参考に書いております。

前置きのために記事ではCodeCompetitionとはから説明していますが本題から読みたい方は#git等で管理しているファイル構造をそのまま使うから読んで下さい。
