[中文](README.md) | [English](README_EN.md) | 日本語

# AI Berkshire — AI時代のバリュー投資リサーチフレームワーク

> "Price is what you pay, value is what you get." — Warren Buffett

**AI Berkshire** は Claude Code / Codex 向けの投資リサーチ Skill 集です。バフェット、マンガー、段永平、李録の方法論を構造化し、AI Agent で専門的な調査を進めます。

本リポジトリは上流フレームワークの fork です。上流のレポートと個人向け展示は削除済みで、個人のリサーチ作業台として使えます。新しい成果は `reports/` に置き、`python3 tools/reports_index.py` で索引を更新してください。

[なぜ直接AIに聞かないのか](#なぜ直接aiに聞かないのか) · [Skills](#skills22) · [クイックスタート](#クイックスタート) · [研究索引](reports/README.md) · [設計思想](#設計思想)

---

## なぜ直接AIに聞かないのか

普通のチャット回答は両論併記で終わりやすく、意思決定には足りません。本フレームワークが重視するのは **分析の質と規律** です。

1. 結論を強制：通過 / 不通過 / グレーゾーン＋価格観察帯
2. 四巨人視点の対立（事業・財務・逆張り・長期）
3. バイアス対策：情報豊富度、逆説テスト、拒否リスト、留白
4. `tools/financial_rigor.py` による正確な財務計算
5. 再現可能なレポート構造
6. チーム型 Skill のマルチ Agent 並列調査

<p align="center">
  <img src="assets/team-core.svg" alt="Team Lead が四巨人 Agent を並列スケジュール" width="720" />
</p>

---

## アーキテクチャ

<p align="center">
  <img src="assets/architecture.svg" alt="AI Berkshire アーキテクチャ" width="760" />
</p>

詳細な Skill 一覧は [中文 README](README.md) を参照。正本は [`skills/`](skills/)、Codex 用は [`codex-skills/`](codex-skills/) です。

---

## Skills（22）

代表例：

| Skill | 用途 |
|-------|------|
| `/investment-research` | 四巨人総合企業調査 |
| `/investment-team` | 並列マルチ Agent 調査 |
| `/earnings-review` | 一次資料の決算精読 |
| `/industry-funnel` | 全市場 → ≤10 → 3 の漏斗 |
| `/portfolio-review` | ポートフォリオ点検 |
| `/news-pulse` | 株価異動の短時間归因 |
| `/financial-data` | 財務データの交差検証規範 |

---

## クイックスタート

```bash
git clone https://github.com/zqiong6/ai-berkshire.git
cd ai-berkshire
./scripts/install-claude-commands.sh
./scripts/install-codex-skills.sh
```

例：

```bash
/investment-research テンセント
/industry-funnel AI算力
```

レポート追加後：

```bash
git add -- reports/
python3 tools/reports_index.py
```

---

## 設計思想

四巨人が互いに挑戦する設計です。財務検証は `tools/financial_rigor.py` と `tools/valuation/` を使います。

---

## 免責

学習・研究目的のみ。投資助言ではありません。自己責任で判断してください。

## License

MIT License
