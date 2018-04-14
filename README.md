# 使い方

 `launch_pad` ディレクトリに移動後、

```
$ ansible-playbook ./my_workspace.yml -i inventory.ini
```
で開始。

### その前にやっておくこと

#### 【1/2】ssh接続の各種設定
 
 `ansible.cfg` ファイルの記述を補完すること
```
[ssh_connection]
ssh_args = -F (ssh接続のコンフィグファイルを指定)
```

#### 【2/2】操作先ホストの指定
 
以下のような内容で `inventory.ini` ファイルを作成すること
```
[my_workspace]
(ホスト名またはIPアドレスを記述。複数記述する場合は都度改行)
```
