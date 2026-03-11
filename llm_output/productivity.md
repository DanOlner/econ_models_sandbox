# From Micro Production to Aggregate Productivity: Source Search and Summary

## The Ask

Starting from the [Solow residual](https://en.wikipedia.org/wiki/Solow_residual): search and summarise sources that can help think through building toy model examples — from the smallest two-firm illustrative interaction, through agent-based firm models, to full connection with known data and prediction — with the goal of showing the **transmission belt from actual production through to aggregate productivity theories**.

---

## The Solow Residual: Starting Point

The Solow residual is the portion of output growth not explained by growth in measured inputs (capital and labour). It's typically labelled "total factor productivity" (TFP) or, as Abramovitz put it, **"a measure of our ignorance."** The core accounting identity:

```
Y = A * F(K, L)
```

where A is the residual. The key problem for our purposes: **A is computed at the aggregate level and hides everything about what's actually happening at the firm level.** Reallocating resources toward more socially valued uses raises aggregate productivity without necessarily reflecting technology changes. Because aggregate data include non-technological reallocations, measuring technology requires disaggregated data.

---

## Level 1: Two-Firm / Two-Agent Illustrative Models

### Comparative Advantage as the Simplest Transmission Belt

The most minimal model of how firm-level differences produce aggregate productivity gains is the Ricardian comparative advantage setup. Even with just two agents and two goods, specialisation based on differing opportunity costs produces gains from trade that show up as higher aggregate output — a micro-to-macro transmission in its purest form.

- [CORE Econ: Comparative Advantage, Specialization and Markets](https://books.core-econ.org/the-economy/microeconomics/02-technology-incentives-03-comparative-advantage.html) — clean interactive two-agent setup
- [Krugman, Obstfeld & Melitz textbook chapter on Labour Productivity and Comparative Advantage](https://web.pdx.edu/~ito/Krugman-Obstfeld-Melitz/Manuscripts-second%20pass/M03_KRUG6654_09_SE_C03.pdf) — numerical worked examples

### What These Toy Models Show

Two sources of gains:
1. **Specialisation gain** — each agent concentrates on their most productive use
2. **Exchange gain** — both get to trade at better price ratios than autarky

These are the irreducible micro mechanisms. The modelling task is to show how these scale up and interact with real-world frictions.

---

## Level 2: Heterogeneous Firm Models (Analytic)

### Melitz (2003) — The Workhorse Model

The landmark paper combining firm heterogeneity with trade:

- Firms draw productivity from a distribution → heterogeneity
- Fixed export costs mean only the most productive firms export
- Trade liberalisation forces the least productive firms to exit
- **Result: intra-industry reallocation toward more productive firms raises aggregate industry productivity**

This is the key "transmission belt" at the industry level — trade doesn't just create new technology, it **reallocates resources** toward more productive firms.

- [Melitz (2003) "The Impact of Trade on Intra-Industry Reallocations and Aggregate Industry Productivity"](https://scholar.harvard.edu/files/melitz/files/aggprod_ecma.pdf) — original paper
- [Melitz & Redding, "Heterogeneous Firms and Trade"](https://scholar.harvard.edu/files/melitz/files/finalproofs.pdf) — handbook chapter with full exposition
- [Dave Donaldson's MIT lecture notes on firm heterogeneity](https://dave-donaldson.com/wp-content/uploads/Lecture-3-Firm-heterogeneity-theory-I.pdf)

### Hsieh & Klenow (2009) — Misallocation and Aggregate TFP

Directly addresses the question: how much does firm-level misallocation drag on aggregate TFP?

- Monopolistic competition model with heterogeneous firms
- Measures gaps in marginal products of capital and labour across plants
- **Finding: reallocating resources to equalise marginal products would raise TFP by 30-50% in China, 40-60% in India**
- Shows that aggregate TFP is not just about technology — it's about allocation

- [Hsieh & Klenow (2009) "Misallocation and Manufacturing TFP in China and India"](http://klenow.com/MMTFP.pdf)
- [MIT lecture notes on misallocation and productivity differences](https://economics.mit.edu/sites/default/files/inline-files/Lecture%2011%20-%20Misallocation%20and%20Productivity%20Differences%20across%20Countries.pdf)

---

## Level 3: Aggregation Theory — Connecting Micro to Macro

### Domar Aggregation

The formal framework for building aggregate TFP from industry/firm-level measures:

- Aggregate MFP growth = weighted average of component industry growth rates
- **Domar weights** = ratio of industry gross output to GDP (sum to more than 1, capturing indirect effects via intermediate inputs)
- When firms have markups (imperfect competition), cost-based Domar weights allow separate estimation of technological improvement vs. allocative efficiency

- [Basu & Fernald, "The Solow Residual, Domar Aggregation, and Inefficiency"](https://link.springer.com/article/10.1007/s11123-010-0205-z) — synthesises TFP measures
- [Murao, "Aggregate Productivity Growth Decomposition: an Overview"](https://www.mof.go.jp/english/pri/publication/pp_review/fy2017/ppr13_03_03.pdf)

### Koby — Aggregation in Heterogeneous-Firm Models

Extends classical aggregation theorems to environments with non-neoclassical, non-convex, and non-continuous production structures (fixed costs, increasing returns, entry-exit margins).

- [Koby, "Aggregation in Heterogeneous-Firm Models: Theory and Measurement"](https://economics.mit.edu/sites/default/files/publications/hetfirms_agg_202007.pdf)

### Production Networks

Micro shocks don't always wash out at the aggregate level. When industries are highly asymmetric in their roles as input suppliers, shocks propagate widely (the "granularity hypothesis"):

- [Carvalho & Tahbaz-Salehi, "Production Networks: A Primer"](https://www.kellogg.northwestern.edu/faculty/alirezat/ProductionNetworksPrimer.pdf)
- [Baqaee & Farhi, "Micro Propagation and Macro Aggregation"](https://bfi.uchicago.edu/wp-content/uploads/2022/10/BFI_WP_2022-136.pdf)

---

## Level 4: Agent-Based Computational Models

These explicitly compute aggregate variables "from the bottom up" — heterogeneous agents interact, and macro patterns emerge.

### Key Papers

- [Dosi et al., "Endogenous Growth and Global Divergence in a Multi-Country Agent-Based Model"](https://www.sciencedirect.com/science/article/abs/pii/S0165188919300302) — evolutionary microfoundations with international technology flows, trade interactions, exchange rate dynamics. Accounts for empirical regularities at macro, meso, and micro levels.
- [Dawid et al., "Agent-Based Macroeconomics"](https://sciencedirect.com/science/article/abs/pii/S1574002118300066) — handbook chapter surveying the field
- [The agent-based Solow growth model with endogenous business cycles](https://ideas.repec.org/p/zbw/cauewp/201501.html) — directly translates the Solow model into an agent-based framework
- [ABIDES-Economist](https://arxiv.org/html/2402.09563v1) — multi-agent simulator with heterogeneous households, firms, central bank and government; agents can learn strategies via interaction

### Software / Code Platforms

- [abcEconomics (ABCE)](https://github.com/AB-CE/abce) — Python library for agent-based economic modelling; includes production, consumption, trade functions. [Examples](https://abce.readthedocs.io/en/master/examples.html).
- [computational-economy](https://github.com/uwol/computational-economy) — implements an Arrow-Debreu model with factories using Cobb-Douglas/CES production functions
- [Economic Simulation Library (ESL)](https://github.com/INET-Complexity/ESL) — high-performance C++/Python library from INET Oxford
- [CoMSES Net Model Library](https://www.comses.net/codebases/?tags=agent-based+computational+economics) — repository of agent-based econ models with code
- [QuantEcon Solow-Swan tutorial](https://intro.quantecon.org/solow.html) — Python implementation of the Solow model as a starting point

---

## Level 5: Connecting to Data

### Firm-Level to Aggregate Empirics

- [Richiardi, "Firm Heterogeneity and the Aggregate Labour Share"](https://onlinelibrary.wiley.com/doi/10.1111/labr.12265) — shows firm heterogeneity remains invisible when using aggregate production functions
- [OECD Corporate Agent-Based (CAB) Model](https://www.oecd.org/content/dam/oecd/en/publications/reports/2021/07/a-new-firm-level-model-of-corporate-sector-interactions-and-fragility-the-corporate-agent-based-cab-model_dc8f4e70/e9de0097-en.pdf) — firm-level model of corporate sector interactions, calibrated to data
- [NBER project: Macroeconomics as Explicitly Aggregated Microeconomics](https://www.nber.org/programs-projects/projects-and-centers/7803-macroeconomics-explicitly-aggregated-microeconomics)
- ["From Firm Productivity Dynamics to Aggregate Efficiency"](https://academic.oup.com/wber/article/30/Supplement_1/S57/2897425) — World Bank Economic Review

---

## Sources That Explicitly Attempt the Micro-to-Macro Transmission Belt

The following directly tackle building the bridge from firm-level production to aggregate productivity measures:

1. **Baqaee & Farhi (2020), "Micro Propagation and Macro Aggregation"** — formal theory of how micro shocks aggregate, with production networks
2. **Koby (2020), "Aggregation in Heterogeneous-Firm Models"** — extends aggregation theory to non-neoclassical settings
3. **Dosi et al. (2019), agent-based multi-country growth model** — bottom-up computation showing how firm-level dynamics (knowledge accumulation, trade performance) create virtuous/vicious cycles visible at the macro level
4. **Hsieh & Klenow (2009)** — quantifies how firm-level misallocation shows up as lower aggregate TFP
5. **Melitz (2003)** — the micro mechanism (reallocation across heterogeneous firms) that drives aggregate industry productivity
6. **Basu & Fernald (2011)** — the Domar aggregation synthesis, connecting firm/industry residuals to the aggregate Solow residual
7. **OECD CAB Model (2021)** — practical agent-based model calibrated to firm-level data

---

## Suggested Modelling Progression

For building toy models that show the transmission belt:

1. **Two firms, two goods** — Ricardian comparative advantage. Show specialisation gains as "aggregate productivity improvement"
2. **N firms, one industry** — Melitz-style setup. Introduce productivity heterogeneity and show how entry/exit/reallocation changes the aggregate
3. **N firms, multiple industries with input-output links** — production network effects, Domar aggregation
4. **Agent-based simulation** — firms learn, adapt, enter/exit. Calibrate to actual firm-size and productivity distributions. Connect to Solow residual accounting
5. **Confront with data** — use firm-level micro data (e.g. census of manufactures) to validate that the model's aggregate TFP matches observed residuals
