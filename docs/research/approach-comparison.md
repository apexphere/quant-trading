# Approach Comparison: Personal Quant Trading AI Agent

> Research conducted Feb 2026. Constraint: No capability to train models.

## What Exists (Real, Working Frameworks)

| Framework | What It Does | Best For | Complexity |
|-----------|-------------|----------|------------|
| **Microsoft Qlib** | Full quant platform: data, ML, backtesting, RL | Production-grade research | High |
| **Microsoft RD-Agent** | LLM-powered automated factor mining + model optimization | Automating R&D process | High |
| **FinRL** | Reinforcement learning for trading (stocks, crypto, portfolio) | Learning RL approach | Medium |
| **FinGPT** | Financial LLMs for sentiment analysis, not trading | Sentiment signals | Medium |
| **VectorBT** | Ultra-fast vectorized backtesting | Research & optimization | Low-Medium |

## Constraint: No Model Training

**What still works without training:**

| Approach | Training Needed? | How It Works |
|----------|-----------------|--------------|
| **Multi-factor ranking** | ❌ None | Pure math — rank stocks by momentum, value, etc. |
| **RD-Agent** | ❌ None | Uses API LLMs (GPT-4, Claude) — no local training |
| **Pre-trained FinGPT** | ❌ None | HuggingFace inference API — sentiment signals |
| **LightGBM** | ⚠️ Minutes on laptop | Lightweight, trains on CPU in <5 mins |

**What's ruled out:**

- FinRL (RL needs training loops)
- Custom LLM fine-tuning
- Deep learning models (LSTM, Transformers)

---

## Two Viable Options

### Option A: Multi-Factor + LLM Sentiment

You build factors manually, LLM adds sentiment signal.

**Components:**
- Multi-factor ranking (momentum + value + quality)
- LLM (Claude/GPT via API) for news sentiment as one factor
- VectorBT for backtesting
- Manual or simple rule-based execution

### Option B: RD-Agent (Automated R&D)

LLM proposes factors, system tests them automatically.

**Components:**
- Microsoft RD-Agent (uses GPT-4/Claude API)
- Qlib for data + backtesting
- LLM reads financial reports, proposes factors
- System validates with backtesting
- Cost: ~$10 per optimization cycle (API calls)

---

## Comparison

| | **Option A: Multi-Factor + LLM Sentiment** | **Option B: RD-Agent (Automated R&D)** |
|---|---|---|
| **What it is** | You build factors, LLM adds sentiment signal | LLM proposes factors, system tests them automatically |
| | | |
| **Pros** | | |
| Simplicity | ✅ You understand every piece | ❌ More complex system to set up |
| Control | ✅ Full control over logic | ⚠️ LLM proposes, you review |
| Cost | ✅ Minimal API calls | ⚠️ More API calls (~$10/cycle) |
| Learning | ✅ Learn quant fundamentals | ⚠️ Abstracts away the learning |
| Dependencies | ✅ Fewer moving parts | ❌ Qlib + RD-Agent + Docker |
| Time to start | ✅ Days | ❌ Weeks (setup + learning curve) |
| | | |
| **Cons** | | |
| Scalability | ❌ Manual factor research | ✅ Automated discovery |
| Alpha discovery | ❌ Limited to your ideas | ✅ LLM reads reports, finds patterns |
| Iteration speed | ❌ Slow (you do the work) | ✅ Fast (automated cycles) |
| Edge | ❌ Common factors = crowded | ✅ Novel factors possible |

---

## Decision Matrix

| If you want... | Choose |
|----------------|--------|
| Learn quant trading from ground up | **Option A** |
| Ship something fast, understand it | **Option A** |
| Automate the boring research work | **Option B** |
| Find novel factors others miss | **Option B** |
| Minimize dependencies | **Option A** |
| Long-term competitive edge | **Option B** |

---

## Recommendation

**Start with Option A to learn the fundamentals. Graduate to Option B once you understand what a factor is, how backtesting works, and why risk control matters.**

Otherwise RD-Agent is a black box you can't debug.

---

## Open Questions (Need More Research)

1. **Broker integration** — Interactive Brokers API specifics, paper trading setup
2. **NZ/AU specific** — Tax implications, available brokers, local data sources
3. **Real costs** — API fees, data subscriptions, compute for backtesting

---

## Sources

- [Microsoft Qlib](https://github.com/microsoft/qlib) — 15k+ stars, actively maintained
- [Microsoft RD-Agent](https://github.com/microsoft/RD-Agent) — LLM-powered R&D automation
- [FinRL](https://github.com/AI4Finance-Foundation/FinRL) — RL for finance
- [FinGPT](https://github.com/AI4Finance-Foundation/FinGPT) — Financial LLMs
- [VectorBT](https://vectorbt.dev/) — Fast backtesting

---

## 2026 Trend Analysis

> Last updated: 2026-02-27

### Current Industry Signals

| Signal | Data | Implication |
|--------|------|-------------|
| **RD-Agent GitHub** | 11.4k ⭐, pushed 2026-02-26 | Active development, growing adoption |
| **RD-Agent-Quant** | Accepted at NeurIPS 2025 | Academic validation of multi-agent approach |
| **Qlib GitHub** | 37.9k ⭐ | Mature infrastructure, production-tested |
| **arxiv q-fin papers** | Cross-listed with cs.AI, cs.LG | AI/ML is dominant research theme |

### Verdict: Option B is where the industry is heading

The 2026 research frontier is **multi-agent LLM systems for automated R&D**:
- Microsoft investing heavily (Qlib + RD-Agent ecosystem)
- NeurIPS acceptance validates the approach
- Factor discovery automation is the competitive edge

### However: Recommendation Unchanged

> **Start with Option A to learn fundamentals. Graduate to Option B.**

Why? The people publishing NeurIPS papers on RD-Agent understand factors, backtesting, and risk control deeply. They automated what they already understood.

Starting with Option B without understanding Option A = black box you can't debug.

**The trend being "AI agents" doesn't mean you should start there.**

---

## Changelog

| Date | Update |
|------|--------|
| 2026-02-27 | Added 2026 trend analysis with GitHub/NeurIPS signals |
| 2026-02-27 | Initial research: approach comparison, pros/cons, recommendation |
