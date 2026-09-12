# Ian Xiaohei Illustrations

[简体中文](README.md) · [English](README.en.md) · **日本語**

> 記事のなかにある判断・フロー・状態・比喩を、白地・手描き・奇妙だけど清潔な本文挿絵に変換します。本文の言語は問わず、画像内の手書き注記は本文の言語に追従します。
>
> 16:9 横長 | 小黑 IP | 白地の手描き | 少量の赤・橙・青の手書き注記 | 多言語 | Codex Skill

---

## このリポジトリについて

Ian Xiaohei Illustrations は、AI エージェントに記事・投稿・ブログ・Notion ドキュメント・方法論コンテンツ向けの本文挿絵を生成させるための Codex Skill です。本文の言語は中国語・英語・日本語など何でもよく、画像内の手書き注記はデフォルトで本文の言語に追従します。

汎用のイラスト用プロンプトでも、PPT インフォグラフィックのテンプレートでもありません。目的は、まず記事のなかの「認知のアンカー」を理解し、そのうちの一つの判断・フロー・構造・状態・比喩を、記憶に残る 16:9 の手描き説明図に変えることです。

デフォルトのビジュアル IP は **小黑（シャオヘイ）**：黒く塗りつぶされた体、白い点の目、細い脚、無表情の小さなキャラクターです。小黑 はマスコットでもステッカーでも、隅に立っている飾りでもありません。システムの動作に真剣に参加している、不条理な作業者です。

一言でいうと：**AI に「とりあえず挿絵を付ける」のではなく、記事のなかの重要な認知動作を描かせる。**

---

## こんな人向け

向いている人：

- 記事（中国語・英語・日本語など）を書いていて、本文挿絵や記事イラストが必要な人
- ナレッジ系コンテンツ、方法論コンテンツ、AI ワークフローの解説を作っている人
- 抽象的な判断を具体的な比喩に落としたい人
- PPT インフォグラフィックより軽く、奇妙で、個性が出る挿絵スタイルが欲しい人
- Codex でコンテンツ制作をしていて、一貫したビジュアル言語を再利用したい人

向いていない人：

- 商業イラスト、ブランド KV、洗練されたフラットイラストが欲しい人
- 従来型の PPT インフォグラフィック、複雑なアーキテクチャ図、正式なフローチャートが欲しい人
- 子ども向けアニメ、かわいい IP、スタンプ風のテイストが欲しい人
- 大量の本文や長い説明、講座ページ丸ごとを 1 枚に詰め込みたい人
- 厳密に編集可能なベクターソースが必要な人

---

## 何が出力されるか

デフォルトの出力：

- 16:9 横長の本文挿絵
- 1 本の記事に対する 4〜8 枚の shot list
- 各画像のテーマ・核心の意味・構造タイプ・小黑 の動作・注記案（言語は本文に追従）
- 最終的な PNG。ワークスペースの `assets/<article-slug>-illustrations/` に保存

デフォルトでは出力しないもの：

- PPTX / PDF / Keynote
- 編集可能な SVG / HTML / Canvas
- 商業ポスターやカバー KV
- 文字量の多いインフォグラフィック

---

## ビジュアルスタイル

この skill は Ian の「小黑 の奇妙な本文挿絵」スタイルをデフォルトにしています：

- 白地。紙のテクスチャ、ベージュ、影、グラデーションは使わない
- 黒の手描き線画。細く、わずかに揺れた線
- 余白を多く取り、主役は画面の 40%〜60% 程度に収める
- 少量の赤・橙・青の手書き注記。言語は本文に追従
- 1 枚で表すのは一つの核心動作・構造・状態・比喩だけ
- 小黑 は必ず核心動作を担う。飾りにしない
- 奇妙・創造的・清潔に。幼稚にも、あざとくもしない

---

## 作例

### 二つの断点

![二つの断点](examples/images/01-two-breakpoints.png)

### 目的で仕分ける

![目的で仕分ける](examples/images/02-sort-by-purpose.png)

### 一匹の魚を何通りにも食べる

![一匹の魚を何通りにも食べる](examples/images/03-one-fish-many-uses.png)

### 受け渡しの経路

![受け渡しの経路](examples/images/04-handoff-path.png)

### 情報の井戸

![情報の井戸](examples/images/05-information-well.png)

### アイデアのプレス機

![アイデアのプレス機](examples/images/06-idea-press.png)

### コンテンツの発酵

![コンテンツの発酵](examples/images/07-content-fermentation.png)

### 信頼の橋

![信頼の橋](examples/images/08-trust-bridge.png)

これらは構図のテンプレートではなく、スタイル校正用のサンプルです。使うときは目の前の記事から比喩を作り直し、過去作のモチーフや構図をそのまま流用しないでください。

---

## インストール

リポジトリをクローン：

```bash
git clone https://github.com/helloianneo/ian-xiaohei-illustrations.git
cd ian-xiaohei-illustrations
```

skill を Codex の skills ディレクトリにコピー：

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ./ian-xiaohei-illustrations "${CODEX_HOME:-$HOME/.codex}/skills/"
```

インストール後、Codex で使う：

```text
Use $ian-xiaohei-illustrations この記事のために 小黑 の奇妙な本文挿絵を 5 枚設計して生成して。
```

---

## 使い方

### 挿絵の設計だけ行う

```text
Use $ian-xiaohei-illustrations まだ画像は生成しないで。
下の記事のどこに挿絵を入れる価値があるか分析して、5 枚程度の shot list を出して。
各画像について：どの段落の後ろに置くか、テーマ、核心の意味、構造タイプ、小黑 が何をしているか、注記案を書いて。

<記事を貼り付け>
```

### そのまま本文挿絵を生成する

```text
Use $ian-xiaohei-illustrations 下の記事から 小黑 の奇妙な本文挿絵を 4 枚生成して。
条件：16:9 横長、白地、黒の手描き線画、少量の赤・橙・青の手書き注記。

<記事を貼り付け>
```

### 一つの主張から 1 枚だけ作る

```text
Use $ian-xiaohei-illustrations 「信頼は叫んで得るものではなく、証拠を一つずつ敷いていくものだ」というテーマで本文挿絵を 1 枚生成して。
奇妙だけど清潔に。小黑 が核心動作を担うこと。
```

### 注記の言語を指定する

```text
Use $ian-xiaohei-illustrations 下の日本語記事から本文挿絵を 3 枚生成して。
本文は日本語だけど、画像内の注記は英語だけにして。1 か所 1〜4 語、言語を混ぜないで。

<記事を貼り付け>
```

### 画像内のタイトルや誤字を消す

```text
Use $ian-xiaohei-illustrations この画像を編集して、左上の「フロー図」というタイトルだけ消して。ほかはそのまま維持して。
```

さらに多くの例は [examples/prompts.md](examples/prompts.md)（中国語）を参照してください。

---

## 処理の流れ

この skill の流れ：

1. 記事・Markdown・Notion の内容・スクリーンショット・与えられたテーマを読む
2. 核心の主張、認知の転換点、フロー構造、ビジュアル化に向く段落を抽出する
3. まず shot list を出す。1 枚につき認知アンカーは一つだけ
4. 各画像の構造タイプを選ぶ：ワークフロー／システムの一部／ビフォーアフター／キャラクターの状態／概念的比喩／階層化された方法／地図とルート／短いコマ割り
5. ローテクで奇妙、けれど筋の通る物理的な比喩を作り直す
6. 小黑 に核心動作を担わせる
7. 画像は 1 枚ずつ、別々に画像モデルを呼んで生成する
8. QA チェックリストで確認：白地、余白、小黑 の動作、注記の言語と可読性、PPT っぽくないか、過去作の焼き直しでないか
9. 最終 PNG を保存し、用途とパスを報告する

---

## ディレクトリ構成

```text
.
├── README.md
├── README.en.md
├── README.ja.md
├── LICENSE
├── NOTICE.md
├── assets/
│   └── ian-wechat-qr.jpg
├── examples/
│   ├── images/
│   │   ├── 01-two-breakpoints.png
│   │   ├── 02-sort-by-purpose.png
│   │   └── ...
│   └── prompts.md
└── ian-xiaohei-illustrations/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   └── examples/
    └── references/
        ├── style-dna.md
        ├── xiaohei-ip.md
        ├── composition-patterns.md
        ├── prompt-template.md
        └── qa-checklist.md
```

実際に Codex にインストールするのはサブディレクトリだけです：

```text
ian-xiaohei-illustrations/
```

ルートの README・LICENSE・NOTICE・examples は GitHub 向けのドキュメントです。

---

## 注意点

- 画像内の文字は短いほど安定します。非ラテン文字（中国語・日本語・韓国語など）は英語より崩れやすいので、注記はより少なく短くしてください。
- 注記の言語はデフォルトで本文に追従します。英語の注記が欲しいときは、プロンプトで明示してください。
- 1 枚につき核心構造は一つだけ。記事をマニュアルにしないこと。
- 小黑 は必ず核心動作を担うこと。小黑 を消しても図が成立するなら、それは飾りです。
- サンプル画像は線の密度・余白・色の抑制・小黑 の関わり方を校正するためだけのものです。構図は流用しないでください。
- AI 画像モデルは誤字、存在しないラベル、スタイルのぶれ、余計なタイトルを出すことがあります。生成後は必ず確認してください。
- 誤字がひどい場合は注記の数を減らして再生成。言語が違ったり混ざったりする場合は、プロンプトで注記の言語を一つに固定してください。

---

## 関連プロジェクト

- [Ian Handdrawn PPT](https://github.com/helloianneo/ian-handdrawn-ppt) — 中国語の手描き技術 PPT 風ページ画像を生成する Skill
- [Awesome Claude Code Skills](https://github.com/helloianneo/awesome-claude-code-skills) — Claude Code の Skills / Agents / Plugins のキュレーション集
- [Obsidian + Claude AI Second Brain](https://github.com/helloianneo/obsidian-ai-second-brain) — Obsidian と Claude AI で個人ナレッジベースを作るガイド

---

## 作者について

**Ian（伊恩）** — プロダクトデザイナー / 一人会社の実践者 / AI Builder

AI チームで一人会社を作っています。

- GitHub: [helloianneo](https://github.com/helloianneo)
- X/Twitter: [@ianneo_ai](https://x.com/ianneo_ai)
- サイト: [www.ianneo.xyz](https://www.ianneo.xyz)
- WeChat: `ianneoxyz`
- メール: hello.neoc@gmail.com

---

## さらに知りたい方へ

この 小黑 挿絵 Skill は、AI で組み立てている個人の生産システムのなかの小さな道具の一つにすぎません。

AI をコンテンツ・ナレッジベース・ワークフロー・プロダクト化に使っているなら、サイトも読んでみてください：[www.ianneo.xyz](https://www.ianneo.xyz)。

まずは様子を見たい方は [X/Twitter](https://x.com/ianneo_ai) をフォローしてください。

Indie Builders Club に興味があれば、WeChat `ianneoxyz` に「OPC」と書いて申請してください。

<p>
  <img src="assets/ian-wechat-qr.jpg" alt="Ian の WeChat QR コード" width="120">
</p>

QR の読み取りが難しい場合は WeChat ID を検索してください：`ianneoxyz`。

---

## License

MIT License. See [LICENSE](LICENSE).
