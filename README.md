LibreOfficeドキュメント翻訳用OmegaTチームプロジェクト/リポジトリ
===============================================================

これは何?
---------

翻訳支援ツールの[OmegaT](https://omegat.org/ja/)を利用して、ODFで作られた[ユーザーガイド](https://wiki.documentfoundation.org/Documentation/Publications)や[TDF Wiki](https://wiki.documentfoundation.org/)(MediaWiki)を楽に翻訳するためのチームリポジトリ/プロジェクトです。

このリポジトリに書き込み権限がある方は、OmegaTのチームプロジェクトとして利用できます。また、書き込み権限が無くても、リポジトリのアーカイブをダウンロードして展開すればOmegaTプロジェクトファイルとしても利用できます。

クイックスタート
================

プロジェクトファイルとして利用する
-------------------------------------------------

とりあえず起動してみたい!という方は、以下の手順で利用できます。
ですが、この手順では必要最低限の環境しかありません。起動が確認できれば、下の説明を見て、辞書を追加したりプラグインを追加して環境を整えてください。

1. [OmegaT](https://omegat.org/ja/)をダウンロードしてインストールします。
2. このページの「Clone or Download」から、リポジトリの[zipファイル](https://github.com/libreoffice-ja/libreoffice-trans-ja/archive/master.zip)をダウンロードして展開します。
3. sourceフォルダーに原文ファイルを配置します。
4. OmegaTを起動して、プロジェクトとしてフォルダーを読み込みます。
5. 翻訳対象ファイル一覧から原文ファイルを開けば、翻訳ができます!

チームプロジェクトとして利用する (書き込み権限がある方向け)
------------------------------------------------------------

リポジトリの書き込み権限がある方は、メニューのファイルにある「チームプロジェクトをダウンロードする」を選択して、リポジトリを指定してください。

翻訳環境の設定をおこなう
========================

英辞郎を使う
------------

リポジトリには、辞書として自由に利用できる[JMDict](http://simonwiles.net/projects/jmdict/)を用意していますが、テキストデータとして販売されている[英辞郎を購入](https://booth.pm/ja/items/777563)して利用もできます。

利用方法は、StarDict形式への変換スクリプト[eiji2sd](http://cabonera.hateblo.jp/entry/2016/03/01/215118)を使い、購入した英辞郎データをStarDict形式に変換して、dictionaryフォルダーに配置します。

    $ perl ./eiji2sd-html.pl EIJIRO-1445.TXT


みんなの自動翻訳@TexTraプラグインをインストールする
---------------------------------------------------

NICTが提供する自動翻訳サービス[みんなの自動翻訳@Textra](https://mt-auto-minhon-mlt.ucri.jgn-x.jp/content/menu/)は、オープンソースソフトウェアの文書の翻訳に利用できる機械翻訳サービスです。

参考
* 利用規約の別紙1: https://mt-auto-minhon-mlt.ucri.jgn-x.jp/content/policy/
* 開発者の方からの言及: https://mt-auto-minhon-mlt.ucri.jgn-x.jp/content/qa/detail/?q_qa_id=204&t=1488561411 (要ログイン)

OmegaTから、みんなの自動翻訳を使うためのプラグインが公開されており、こちらをインストールするとOmegaTの中から自動翻訳が使えます。

* <https://github.com/miurahr/omegat-textra-plugin>

### APIキーとシークレットキーが保存されない

設定は自動的に保存されるはずですが、自分の場合、なぜか保存されませんでした。 その場合は、OmegaTの設定ファイル ``~/.omegat/omegat.prefs`` (Linuxの場合) に追記します。

    <mt_textra_username>ユーザー名</mt_textra_username>
    <mt_textra_apikey>APIキー</mt_textra_apikey>
    <mt_textra_secret>シークレットキー</mt_textra_secret>

Okapi Filters Plugin for OmegaTをインストールする
-------------------------------------------------

Okapi Filtersプラグインをインストールすると対応ファイル形式が増えるので、インストールしておくと良いでしょう。

* <http://okapiframework.org/wiki/index.php/Okapi_Filters_Plugin_for_OmegaT>


その他
======

リポジトリのディレクトリ構成
----------------

リポジトリのディレクトリ構成は以下のようになっています。sourceフォルダーに原文ファイルを置き、OmegaTからプロジェクトとして読み込むと、すぐに翻訳ができるようにしてあります。


    libreoffice-trans-ja/
    ├── README.md
    ├── dictionary (StarDict形式の辞書を置きます)
    │   ├── JMdict.dict.dz
    │   ├── JMdict.idx
    │   ├── JMdict.ifo
    ├── glossary (用語集)
    │   └── glossary.txt
    ├── libreoffice-trans-ja-level1.tmx
    ├── libreoffice-trans-ja-level2.tmx
    ├── libreoffice-trans-ja-omegat.tmx
    ├── omegat
    ├── omegat.project
    ├── source (原文ファイルを置きます)
    ├── target (翻訳をした訳文が生成されます)
    └── tm (pootleのpoから生成した翻訳メモリを置きます。たまに更新する予定)
        ├── pootle-level1.tmx
        ├── pootle-level2.tmx
        └── pootle-omegat.tmx

