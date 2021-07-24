# Skript

[ダウンロード: Skriptからデイリーランキングを操作できる関数類](https://cdn.discordapp.com/attachments/842413942834987039/868446935248416778/dailyranking.sk)
[ダウンロード: ↑のテストコマンド類](https://cdn.discordapp.com/attachments/842413942834987039/868448214100094986/testcommand.sk)

- `creategame(id, ゲーム名)` - ゲームを作成する
- `removegame(ゲームID)` - ゲームを削除する
- `renamegame(ゲームID, 新しい名前)` - ゲーム名を変更する
- `setformat(ゲームID, フォーマット)` - ランキングボードの表示形式を変更(`%d` が数値に置き換えられる)
- `createmap(ゲームID, id, マップ名)` - マップを作成
- `removemap(ゲームID, マップID)` - マップを削除
- `renamemap(ゲームID, マップID, 新しい名前)` - マップ名を変更
- `resetallscore(ゲームID, マップID)` - マップのデイリーランキングをすべてリセット
- `setscore(ゲームID, マップID, プレイヤー, 数値)` - 記録をマップのデイリーランキングに登録
- `removescore(ゲームID, マップID, プレイヤー)` - マップのデイリーランキングから記録を削除
