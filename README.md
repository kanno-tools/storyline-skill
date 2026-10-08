# storyline — 資料のストーリーラインを組む Skill

資料を作る前に、1枚1行のタイトル列（ストーリーライン）を組む Gemini CLI / Claude Code 用の Agent Skill。スライドは作らない。

作者：菅野 宏勇（Hirotake Kanno）と Claude。個人用（配布しない）。

## 中身

コンサルの知見は、[consulting-pptx-skill](https://github.com/carnot-tech/consulting-pptx-skill)（Carnot AI Inc.、MIT License）の規約から、ストーリーラインに関わる節を**原文のまま**抜き出して使っている。書き直すと元の知見からずれる恐れがあるため（v2 系で実際に12件のずれが出た。docs/validation.md）。

このリポジトリで書き足したのは SKILL.md だけで、中身は「ストーリーラインで止めて、後工程に渡せる表で出す」ための使い方に限っている。

```
SKILL.md                              使い方（ストーリーラインで止める・出力の形）
references/consulting-rules.md        規約 slide-rules.md のストーリー関連の節（原文。抜き出した行番号を冒頭に記載）
references/archetype-catalog.md       見せ方の型の一覧（原文）
references/ai-smell-lexicon.md        AI 特有の言い回しのリスト（原文）
references/content-review-prompt.md   フレッシュアイ・レビューの指示文（原文）
LICENSE-consulting-pptx-skill         元の MIT License と著作権表示
docs/validation.md                    v1〜v2 系の比較検証の記録（Gemini には読ませない）
```

元にした版：consulting-pptx-skill commit d75bffa（2026-10-06）。本家のストーリー関連の節が更新されたら、consulting-rules.md 冒頭の行番号で抜き出し直す。

## インストール

### Gemini CLI

```bash
git clone https://github.com/kanno-tools/storyline-skill.git
gemini skills link ./storyline-skill
gemini skills list
```

`link` なので、更新は `git pull` だけで反映される。

### Claude Code

このリポジトリの中身を `~/.claude/skills/storyline/` に置く。

## 使い方

素材（メモ・数字・議事録）を渡して「これのストーリーラインを組んで」。背景（誰に・どの会議で・何を決めてもらうか）が分からないと、デッキの代わりに1枚の論点整理と質問が返る。

## バージョン

| 版 | 内容 |
|---|---|
| v3.0.0 | 方式を変更。規約を書き直すのをやめ、元の規約のストーリー関連の節を原文のまま収録した。SKILL.md は使い方だけ |
| v2.1.0 | 元の規約と突き合わせ、食い違う規則を差し戻した（書き直し方式の最終版） |
| v2.0.0 | 自作の審査基準で比較検証して規則を直した版 |
| v1.1.0 | 「動かす」列を外した |
| v1.0.0 | 初版 |
