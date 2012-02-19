git-now, git-masterのインストール方法
============================================================

Mistilteinnで用いられるgitのサブコマンド群です。
:doc:`visualstudio` と :doc:`emacs` とで使われています。

インストール方法
------------------------------

https://github.com/mistilteinn/git-tools/tarball/master をダウンロードし、パスの通ったディレクトリに展開します。

git-now
------------------------------

nowコミットの生成、およびfixupを行なうためのコマンドです。

``git now``
  nowコミットを生成します。
``git now --compact``
  nowコミットを生成します。 前回のnowコミットからの変更点が少ない場合は、amendされます。
``git now --diff``
  nowコミットのdiffを生成します。
``git now --rebase``
  nowコミットをrebase -iします。
``git now --fixup``
  nowコミットをfixupします。

git-master
------------------------------

masterizeを行なうためのコマンドです。

``git master``
  現在のブランチのコミットをmasterブランチにmasterizeします。
``git master hoge``
  現在のブランチのコミットをhogeブランチにmasterizeします。

バグ報告
------------------------------

要望・バグ報告は、 https://github.com/mistilteinn/git-tools/ に対するIssues登録、もしくはpull requestで報告してください。
