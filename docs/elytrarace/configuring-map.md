# マップの設定方法

## 必須条件
- 誰かに頼んで`elytrarace.admin`の権限をゲットする
- マップ
- ロビーとレース会場のワールドを同じにしないこと
- ただし同じワールドに複数のレース会場を設けるのはOK

## マップ作成/設定

### マップ作成 (仕組み等)

![](https://user-images.githubusercontent.com/19150229/123234491-f23c4e00-d515-11eb-9351-d76725572278.png)

上の画像のような金の枠を作るとプレイヤーの速度が2倍になるリングを作れます。

![](https://user-images.githubusercontent.com/19150229/123234664-17c95780-d516-11eb-93d2-95c6e269fb19.png)

ダイヤの枠を作るとプレイヤーの速度が3倍になるリングを作れます。

![](https://user-images.githubusercontent.com/19150229/123234793-39c2da00-d516-11eb-9f4b-8f42f7373662.png)

エメラルドの枠を作ると特定のアイテムがもらえるリングが作れます。

それぞれのリングは
- 角がない
- 枠のブロック数が101ブロック以上にならない
- 斜めではない
の条件が揃うと動きます

たとえば、このような枠も動きます

![](https://user-images.githubusercontent.com/19150229/123235352-beadf380-d516-11eb-9392-d709e4027fbe.png)

ただしこのようなものは動きません

![](https://user-images.githubusercontent.com/19150229/123235591-fa48bd80-d516-11eb-9d2e-f4f331f55cbd.png)

### マップの制作中にリングが動くかをテストしたい
1. `/er createmap <マップID> <マップの名前(あとで変更可能)>`でマップデータを作成
2. クリエでエリトラを装備して
3. リングを通る


### マップデータ作成
- ロビーをまだ設定していない場合は`/er set lobby`でロビーの位置を設定する(ロビーのワールドも一緒に設定される)
- `/er createmap <マップID> <マップ名>`で新しいマップを作成 (IDは変更できないので注意)
- マップIDを間違えた場合は`/er map <マップ> delete`でマップを削除して上のステップをやりなおす
  - マップを削除してもサーバーを再起動もしくはプラグインを無効化するまでは`plugins/ElytraRace/maps/マップID.yml`をバックアップしてからプラグインをreloadして戻すと復元できます
- マップ名を間違えた場合は`/er map <マップ> set name <新しいマップ名>`でマップ名を変更

### マップ設定
- `/er map <マップ> set spawnLocation`でマップに入った時に出るスポーン地点を設定
- `/er map <マップ> checkpoint add <from> <to>`で`from`～`to`にある`minecraft:infested_stone`を通過点とし、プレイヤーがコマンド実行時にいる位置をリスポーン位置としてチェックポイントを追加
  - このコマンドを実行した地点で指定範囲内にある`minecraft:infested_stone`が`minecraft:air`に置き換えられ、プレイヤーの通過点になります(チェックポイントとして登録されたブロックは一定時間発光されます)。
  - `/er map <マップ> checkpoint remove <index>`でチェックポイントを削除 (0が最初のチェックポイント)
  - チェックポイントを通らずにゴール、もしくは前のチェックポイントを通らずに次のチェックポイントを通過すると前のチェックポイントの場所に戻される
  - チェックポイントが10000個超えるとバグるのでやらないでください
  - cpはcheckpointの略です
- `/er map <マップ> set startLocation <from> <to>`でスタート地点を設定 (スタートする前に外に出れなくするため)
- `/er map <マップ> set lapLocation <from> <to>`でラップ地点 (エリア内に入ると通過判定)
- `/er map <マップ> set finishLocation <from> <to>`でゴールを設定 (エリア内に入るとゴール判定)
- `/er map <マップ> set maxTime <秒>`でレースの最大時間(秒)を設定できます。
- `/er map <マップ> itembox add`でアイテムボックスの場所をプレイヤーの位置に追加します。
- `/er map <マップ> itembox remove`で近くにあるアイテムボックスを削除できます。
- `/er map <マップ> set maxPlayers <プレイヤー数>`で最大プレイヤー数を設定できます。
- `/er map <マップ> set lapCount <ラップ数>`でラップ数を設定できます。 (1 = lapLocation無視)
- `/er map <マップ> set enabled <true/false>`でプレイ可能なマップに含めるかを設定します。
- `/er map <マップ> info`でマップ情報を表示できます。
- `/er map <マップ> start`で手動でゲームを開始できます。

## マップのテスト
- `/er joinandstart [<マップID> <プレイヤー...>]`で参加+ゲーム開始が可能です(`/er map <マップ> set enabled true`をしていなくても)。
- マップから抜けたい場合は`/er leave <プレイヤー...>`で参加しているゲームから抜けることができます。
