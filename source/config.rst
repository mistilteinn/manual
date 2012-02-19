設定ファイルのフォーマット
==============================

設定ファイルは ``.mistilteinn/config.yaml`` に置かれており、以下のような書式になっています。

.. code-block:: yaml

  ticket:
    # チケット一覧の取得元を設定します。
    #   redmine: redmineからチケット一覧を取得します
    #   github:  github issuesからチケット一覧を取得します
    source: redmine

  # redmineに関係する設定
  redmine:
    # URL
    url: https://example.com/redmine/
    # プロジェクト名
    project: mistilteinn
    # APIキー。
    # セキュリティ上の理由で設定ファイルに書けない場合は
    #   git config redmine.apikey your_key
    # で設定できます。
    apikey: your_key

  # githubに関係する設定
  github:
    # ユーザ名
    name: mistilteinn
    # プロジェクト名
    project: mistilteinn-shell

