# AsureTimer - アスレチック＆ドロッパータイマー

> ⚠️ **α版（アルファ版）** - このプラグインは現在開発中です。バグが存在する可能性があります。

アスレチックコースとドロッパーのタイム計測・ランキングプラグインです。

---

## 機能

### 2種類のゲームモード

**アスレチック（Asure）**
- 距離計測対応（例: 1000mアスレ）
- クリアタイムランキング
- 到達距離ランキング

**ドロッパー（Dropper）**
- 落下タイム計測
- クリアタイムランキング

### その他の機能
- 複数コース対応
- 看板システム（スタート、ゴール、ランキング）
- ActionBarでリアルタイム表示
- SQLiteデータベースで永続化
- ギブアップアイテム

---

## コマンド

### セットアップ

| コマンド | 説明 |
|---------|------|
| `/asure setup spawn [コースID]` | スポーン地点設定 |
| `/asure setup start [コースID]` | スタート地点設定 |

### コース管理

| コマンド | 説明 |
|---------|------|
| `/asure course list` | コース一覧 |
| `/asure course create <ID> <asure\|dropper> [距離]` | コース作成 |
| `/asure course delete <ID>` | コース削除 |
| `/asure course settype <ID> <asure\|dropper>` | タイプ変更 |

### その他

| コマンド | 説明 |
|---------|------|
| `/asure ranking [コースID] [time\|distance]` | ランキング表示 |
| `/asure reload` | 設定再読み込み |

---

## 看板システム

### スタート看板
```
[asure]     または    [dropper]
start                 start
1000m                 dropper1
```

### ゴール看板
```
[asure]
goal
1000m
```

### ランキング看板
```
[asure]
ranking
1000m
time
```

---

## 権限

| 権限 | 説明 | デフォルト |
|------|------|-----------|
| `asuretimer.admin` | 管理者権限 | op |
| `asuretimer.play` | プレイ権限 | true |

---

## セットアップ

1. `plugins` フォルダに配置
2. サーバー再起動
3. `/asure course create 1000m asure 1000`
4. `/asure setup spawn 1000m`
5. `/asure setup start 1000m`
6. スタート・ゴール看板を設置
7. プレイ！

---

## 設定（config.yml）
```yaml
default-course: "1000m"

courses:
  1000m:
    type: asure
    distance: 1000

messages:
  start: "&aアスレチックを開始しました！"
  clear: "&a&lクリアタイム: &e{time}"

giveup-item:
  material: NETHER_STAR
  name: "&c&lギブアップ"

actionbar-interval: 5
sign-update-interval: 30
```

---

## 動作環境

- Spigot/Paper 1.21.x
- Java 17以上
- 前提プラグインなし

## コミュニティ

**Discord:** https://discord.gg/zYY55dzhjd

## ライセンス

All Rights Reserved
