# STATUS — storyline-skill

## 現在地
- v1.0.0 を KANNOHI1/storyline-skill（private）に公開。資料のストーリーライン（1枚1行のタイトル列）を組む Skill。スライドは作らない

## 次にやること
1. 会社 VM の Gemini CLI に入れて、実際の題材で1回使う（private リポジトリなので VM 側に GitHub の認証が要る。無理なら public 化を検討）
2. 使って出た曖昧さを references/ に1行ずつ足す

## 未解決・保留
| 項目 | 状態 | メモ |
|---|---|---|
| 個人 PC の Gemini CLI で実行テスト | 不可 | 個人向け Gemini Code Assist が終了（IneligibleTierError）。認識（skills list）は確認済み。実行は Claude の別エージェントで2回検証 |

## 判断済みの決定
| 決定 | 理由 | 日付 |
|---|---|---|
| moving-slides に組み込まず独立 Skill にする | HK の判断。資料の種類（動く／静止）に依らず前工程として使うため | 2026-10-08 |
| 作者は HK と Claude。private・配布しない | HK の判断。文章はすべて書き下ろし（consulting-pptx-skill の考え方を参考にしたが、文章は複製していない） | 2026-10-08 |

## ハマりパターン
- `gemini skills install` は確認プロンプトで止まる。非対話では `--consent` を付ける

## 更新履歴
| 日付 | 内容 |
|---|---|
| 2026-10-08 | v1.0.0 作成。Claude の別エージェントで2回実行テストし、1回目の指摘9件のうち8件を規則で解消 [Claude] |
