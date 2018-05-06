# 使い方

 `launch_pad` ディレクトリに移動後、

```
$ ansible-playbook ./my_workspace.yml -i inventory.ini
```
で開始。

### その前にやっておくこと

#### 【1/3】操作先ホストへのssh接続の各種設定
 
 `ansible.cfg` ファイルの記述を補完すること
```
[ssh_connection]
ssh_args = -F (ssh接続のコンフィグファイルを指定)
```

#### 【2/3】操作先ホストの指定
 
以下のような内容で `inventory.ini` ファイルを作成すること
```
[my_workspace]
(ホスト名またはIPアドレスを記述。複数記述する場合は都度改行)
```

#### 【3/3】公開鍵ファイル等の設置

 `roles/deploy/files/` 以下に公開鍵ファイルを置いてください。
そして `group_vars/project.yml` の `public_key_file_name:` の項に、公開鍵ファイルの名前を記述してください。

同じ場所に、railsアプリの `config/master.key` も置いてください。

#### その他

必要に応じて、 `group_vars/project.yml` の変数を書き換えてください。
ユーザーのパスワード設定等を。

### 実行環境の設定について

以下のモジュールに依存している箇所があります。
事前にインストールが必要です。
```
$ pip install passlib
```
