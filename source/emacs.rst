Emacs
==============================

Mistilteinn for Emacsはマイナーモードとして実装されているため、任意のメジャーモードとともに利用できます。

主な機能
------------------------------

 * anything.elのインタフェースを利用したチケット選択
 * ファイル保存時の自動nowコミット
 * fixup/masterizeのサポート
 * nowコミットのdiff表示

インストールに必要なもの
------------------------------

 * git
 * Ruby 1.8.7以降
 * RubyGems 1.4.2 以降
 * git-now, git-master ( :doc:`git-tools` 参照)
 * Emacs
 * anything.el

インストール方法
------------------------------

mistilteinn-shellをインストールします。うまくインストールできない場合は :doc:`shell` を参照してください。

.. code-block:: none

  gem install mistilteinn

http://www.emacswiki.org/emacs-en/mistilteinn.el からダウンロードして、 ``load-path`` の通った場所に置きます。
``auto-install.el`` がインストール済みの場合は、 ``M-x auto-install-from-emacswiki`` から ``mistilteinn.el`` をインストールできます。

.emacsに次の設定を追加します。

.. code-block:: cl

  (add-to-list 'load-path "~/workspaces/mistilteinn/")
  (require 'mistilteinn)

  ;; for minor mode
  ;; .mistilteinnの有効化されたレポジトリ内では常にmistilteinn-minor-modeを有効にする
  (global-mistilteinn-mode t)

  ;; for anything
  (defun anything-for-mistiltein ()
    (interactive)
    (anything-other-buffer
      '(anything-c-source-git-ticket) "*mistiltein*"))
  (define-key global-map (kbd "C-t") 'anything-for-mistiltein))

レポジトリごとの設定
------------------------------

``git init`` 等でレポジトリ等を初期化したのちに、 ``mistilteinn init`` でMistilteinnの初期化を行ないます。

.. code-block:: none

  $ cd /path/to/project
  $ git init
  $ ...
  $ mistilteinn init

チケット管理システムの設定等は ``.mistilteinn/config.yaml`` に記述します。
``mistilteinn/config.yaml`` の内容については :doc:`config` を参照してください。

使い方
------------------------------

関数
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``mistilteinn-minor-mode``
  マイナーモードのオン・オフを切り替えます。
``global-mistilteinn-mode``
  Mistilteinnを有効にしたレポジトリ内のファイルを開いたときに、mistilteinn-minor-modeを自動で有効にするかどうかを切り替えます。

キーバインド
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``C-c # c``
  チケットを作成します。
``C-c # n``
  nowコミットを行ないます。
``C-c # d``
  nowコミットによるdiffを表示します。
``C-c # f``
  fixupを行ないます。
``C-c # m``
  masterizeを行ないます。

設定項目
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``M-x customize`` の ``[Programming]`` -> ``[Tools]`` -> ``[Mistilteinn]`` で設定できます。

Mistilteinn Exclude Modes
  mistilteinn-minor-modeを自動で有効にしないメジャーモードのリストです。
Mistilteinn Inactive Ticket Regexp
  チケット一覧を出す際に、解決済みとみなすステータスの正規表現です。
Mistilteinn Active Ticket Face:(sample) [Show Face]
  チケット一覧において、アクティブなチケットに対して使うfaceです。
Mistilteinn Inactive Ticket Face
  チケット一覧において、解決済みのチケットに対して使うfaceです。
