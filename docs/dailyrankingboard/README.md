# DailyRankingBoard (デイリーランキング) (Kotlin)

- [Skript](/dailyrankingboard/skript)

## 注意事項
- reloadしちゃダメ！！！！！

## 初期設定

これらは全部`dailyrankingboard.command`もしくは`dailyrankingboard.admin`があれば実行可能

- `/dr set board_location` - デイリーランキングのランキングボードの位置の場所を設定
- `/dr set game_selector_location` - ゲーム選択ができる操作盤の場所を設定
- `/dr set map_selector_location` - マップ選択ができる操作盤の場所を設定

## ルマンド

ここに書いてあるコマンドは`dailyrankingboard.admin`かコマンドの横に書いてあるパーミッションが必要

全部コンソール/コマンドブロックから実行可能

- `/dr games add <id> <name>` (`dailyrankingboard.games.add`) - ゲームを作成
- `/dr game <game> remove` (`dailyrankingboard.games.remove`) - ゲームを削除
- `/dr game <game> rename <new-name>` (`dailyrankingboard.games.rename`) - ゲームの名前を変更
- `/dr game <game> setformat <format>` (`dailyrankingboard.games.setformat`) - ランキングボードに表示される形式を設定(`%d`が数値として置き換えられる)
- `/dr game <game> setorder <order>` (`dailyrankingboard.games.setorder`) - ランキングボードに表示される値の順序を変更(下記参照)
- `/dr game <game> maps add <id> <name>` (`dailyrankingboard.maps.add`) - マップを作成
- `/dr game <game> map <map> remove` (`dailyrankingboard.maps.remove`) - マップを削除
- `/dr game <game> map <map> rename <new-name>` (`dailyrankingboard.maps.rename`) - マップの名前を変更
- `/dr game <game> map <map> leaderboard resetall` (`dailyrankingboard.maps.leaderboard.resetall`) - マップのデイリーランキングをすべてリセット
- `/dr game <game> map <map> leaderboard add <player> <value: integer>` (`dailyrankingboard.maps.leaderboard.resetall`) - 記録をマップのデイリーランキングに登録
- `/dr game <game> map <map> leaderboard remove <player>` (`dailyrankingboard.maps.leaderboard.resetall`) - マップのデイリーランキングから記録を削除

## Orderに指定可能なもの

| Order | 順序 |
| --- | --- |
| ASC | 0, 1, 2, 3, 4, 5, ... |
| DESC | 9999, 8888, 7777, 6666, ... |
