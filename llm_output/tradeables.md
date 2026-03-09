# Digest: "Tradability, Productivity, and Regional Disparities: theory and UK evidence"

**Rice & Venables (2022), The Productivity Institute Working Paper No. 021**

---

## Summary of the argument

The paper asks: why do places with different sectoral structures have different earnings levels? The answer, they argue, depends critically on the **tradability** of each sector's output.

### The model

A Rosen-Roback spatial equilibrium with N places and S sectors. Key ingredients:

- **Cobb-Douglas production** using labour and land, with place-sector-specific Ricardian productivity `a_is`
- **Labour is perfectly mobile** across places and sectors (utility-maximising discrete choice, Frechet-distributed preferences)
- **Land is immobile** with supply elasticity `η` -- the scarce factor that makes places "expensive"
- **Sectors vary in tradability**: parameterised by iceberg trade cost `t_s`. Low `t_s` = highly tradable (can sell everywhere). High `t_s` = non-tradable (consumed locally)
- **Armington differentiation**: output from different places within a sector are imperfect substitutes (CES with elasticity `σ`)
- External trade with rest-of-world as price-taker for imports, with exports facing downward-sloping demand

### The core mechanism

Tradability determines the **price elasticity of demand** `E_s` a sector faces. This is the crucial link:

- **Perfectly tradable** (`t_s = 1`): demand elasticity → `σ` (very high, ~10). A productivity advantage leads to **output expansion**, drawing in labour, bidding up land rents and cost-of-living, raising nominal wages across all local sectors.
- **Perfectly non-tradable** (`t_s` → ∞): demand elasticity → 1 (unit elastic, from Cobb-Douglas upper-level preferences). A productivity advantage leads to **lower local prices**, lower cost-of-living, and potentially *lower* nominal wages.

So the same productivity shock has opposite wage effects depending on tradability.

### Two channels to wage variation

1. **Sector-differential effect** (~1/3 of variation): tradable sectors simply pay higher wages on average (correlated with skill intensity). This is a direct composition effect.

2. **Area-differential effect** (~2/3 of variation): the equilibrium response. Places biased towards tradable sectors have higher employment, higher rents, higher cost-of-living, and hence higher nominal wages *in all sectors* -- including non-tradables.

### The "sparsity-bias" measure

Since tradability is unobserved, they proxy it with **sectoral sparsity** -- how geographically concentrated a sector's employment is. Sparse sectors (concentrated in few places) ≈ tradable. Ubiquitous sectors (everywhere) ≈ non-tradable. A place's **sparsity-bias** is the employment-weighted average sparsity of its sectors.

Central finding: sparsity-bias accounts for ~75% of the variation in average earnings across 163 ITL3 areas of Great Britain.

### Historical application

The 1970s-80s deindustrialisation destroyed manufacturing employment (highly tradable, often sparse) in specific regions. These places saw their sparsity-bias decline and, as the model predicts, experienced relative earnings decline. The relationship between changes in sparsity-bias and changes in relative earnings 1971-1991 has a correlation of 0.56.

---

## Is this just comparative advantage restated?

**Your intuition is substantially correct, but with a specific spatial-equilibrium twist.** Here's the decomposition:

### What IS standard comparative advantage

The core of the model is **Ricardian comparative advantage** -- places have exogenous productivity differences across sectors, and they specialise accordingly. The authors are explicit about this (footnote 3: "We do not offer a theory of place-sector productivity -- there are simply Ricardian productivity differences"). The Armington/CES trade structure with iceberg costs is standard new trade theory (Eaton & Kortum 2002). The Cobb-Douglas preferences and CES sub-utility are textbook.

### What they add: the spatial equilibrium price transmission

The genuine contribution is working through how comparative advantage interacts with **tradability to shape local factor prices** via spatial equilibrium. Standard international trade models typically don't have:

- An immobile factor (land/housing) that gets bid up by local activity
- A cost-of-living channel where tradable-sector productivity advantages raise prices of local non-tradables
- The resulting **divergence between physical and revenue productivity** across all local sectors (not just the advantaged one)

This is where the Rosen-Roback spatial framework adds value over pure trade theory. The "area-differential" effect -- that all sectors in a tradable-biased place pay higher nominal wages -- is an equilibrium result that wouldn't emerge from a simple H-O or Ricardian model without local land markets.

### But the mobile-labour assumption does the heavy lifting

**Yes, labour mobility is crucial and arguably the most contestable assumption.** Perfect mobility (via Frechet discrete choice) ensures spatial utility equalisation. This means:

- Higher nominal wages in tradable-biased places are *exactly offset* by higher costs-of-living
- Real wages equalise across places in the model
- Regional "disparities" in nominal wages are an equilibrium feature, not a welfare problem

This is a strong claim. If labour is actually quite immobile (which decades of UK regional economics suggests -- people don't move from Hartlepool to London easily), then:

- Nominal wage differences ARE welfare differences
- The "equilibrium" interpretation collapses
- The model becomes descriptive of a pattern (tradable bias → higher wages) without the equilibrium mechanism actually operating

---

## Critique

### 1. Productivity is entirely exogenous -- the demand side is invisible

The model takes `a_is` (place-sector productivity) as given. There is no theory of *why* places have the productivity advantages they do. Agglomeration effects, knowledge spillovers, demand density, institutional quality -- all absent. The authors acknowledge this (p.17-18) but it's a fundamental limitation. Combined with Webber & Huaccha's critique, this model measures *revenue* productivity that conflates technical efficiency with demand conditions, pricing power, and scale effects.

### 2. The sparsity-tradability proxy is circular

The claim: sparse sectors are tradable, therefore sparsity-bias predicts wages. But sparsity (geographic concentration) is an *outcome* of productivity advantages combined with tradability, agglomeration economies, historical accident, and resource endowments. Using an endogenous outcome as a proxy for an exogenous parameter is problematic. A sector might be "sparse" because of resource dependence (mining), historical lock-in (Sheffield steel heritage), agglomeration (London finance), or simple path dependence -- none of which are "tradability" per se.

### 3. No role for aggregate demand

The entire model is supply-side. Output is determined by productivity and factor supplies. There is no demand deficiency, no unemployment, no capacity underutilisation. Every place is in equilibrium. This means it cannot address questions like: "what happens if government cuts spending in regions dominated by non-tradable public sector employment?" The answer in this model is simply that labour reallocates frictionlessly. In reality, it doesn't.

### 4. The land/housing mechanism may explain London, not the UK

The "area-differential" effect works through land rents and cost-of-living. This is primarily a story about London and the South East, where housing costs are indeed extreme. For much of the rest of the UK, the variation in housing costs is much smaller, and the mechanism weaker. The paper's own results show the relationship weakens substantially when London is excluded (R² drops from 0.74 to 0.54).

### 5. No dynamics, no hysteresis, no adjustment costs

The model is static comparative statics. The historical section (1970s-80s deindustrialisation) tells a story of *persistent* damage from losing tradable sectors, but the model has no mechanism for persistence. In the model, if manufacturing disappears, labour simply moves elsewhere and wages re-equilibrate. The observed persistence of regional disadvantage is *inconsistent* with the model's equilibrium assumptions. The authors note the "stickiness" of sector location in their conclusions, but this is a post-hoc addition, not something the model generates.

### 6. The "revenue vs physical productivity" distinction undermines the model's own measure

The paper itself notes (p.17-18) that tradability creates relationships between revenue productivity and scale that "may show up in sectors where technical efficiency is the same everywhere, and that have nothing to do with agglomeration." But the empirical work uses earnings (a revenue/nominal measure) as the dependent variable. The model's own logic says that high nominal wages in tradable-biased places reflect cost-of-living, not superior productive efficiency. So what exactly is the policy problem? If real wages equalise (as the model assumes), there is no welfare disparity to fix.

### 7. Constant returns to scale assumed throughout

The model assumes CRS in production. No increasing returns, no economies of scale. This is a significant omission for a paper about tradable sectors, where scale economies are often the *reason* for geographic concentration (and hence "sparsity"). Krugman's new economic geography (which is conspicuously absent from the references) would generate similar concentration patterns through increasing returns rather than exogenous Ricardian differences, with very different policy implications.

---

## Relationship to the Webber & Huaccha 2D GVA framework

The two papers are complementary but in tension:

- **Rice & Venables** treat productivity as exogenous and supply-side, then work out spatial equilibrium consequences. Demand only appears through consumer preferences for variety.
- **Webber & Huaccha** argue that GVA figures (and hence measured productivity) are fundamentally shaped by demand, prices, and scale -- precisely the variables that Rice & Venables take as equilibrium outcomes of exogenous productivity.

A synthesis would need to make productivity *endogenous* to demand conditions (Verdoorn/Kaldor), allow for non-equilibrium outcomes (unemployment, demand deficiency), and recognise that the spatial distribution of tradable sectors is itself an outcome of cumulative causation rather than simply Ricardian exogenous differences.

For our modelling aims, the Rice & Venables framework offers useful structure for thinking about how firm-level heterogeneity (in the Webber & Huaccha sense) interacts with tradability to produce spatial wage patterns. But it would need to be substantially modified to allow demand-side effects to operate.

---

## Critical review: are tradeable jobs the only "growth-relevant" kind?

The Rice & Venables model, and a broader tradition in regional economics, implies a hierarchy: tradeable sectors drive regional prosperity, non-tradeables are derivative. This section reviews literature that supports, critiques, and complicates that claim.

### Critiques of tradeable primacy

**1. Bentham, Bowman, de la Cuesta, Engelen, Erturk, Folkman, Froud, Johal, Law, Leaver, Moran & Williams (2013) -- "Manifesto for the Foundational Economy"**
*CRESC Working Paper 131.*
Argues that essential but mundane sectors -- utilities, food distribution, health, education, care -- constitute roughly half of all employment and are the material infrastructure of civilised life. Policy should focus on the quality and governance of these "sheltered" sectors rather than chasing high-value tradeable investment. Directly challenges the hierarchy that privileges export-oriented activity.
[CRESC Working Paper](https://hummedia.manchester.ac.uk/institutes/cresc/workingpapers/wp131.pdf)

**2. Froud, Haslam, Johal & Williams (2020) -- "(How) Does Productivity Matter in the Foundational Economy?"**
*Local Economy, 35(4), 316-336.*
Conventional productivity metrics are often meaningless or perverse in foundational sectors: higher "productivity" in health or social care can mean worse outcomes (faster throughput, less attention per patient). Challenges the assumption that productivity-led wage growth is the only route to household financial security, pointing to housing costs, employment conditions and social infrastructure as equally important.
[SAGE](https://journals.sagepub.com/doi/10.1177/0269094220956952)

**3. Ferreiro & Guillen (2023) -- "Revisiting Baumol's Disease: Structural Change, Productivity Slowdown and Income Inequality"**
*Intereconomics, 58(6).*
The structural shift into services is an inevitable feature of affluence, not a pathology. The real problem is not that non-tradeable services grow slowly in productivity but that gains from high-productivity tradeable sectors are distributed increasingly unequally. Reframes "Baumol's disease" as a distribution problem, not a growth problem.
[Intereconomics](https://www.intereconomics.eu/contents/year/2023/number/6/article/revisiting-baumol-s-disease-structural-change-productivity-slowdown-and-income-inequality.html)

**4. Arenas Jimenez et al. (2022) -- "Can Foundational Economy Save Regions in Crisis?"**
*Journal of Economic Geography, 23(3), 577-599.*
Regions heavily reliant on foundational sectors showed greater resilience during economic downturns. These sectors provide stable, place-bound employment that cannot be offshored -- directly challenging the notion that only tradeable sectors deliver meaningful regional outcomes.
[Oxford Academic](https://academic.oup.com/joeg/article/23/3/577/6759701)

**5. De Propris & Jones (2024) -- "Facing Up to the Foundational Economy: Regional Development, Public Policy and Employment in Wales"**
*Regional Studies.*
In Wales, the foundational economy accounts for close to half of all employment in former industrial districts. Treating foundational employment as merely derivative of tradeable activity ignores the reality that for many UK regions, the foundational economy *is* the economy. Policy must engage with it on its own terms rather than waiting for tradeable-sector revival that may never come.
[Taylor & Francis](https://www.tandfonline.com/doi/full/10.1080/00343404.2024.2435521)

### Support for tradeable primacy

**6. Moretti (2010) -- "Local Multipliers"**
*American Economic Review, 100(2), 373-377.*
Each new tradeable (manufacturing) job creates ~1.6 additional local non-tradeable jobs. For skilled/high-tech jobs, the multiplier reaches ~2.5. This is the key empirical basis for the policy view that attracting tradeable employers is the most efficient route to local job creation.
[Berkeley PDF](https://eml.berkeley.edu/~moretti/multipliers.pdf)

**7. Kemeny & Storper (2015) -- "Is Specialization Good for Regional Economic Development?"**
*Regional Studies, 49(6), 1003-1018.*
Growing absolute specialisation in tradeable industries is positively linked to metropolitan wages, while mere relative concentration is not. What matters for regional prosperity is building scale in tradeable activities that compete beyond local markets.
[Taylor & Francis](https://www.tandfonline.com/doi/full/10.1080/00343404.2014.899691)

**8. What Works Centre for Local Economic Growth (2024) -- "Understanding Tradable and Non-Tradable Sectors"**
Policy-facing evidence summary arguing that spatial productivity differences are driven primarily by the tradeable sector, that tradeables benefit more from technological change, and that when the tradeable sector shrinks it drags local non-tradeable employment down via the multiplier.
[What Works Growth](https://whatworksgrowth.org/insights/understanding-tradable-non-tradable-sectors/)

### Complications and nuances

**9. Faggio & Overman (2014) -- "The Effect of Public Sector Employment on Local Labour Markets"**
*Journal of Urban Economics, 79, 149-163.*
Public sector expansion creates ~0.5 additional local non-tradeable jobs but crowds out ~0.4 tradeable jobs, with no net private employment effect. Public spending acts as a local demand injection (like an export base funded by fiscal transfers), but displaces exactly the tradeable activity the primacy view privileges. Highly relevant to regions where the state is the dominant employer.
[ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0094119013000430)

**10. Federal Reserve Bank of Philadelphia (2022) -- "Anchor Impact: Understanding the Role of Higher Education and Hospitals in Regional Economies"**
Universities and hospitals -- nominally non-tradeable -- employed nearly 10 million people in the US. In 66 of the 100 largest US inner cities, anchor institutions are the largest employer. They attract students, patients and research funding from far beyond the local area, functioning as de facto exporters. Their "buy local" procurement also creates import-substitution multiplier effects, blurring the tradeable/non-tradeable line.
[Philadelphia Fed](https://www.philadelphiafed.org/community-development/workforce-and-economic-development/anchor-impact-understanding-the-role-of-higher-education-and-hospitals-in-regional-economies)

**11. UNCTAD (2021) -- "Digitalization of Services: What Does It Imply for Trade and Development?"**
Digitalisation is converting previously non-tradeable services into tradeable ones: telemedicine, remote education, cloud computing, fintech, platform-mediated professional services. The tradeable/non-tradeable boundary is a shifting technological frontier, not a fixed structural feature -- undermining policy frameworks built on a static classification.
[UNCTAD PDF](https://unctad.org/system/files/official-document/ditctncd2021d2_en.pdf)

**12. Richmond Federal Reserve (2025) -- "Impacts of Government Spending Changes on Local Economies"**
*Economic Brief 25-28.*
Local fiscal multipliers of 1.3-2.0 for government spending. For regions receiving large net fiscal transfers (military bases, federal agencies, pension payments), government spending functions as an "export base" -- money flowing in from outside the region. A region can prosper not by exporting goods but by "exporting" political claims on central government revenue.
[Richmond Fed](https://www.richmondfed.org/publications/research/economic_brief/2025/eb_25-28)

**13. Hanson (2024) -- "Local Employment Multipliers for Large Publicly Subsidized Firms"**
*Journal of Regional Science.*
Using synthetic control methods, finds that local multiplier effects of large subsidised firms (often tradeable) are smaller and more uncertain than Moretti's earlier estimates. If multipliers are smaller than claimed, the efficiency case for privileging tradeables over direct foundational investment weakens.
[Wiley](https://onlinelibrary.wiley.com/doi/full/10.1111/jors.12680)

### Summary

The tradeable-primacy view has strong theoretical and empirical foundations (Rice & Venables's price/wage mechanism, Moretti's multipliers, Kemeny & Storper on specialisation). But it faces three challenges: (1) the foundational economy literature argues that half the economy is non-tradeable by nature and its quality directly determines wellbeing; (2) the tradeable/non-tradeable boundary is increasingly porous due to digitalisation and the export-like functions of anchor institutions and fiscal transfers; (3) estimated multipliers justifying tradeable-sector subsidies may be smaller than originally claimed. For regions where tradeable sectors have departed (much of post-industrial UK), insisting on tradeable-primacy as the only development path risks neglecting the economy that actually exists.
