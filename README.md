# storyline — 資料のストーリーラインを組む Skill

資料を作る前に、1枚1行のタイトル列（ストーリーライン）を組む Gemini CLI / Claude Code 用の Agent Skill。
スライドは作らない。「誰に何を決めてもらうか」と「読み手の反論」を先に決め、問いを分解し、タイトルだけを通し読みして1本の話になるまで直す。

作者：菅野 宏勇（Hirotake Kanno）と Claude。個人用（配布しない）。

## なぜ

見た目の良い資料を作るスキル（moving-slides、PowerPoint 系）は、何をどの順で言うかが決まっている前提で動く。その手前の「どのページで何を言うか」を固める工程を、独立したスキルにした。

## 使う流れ

```
storyline（このスキル）      ストーリーライン表を作る。スライドは作らない
   ├─ 「動かす」○の行 → moving-slides       動くスライド（Bloomberg など）
   └─ 全行            → PowerPoint 系のスキル  静止スライド
```

出力の表は、moving-slides の素材シート（決めてもらうこと・反論・伝えたいこと・聞かれそうな質問・数字）とそのまま対応する。見本は `examples/cafeteria.md`。

## 構成

```
SKILL.md                     手順・出力形式・点検（最初に読まれる）
references/flow-rules.md     問いの分解、並べ方、枚数、見せ方の選び方
references/title-rules.md    タイトルの書き方と禁止の形
references/review-prompt.md  別の目で読ませる指示文と採否表
examples/cafeteria.md        出力の見本（数字はすべて架空）
```

## インストール

### Gemini CLI

```bash
git clone https://github.com/KANNOHI1/storyline-skill.git
gemini skills link ./storyline-skill
gemini skills list
```

`link` なので、更新は `git pull` だけで反映される。

### Claude Code

このリポジトリの中身を `~/.claude/skills/storyline/` に置く。

## 使い方

素材（メモ・数字・議事録）を渡して「これのストーリーラインを組んで」。

背景（誰に・どの会議で・何を決めてもらうか）が書かれていないと、ストーリーラインの代わりに1枚の論点整理と質問が返る。

## バージョン

| 版 | 内容 |
|---|---|
| v1.0.0 | 初版 |
