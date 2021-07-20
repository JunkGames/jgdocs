# マップの設定方法

## 必須条件
- 誰かに頼んで`treechopper.admin`の権限をゲットする
- マップ
- ロビーとプレイするマップのワールドを同じにしないこと
- ただし同じワールドに複数のマップを設けるのはOK

## マップ作成/設定

### マップデータ作成
- ロビーをまだ設定していない場合は`/treechopper set lobby`でロビーの位置を設定する(ロビーのワールドも一緒に設定される)
- `/treechopper maps create <マップID> <マップ名>`で新しいマップを作成 (IDは変更できないので注意)
- マップIDを間違えた場合は`/treechopper map <マップ> remove`でマップを削除して上のステップをやりなおす
  - マップを削除してもサーバーを再起動もしくはプラグインを無効化するまでは`plugins/TreeChopper/maps/マップID.yml`をバックアップしてからプラグインをreloadして戻すと復元できます
- マップ名を間違えた場合は`/treechopper map <マップ> rename <新しいマップ名>`でマップ名を変更

### マップ設定
設定必須なものは下記2つ(area/setspawn)だけ
- `/treechopper map <マップ> area <from> <to>`でマップのエリアを設定
- `/treechopper map <マップ> setspawn`でマップに入った時に出てくるスポーン地点を設定

- `/treechopper map <マップ> maxtime <秒>`でゲームの最大時間(秒)を設定。(0～10000)
- `/treechopper map <マップ> maxplayers <プレイヤー数>`で最大プレイヤー数を設定。(最低人数\[デフォルト=2]～10000)
- `/treechopper map <マップ> setenabled <true/false>`でプレイヤーが参加できるかどうかを設定
- `/treechopper map <マップ> info`でマップ情報を表示できます。

## マップのテスト
- `/treechopper map <マップ> join <プレイヤー...>`で1人以上のプレイヤーを指定して、`/treechopper map <マップ> start`でカウントダウンなしで開始できます。
- `/treechopper debug resetall`で全員をゲームから退出させることが可能
