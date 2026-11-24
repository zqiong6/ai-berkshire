[中文](README.md) | English | [日本語](README_JA.md)

# AI Berkshire — Value-Investing Research Framework for the AI Era

> "Price is what you pay, value is what you get." — Warren Buffett

**AI Berkshire** is a Claude Code / Codex skill pack that structures the methods of Buffett, Munger, Duan Yongping, and Li Lu into reusable AI research workflows.

This repository is a fork of the upstream framework. Upstream research reports and personal branding have been cleared so it can serve as a private research workbench. Put new reports under `reports/`, then run `python3 tools/reports_index.py`.

[Why not just ask an AI?](#why-not-just-ask-an-ai) · [Skills](#skills-22) · [Quick start](#quick-start) · [Reports index](reports/README.md) · [Design](#design-philosophy)

---

## Why not just ask an AI?

A plain chat answer is usually balanced and non-committal. This framework optimizes for **decision quality and discipline**:

1. Forced conclusions: pass / fail / gray zone, with price observation bands
2. Four-master adversarial lenses instead of one blended prompt
3. Anti-bias structure: information richness grades, inversion tests, veto lists, blank-space rules
4. Exact finance math via `tools/financial_rigor.py` (Decimal, multi-source checks)
5. Reproducible report structure across companies and over time
6. Multi-agent parallel research for team-style skills

<p align="center">
  <img src="assets/team-core-en.svg" alt="Team Lead scheduling four master agents" width="720" />
</p>

---

## Architecture

<p align="center">
  <img src="assets/architecture-en.svg" alt="AI Berkshire architecture" width="760" />
</p>

- **Skills**: 22 entry points for research, earnings, screening, portfolio, and thinking tools
- **Agents**: team skills run parallel master-perspective agents; light skills call tools directly
- **Tools**: exact math, retrieval, report audit

---

## Skills (22)

See the Chinese README skill tables for the full list and Chinese descriptions. Canonical workflow sources live in [`skills/`](skills/). Codex packages are generated into [`codex-skills/`](codex-skills/).

Key entry points:

| Skill | Use |
|-------|-----|
| `/investment-research` | Full four-master company research |
| `/investment-team` | Parallel multi-agent research |
| `/earnings-review` | Primary-source earnings deep read |
| `/industry-funnel` | Market → ≤10 → 3 funnel |
| `/portfolio-review` | Portfolio allocation and opportunity cost |
| `/news-pulse` | Fast attribution for price moves |
| `/financial-data` | Multi-source financial data rules |

---

## Quick start

```bash
git clone https://github.com/zqiong6/ai-berkshire.git
cd ai-berkshire

# Claude Code
./scripts/install-claude-commands.sh

# Codex
./scripts/install-codex-skills.sh
./scripts/install-codex-prompts.sh   # optional
```

Examples:

```bash
/investment-research Tencent
/industry-funnel AI compute
/portfolio-review Tencent 30%, cash 70%
```

Refresh the reports index after adding files under `reports/`:

```bash
git add -- reports/
python3 tools/reports_index.py
```

---

## Design philosophy

Four masters challenge each other: business quality, valuation, inversion/risk, and long-term civilization trends. Finance helpers live in `tools/financial_rigor.py` and `tools/valuation/`.

---

## Disclaimer

For learning and research only. Not investment advice. Do your own research.

## License

MIT License
