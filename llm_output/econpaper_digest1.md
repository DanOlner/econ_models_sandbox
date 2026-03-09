# Digest: "Rethinking productivity: the crucial role of demand"

Claude Code generated doc based on prompts that start here.

**Webber & Huaccha (2024), Journal of Post Keynesian Economics, 47:1, 55-83**

## Purpose of this digest

This writeup serves a specific modelling goal: building a toy economy of heterogeneous firms where we can test questions like *"if x% of firms had this mix of productivity structures, what difference would demand vs supply changes make to the toy model economy as a whole?"* -- parameterised so it can be applied to actual UK spatial data (e.g. sub-national GVA, firm-level data from the Annual Business Survey).

---

## Core argument

Conventional productivity analysis treats GVA (Gross Value Added) as a **one-dimensional scalar** -- a single number on a continuum. Webber & Huaccha argue this is fundamentally misleading because it collapses away the distinct roles of **prices, costs, and scale** that together determine the GVA figure. They propose a **two-dimensional (2D) representation** that decomposes GVA into its geometric constituents and, critically, makes the role of **aggregate demand** visible.

## The 2D GVA framework

At firm level, GVA is calculated as:

```
GVA = Total Revenue - Intermediate Costs
    = (S * Q) - (C * Q)
    = (S - C) * Q
```

Where:
- **S** = average sales price per unit
- **C** = average cost of goods/services used up or transformed per unit (intermediate inputs)
- **Q** = quantity of units sold

GVA is therefore the **area of a rectangle** SABC in price-quantity space, with height (S - C) representing the markup/margin and width Q representing scale. This is the paper's key geometric insight.

### Components within the GVA rectangle

The (S - C) margin decomposes into:
- **Net profit**
- **Labour costs** (wages)
- **Capital depreciation**
- **Other costs** (utilities, etc.)

These sub-areas compete for share of the GVA rectangle. Labour unions push for wage share; shareholders push for profit share; the total is bounded by the area (S - C) * Q unless S, C, or Q change.

## The isoGVA curve

Firms with identical 1D GVA figures can sit at very different points in 2D space. The paper introduces the **isoGVA curve**: a hyperbola in (Ratio of S/C, Q) space where all points yield the same GVA value. This is crucial:

- **High-S/C, low-Q firms** (top-left): specialist/luxury producers, high markup, low volume. Example: Morgan cars.
- **Low-S/C, high-Q firms** (bottom-right): mass producers, thin margins, high volume. Example: mass-market auto manufacturers.

These two firm types have identical GVA but completely different responses to demand shocks, cost shocks, and policy interventions.

## Why demand matters (and is hidden in 1D)

The 1D view makes GVA look like a pure supply-side measure -- how efficiently inputs convert to outputs. The 2D view reveals that **Q is directly driven by demand**. Changes in GVA can come from:

1. **Reducing C** (supply-side: cost savings, offshoring, market power over suppliers)
2. **Increasing S** (demand-side via pricing power, but also supply-side via quality improvements)
3. **Increasing Q** (demand-side: aggregate demand, population, trade, consumer confidence)

The paper argues the post-2008 productivity puzzle (flatlining GVA growth) cannot be understood without recognising that **austerity, wage stagnation, and depressed aggregate demand** directly suppress Q and hence GVA, regardless of supply-side efficiency.

### Spatial dimension

The supply chain example (dairy farmer -> yoghurt producer -> supermarket) shows GVA has a **clear spatial pattern**: retail in urban areas with high demand captures more GVA via market power, while rural producers have lower GVA despite similar input-output efficiency. This means regional productivity differentials partly reflect demand geography, not just supply-side capability.

---

## Relevance to our modelling aims

### What a toy model should capture

The paper's framework maps directly onto a parameterisable firm-level model:

**Per-firm state variables:**
- `S_i` -- average sale price
- `C_i` -- average intermediate input cost
- `Q_i` -- quantity sold
- `GVA_i = (S_i - C_i) * Q_i` -- derived, not primitive

**Within-GVA distribution (optional, for richer models):**
- `w_i` -- labour share of GVA
- `k_i` -- capital depreciation share
- `pi_i` -- net profit share
- Such that `w_i + k_i + pi_i + other_i = 1`

**Firm heterogeneity via position on isoGVA:**
- Firms can be parameterised by their position in (S/C ratio, Q) space
- A "luxury" firm type: high S/C, low Q
- A "mass-market" firm type: low S/C, high Q
- A spectrum in between

### Demand vs supply shocks as model experiments

The key question -- *"what difference would demand vs supply changes make?"* -- becomes testable:

| Shock type | Mechanism | Parameters affected |
|---|---|---|
| **Aggregate demand increase** | More consumers / higher spending | Q_i increases (possibly heterogeneously by firm type) |
| **Aggregate demand decrease** (austerity) | Reduced spending | Q_i falls |
| **Cost reduction** (supply-side) | Better technology, cheaper inputs | C_i falls |
| **Price increase** (market power) | Firms raise prices | S_i rises (but may reduce Q_i via elasticity) |
| **Wage push** | Higher labour costs within GVA | Redistribution within (S-C)*Q, may affect S or C depending on model |

### What the paper warns against

- **Do not use an aggregate production function.** The Cambridge Capital Controversies showed this is logically flawed (reswitching, capital reversing). The paper is explicit: aggregating heterogeneous firms into Y = f(K,L) commits the "fallacy of composition."
- **Do not treat TFP as meaningful.** The Solow residual is "a measure of our ignorance" and lumps demand effects, market power, institutional factors, and actual technical change into one number.
- **Do not assume firms operate on their technical frontier.** Most don't (Hwang, Lee & Zhu 2016). The gap between actual and frontier performance is itself influenced by demand conditions.

### Parameterisation for UK spatial data

To apply to UK geography, the model would need:

1. **Firm-type distributions by region**: what share of firms in each area are high-markup/low-volume vs low-markup/high-volume? The Annual Business Survey (ABS) provides approximate GVA (aGVA) at firm level, covering ~3/4 of the economy. With revenue and intermediate cost data, S*Q and C*Q can be recovered (though S, C, Q individually may not be separable without volume data -- the paper flags this as a key data limitation).

2. **Demand proxies by region**: population, income levels, trade exposure, public spending levels. These drive Q heterogeneously across space.

3. **Supply chain linkages**: the yoghurt example shows GVA cascades spatially along supply chains. Urban retail captures disproportionate GVA via market power over rural/peri-urban producers.

4. **Market structure parameters**: degree of competition, markup behaviour (Kaleckian pricing -- markup proportional to market concentration).

### Key modelling insight from the paper

The central testable proposition is: **in an economy where a large share of firms are demand-constrained (Q below potential), supply-side interventions (reducing C, improving technology) will have less impact on aggregate GVA than demand-side interventions (increasing Q).** Conversely, in a supply-constrained economy, the reverse holds. The mix of firm types and their positions in 2D space determines which regime the economy (or region) is in.

This is directly parameterisable: set up N firms with distributions over (S, C, Q), apply shocks, measure aggregate GVA response.

---

## Limitations and gaps (for our purposes)

- The paper is **conceptual, not formal**. It provides no equations of motion, no dynamics, no equilibrium conditions. We would need to supply these.
- **Price elasticity of demand** is discussed but not formalised. For a working model, we need Q_i = f(S_i, aggregate_demand, ...) with specified functional forms.
- **Firm interaction** (competition, supply chains) is discussed qualitatively but not modelled. An agent-based or input-output structure would be needed.
- **No treatment of entry/exit**, investment dynamics, or credit constraints -- all relevant for a richer model.
- **Data separation problem**: the paper notes that available firm-level data typically gives S*Q and C*Q but not the individual components. This constrains calibration unless supplemented with industry-level price/volume indices.

---

## Related literature: support and critique of the 2D GVA framework

### Supporting ideas

**1. Foster, Haltiwanger & Syverson (2008) -- "Reallocation, Firm Turnover, and Efficiency: Selection on Productivity or Profitability?"**
*American Economic Review, 98(1), 394-425.*
Introduces the critical distinction between physical productivity (TFPQ) and revenue productivity (TFPR), where TFPR = P x TFPQ. Revenue-based productivity measures confound technical efficiency with demand and price effects. Physical productivity is *inversely* correlated with price while revenue productivity is *positively* correlated -- directly supporting the argument that 1D productivity conceals the demand dimension.
[AER article](https://www.aeaweb.org/articles?id=10.1257/aer.98.1.394)

**2. Ehrlich, Haltiwanger, Jarmin, Johnson & Shapiro (2019) -- "Minding Your Ps and Qs: Going from Micro to Macro in Measuring Prices and Quantities"**
*AEA Papers and Proceedings, 109, 182-186.*
Argues that macro indicators (output, productivity, inflation) are built from a fragmented statistical system where prices and quantities are collected separately by different agencies. Advocates item-level transactions data to construct price and quantity indices jointly, revealing patterns invisible in current aggregation. Supports the contention that aggregate measures obscure the price-quantity decomposition.
[NBER Working Paper](https://www.nber.org/papers/w25465)

**3. Felipe & McCombie (2014) -- "The Aggregate Production Function: 'Not Even Wrong'"**
*Review of Political Economy, 26(1), 60-84.*
Demonstrates that estimations of aggregate production functions are tautological: because value added is definitionally V = wL + rK (an accounting identity), regressions of value added on labour and capital produce good fits regardless of whether a production function exists. Devastating for TFP measurement, directly supporting the rejection of conventional productivity models.
[Taylor & Francis](https://www.tandfonline.com/doi/full/10.1080/09538259.2013.874192)

**4. Kaldor (1966) / Verdoorn (1949) -- Verdoorn's Law and cumulative causation.**
Verdoorn's law: productivity growth is a positive function of output growth, implying demand drives productivity rather than the reverse. Kaldor formalised this as cumulative causation: demand growth stimulates investment embodying technical progress, raising productivity, improving competitiveness, further raising demand. The canonical demand-side productivity theory, establishing that Q is an active driver of productivity, not a passive reflection of supply-side efficiency.
[Overview of Verdoorn's Law](https://en.wikipedia.org/wiki/Verdoorn%27s_law) | [Ferranti & Guilhoto (2023)](https://link.springer.com/article/10.1007/s40888-023-00294-y)

**5. Thirlwall (1979, 2019) -- Balance of payments constrained growth.**
*Banca Nazionale del Lavoro Quarterly Review (1979); Review of Keynesian Economics, 7(4), 2019.*
Long-run growth is constrained by demand for exports relative to income elasticity of imports. Productivity growth is endogenous to the demand-determined actual growth rate. Provides the macroeconomic scaffolding: if aggregate demand constrains output growth, it constrains the Q dimension of the 2D decomposition.
[2019 reflections](https://www.elgaronline.com/view/journals/roke/7-4/roke.2019.04.09.xml)

**6. Sawyer (2012) -- "The Kaleckian Analysis of Demand-Led Growth"**
*Metroeconomica, 63(1), 7-28.*
Kaleckian models provide a demand-led view where firms set prices as markups over costs (not via marginal cost pricing) and output is determined by effective demand. Investment, capacity utilisation and hence measured productivity are all responsive to demand. Supports the use of Kaleckian pricing theory for the S dimension.
[Wiley](https://onlinelibrary.wiley.com/doi/10.1111/j.1467-999X.2011.04127.x)

**7. Lee, Frederic S. (1998) -- *Post Keynesian Price Theory***
*Cambridge University Press.*
Synthesises markup pricing, normal-cost pricing, and administered pricing, drawing on 100+ empirical studies of actual business pricing. Firms overwhelmingly set prices as cost-plus markups, not via supply-demand clearing. Provides the microeconomic foundation for the S component being set by institutional and competitive factors.
[Cambridge UP](https://www.cambridge.org/core/books/post-keynesian-price-theory/BD5C465EC1E7AFFEF33D45B8BA25037B)

**8. Haldane (2017, 2018) -- "Productivity Puzzles" and "The UK's Productivity Problem: Hub No Spokes"**
*Bank of England speeches.*
Documented extreme heterogeneity in UK firm productivity with a "long tail" of low-productivity laggards. While framed partly as a diffusion problem (supply-side), the emphasis on *distribution* of firm-level productivity -- and which firms grow vs stagnate -- is consistent with the view that demand conditions (who wins customers) shape aggregate productivity through the Q channel.
[2018 speech](https://www.bankofengland.co.uk/-/media/boe/files/speech/2018/the-uks-productivity-problem-hub-no-spokes-speech-by-andy-haldane) | [2017 speech](https://www.bankofengland.co.uk/-/media/boe/files/speech/2017/productivity-puzzles.pdf)

### Critiques and challenges

**9. De Loecker & Warzynski (2012) -- "Markups and Firm-Level Export Status"**
*American Economic Review, 102(6), 2437-2471.*
Develop methods to estimate firm-level markups from production data using cost-minimisation conditions, without specifying competition mode. Challenge: mainstream IO already has sophisticated markup estimation tools. What does the 2D framework add beyond existing techniques? Moreover, De Loecker-Warzynski operates *within* a production function framework that Webber & Huaccha reject, so the two approaches may talk past each other.
[AER article](https://www.aeaweb.org/articles?id=10.1257/aer.102.6.2437)

**10. Services sector measurement -- Griliches (1992), Moulton (2018)**
*Griliches (ed.), Output Measurement in the Service Sectors (NBER, 1992); Moulton, "The Measurement of Output, Prices, and Productivity" (Brookings, 2018).*
In services (which dominate modern economies), separating prices from quantities is notoriously difficult. What is the "quantity" of a legal consultation or a software licence? If P and Q cannot be reliably decomposed at firm level in services, the 2D framework becomes hard to operationalise precisely where it matters most.
[NBER book](https://ideas.repec.org/b/nbr/nberbk/gril92-1.html) | [Moulton (2018)](https://www.brookings.edu/wp-content/uploads/2018/07/Moulton-report-v2.pdf)

**11. Neoclassical responses to CCC -- Samuelson (1966), Cohen & Harcourt (2003)**
*Samuelson, "A Summing Up," QJE (1966); Cohen & Harcourt, "Whatever Happened to the Cambridge Capital Theory Controversies?" JEP (2003).*
While Samuelson conceded the logical validity of reswitching/capital reversal, the neoclassical response retreated to Arrow-Debreu general equilibrium formulations that do not require aggregate capital or production functions. If modern neoclassical theory does not rely on APFs (even if applied work still does), the CCC critique may not land as forcefully against the theoretical mainstream.
[Cohen & Harcourt (2003)](http://piketty.pse.ens.fr/files/CohenHarcourt03.pdf)

**12. General equilibrium feedback -- the partial equilibrium limitation**
The 2D framework operates at firm level: GVA = (S - C) * Q. But one firm's sale price is another's intermediate cost, and aggregate demand is itself the sum of all firms' value added. A rise in markups economy-wide reduces real wages and hence consumer demand (Q channel); expansion in Q across competitors pushes down prices (S channel). Without accounting for these feedbacks, the decomposition risks being descriptively interesting but analytically incomplete. Dutt (2012) discusses stability conditions for Kaleckian demand-led growth that address some of these issues.
[Dutt (2012)](https://onlinelibrary.wiley.com/doi/10.1111/j.1467-999X.2011.04148.x)
