# まえがき
これはFlaskの実践的な用例をまとめた本です。
一般的なFlaskアプリケーションを開発する際、ユーザー認証やデータベースとの連携など、多くのモジュールを活用する必要があります。
この本ではこれらの「適切な方法」を解説します。
私はこの方法を常に推奨するわけではありませんが、多くの場合において正しい選択だと考えています。

## 前提条件
より具体的なアドバイスを行うために、この本は幾つかの前提に基づいて書かれています。
この本に書いてあることを実際のプロジェクトで利用する際には前提条件を満たしているか十分確認してください。

### 対象読者
この本の内容は公式ドキュメントにある情報を基に書かれています。
事前に[ユーザーガイド](http://flask.pocoo.org/docs/#user-s-guide)と[チュートリアル](http://flask.pocoo.org/docs/tutorial/)を読んでFlaskの用語に慣れておくことを推奨します。
また、ビューやJinjaテンプレートなどの基礎的な概念を知っておくと良いでしょう。

ともかく、この本で取り上げる話題はそれほど高度なものではありません。
この本の目的は開発に役立つ実践的な用例やパターンを紹介することです。
公式ドキュメントとの重複を避けるために、あなたがその概念を既に知っているかどうかを繰り返し確認しています。
なお、初心者向けのチュートリアル本を開きながらこの本を読む必要はありません。

### バージョン

#### Python 2 と Python 3

これを書いている時点で、PythonコミュニティはPython 2からPython 3への移行を行っている最中です。
Python Software Foundationの公式な立場は以下の通りです。[^0-1]

> Python 2.x は現状を維持します。Python 3.x は現在と未来の言語です。

Flaskのバージョン0.10以降であればPython 3.3で動作します。しかし、Armin Ronacherに尋ねてみると、まだ完全に推奨できないという返答がありました。

> 私自身まだPython3を利用していませんので、現状では一般ユーザーにも
> Python3を推奨することは出来ません。
>
> --- Armin Ronacher(Flaskの開発者)

まだPython 3を完全に推奨できない理由の1つは、一般的な依存ライブラリが完全に移植されていないからです。
Pytho3でFlaskアプリケーションを開発しようとすると、利用できないパッケージがあるかもしれません。

**訳注**

Flaskは公式にPython3をサポートしています、しかしまだPython3に対応していないライブラリが多くあるため、誰にでも安心して推奨出来ないという状況です。

Python3を利用する場合は利用するライブラリの対応状況を十分確認した上で利用してください。

[Python 3 Wall of Superpowers](https://python3wos.appspot.com/)というサイトにPython 3に移植済みの有名なパッケージがまとめられています。

**注記**

この本では実践的なアドバイスを行うためにPython2を前提に記述しています。
具体的にはPython 2.7を利用してこの本を書いています。
今後のFlaskコミュニティの動向に応じて更新することもあるかもしれませんが、今の所Python 2.7を利用します。

#### Flask バージョン 0.10
この本を書いている時点でのFlaskの最新バージョンは(0.10.1)でした。
Flaskのマイナーアップデートが行われた際にこの本に細かな変更を行うことはありませんので心に留めいておいてください。

## 生きた文書
この本は定期的に新しいバージョンを出版するというよりも、臨機応変に内容を更新していきます。
紙の本で出版するよりもWEBの方が配布に適した流通経路でしょう。

この本のソースは[GitHub](https://github.com/rpicard/explore-flask)で公開しています。この本の改良や誤りの指摘はこちらでいつでも受け付けています。

**訳注**

翻訳本のソースはこちらです。

 - <https://github.com/hamano/explore-flask-ja>

## この本の構成

### 各章は独立しています
多くの本やチュートリアルは一連の長いレッスンとして書かれていますが、この本の各章はそれぞれ独立したレッスンになっています。
各章ではFlaskの概念を学ぶためにサンプルコードを示していますが、他の章のサンプルコードと組み合わせて大きなアプリケーションをつくるというわけではありません。

### 書式
脚注はなにかを引用する際に利用します。[^0-3]

*下線* はファイル名を示す際に利用します。

**太字** は新しい用語または重要な単語に利用します。

**警告**

大きな問題を引き起こす落とし穴がある場合は警告で表示します。

**注記**

補足的な情報は注記で表示します。

## イースター・エッグ
この本の中にキックスターターキャンペーンの6人の支援者の名前がエンコードされて散りばめられています。
6つ全てを見つけて私にメールすると、ちょっとした賞を授与します。
ヒントはありません。

## まとめ

- この本にはFlaskの推奨例が書かれています。
- チュートリアルはあらかじめ読んでいたほうが良いです。
- 私はPython 2.7を利用しています。
- 私はFlask 0.10を利用しています。
- この本の内容が古くならないように可能な限り更新していきます。
- この本は複数の章で構成されています。
- 補足情報を伝えるために幾つかの書式を利用します。
- 各章の最後に内容を簡単にまとめています。

[^0-1]: [The Python wiki](http://wiki.python.org/moin/Python2orPython3)
[^0-2]: [My conversation with Armin Ronacher](https://www.youtube.com/watch?feature=player_detailpage&v=fs20qdvm0K4#t=190)
[^0-3]: ここが脚注です。

