Mistilteinn/Shell
==============================

Mistilteinn/ShellはMistilteinnの機能をサポートするコマンドラインツールです。

現在は、 :doc:`emacs` のバックエンドとして使われています。

インストール方法
------------------------------

Rubygemsからインストールできます。

.. code-block:: none

  gem install mistilteinn


レポジトリの初期化
------------------------------

``git init`` 等でレポジトリ等を初期化したのちに、 ``mistilteinn init`` でMistilteinnの初期化を行ないます。

.. code-block:: none

  $ cd /path/to/project
  $ git init
  $ ...
  $ mistilteinn init

チケット管理システムの設定等は ``.mistilteinn/config.yaml`` に記述します。
``mistilteinn/config.yaml`` の内容については :doc:`config` を参照してください。

機能
------------------------------

初期化: init
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

現在のレポジトリをMistilteinn用に初期化します。

.. code-block:: none

   $ mistilteinn init

診断モード: self-check
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Mistilteinnが正常に動作するかをチェックします。

.. code-block:: none

   $ mistilteinn self-check
   ------------------------------
   ticket source
   ------------------------------
   source type => Mistilteinn::Ticket::Redmine
   Mistilteinn::Ticket::Redmine => ok

   ------------------------------
   git
   ------------------------------
   inside work tree? => ok
   git-now subcommand => ok
   git-master subcommand => ok
   git-hooks subcommand => ok

   Works! Have a good programming!!

チケットリスト: list
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

チケット一覧を出力します。

.. code-block:: none

   $ mistilteinn list

チケット作成: create
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

チケットを作成する。

.. code-block:: none

   $ mistilteinn create hoge

Mistilteinnが有効かチェック: is-inside
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

現在のレポジトリでMistilteinnが有効かチェックします。
有効な場合は終了コードが0になります。

.. code-block:: none

   $ mistilteinn is-inside

バグ報告
------------------------------

要望・バグ報告は、 https://github.com/mistilteinn/mistilteinn-shell/ に対するIssues登録、もしくはpull requestで報告してください。
