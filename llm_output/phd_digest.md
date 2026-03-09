# PhD Thesis Digest: "An Agent-Based Modelling Approach to Spatial Economic Theory"

**Author:** Dan Olner | **Institution:** University of Leeds, School of Geography | **Date:** June 2013

---

## Overall Summary

This thesis develops an agent-based modelling (ABM) framework for spatial economics, culminating in a "transmission belt" model that connects supply and demand across space. The core motivation is that most spatial economic theory was built during a period of declining transport costs, but climate change and oil depletion may reverse this trend -- and the implications are poorly understood. The thesis engages deeply with Geographical Economics (GE/New Economic Geography), extracting useful tools (especially CES utility functions) while using ABM to escape GE's restrictive "mathematical straitjacket." Two key obstacles for ABM in spatial economics are identified: (1) a lack of attention to model dependencies, and (2) a "year zero" mentality that dismisses pre-computational modelling traditions.

---

## Chapter 1: Introduction

### Research Questions
1. How do changing space costs affect the morphology of the spatial economic landscape, and how does the resulting morphology feed back into actors' choices?
2. What obstacles have stopped ABM from tackling the "big questions" of spatial economics?

### Formal Aims
- Develop an ABM spatial economic framework where agents with heterogeneous locations can optimise welfare given changing costs.
- Use the development process to identify obstacles preventing ABM from fulfilling its potential in spatial economic analysis.

### Key Arguments Introduced
- **ABM suffers from a "streetlight effect"**: its OOP methodology has shaped research questions away from core spatial economic problems, creating "a unique straitjacket of its own making."
- **Dependencies matter**: coding choices in one area constrain what is possible elsewhere. These dependencies carry real meaning, not just technical inconvenience.
- **Descriptive vs. functional mapping**: ABM's affinity with OOP tempts modellers toward making code objects resemble reality rather than serving analytical purpose.
- **ABM should learn from economic modelling history**, not reject it wholesale.
- **Emergence is not explanation**: discovering emergent behaviour should be the start of investigation, not the end.

### Three Model Scenarios (in order of complexity)
1. Mobile People, static Firms (partial model)
2. Mobile Firms, static People (partial model)
3. Transmission belt model (general model linking supply and demand)

---

## Chapter 2: Economic and Spatial Concepts

### Fundamental Economics
- **Factors**: Capital (K) and labour (L) as aggregate inputs; GE substitutes manufacturing (M) vs. agriculture (F). The thesis foregrounds actors' time as the key factor.
- **Utility functions**: Cobb-Douglas (U = F^a * M^b) and CES (constant elasticity of substitution). The CES function is central -- its "love of variety" property means access to more goods varieties increases utility even under a fixed budget. The parameter rho controls substitutability.
- **Production**: A smooth economies of scale function is used instead of GE's fixed-cost approach, enabling the transmission belt model to work with agent-level decisions.
- **Market structure**: Traces the path from perfect competition through Chamberlin's monopolistic competition to Dixit-Stiglitz (1977), which made monopolistic competition tractable and underpins GE.

### Spatial Economics
- **Classical location theory**: Von Thunen (agricultural land-use rings), Weber (industrial location triangles), Christaller/Losch (central place theory).
- **Transport costs**: The thesis uses linear distance costs for goods and asymptotic time-budget costs for people (commuting). GE's "iceberg" model (goods melt during transport) is discussed.
- **The GE core model**: Detailed disassembly of Krugman's core-periphery model showing how mobile workers choosing between regions trigger cumulative causation via home market and price index effects. The thesis extracts useful components while critiquing the tight interdependence of assumptions.
- **Externalities**: Technological (pure), pecuniary, Marshall (same-industry concentration), and Jacobs (diversity-driven). The thesis introduces a novel **density cost** as a proxy for proximity costs (land, congestion), calculated per agent.
- **First vs. second nature**: Exogenous spatial features vs. interaction-generated effects. The thesis argues these become practically indistinguishable almost immediately.

### Strategic Simplifications
Three areas explicitly excluded: infrastructure/network development, non-transport trade costs, and risk/uncertainty.

---

## Chapter 3: Assumptions and Agent-Based Modelling

### On Modelling Assumptions
- Engages deeply with Friedman (1953): assumptions and implications are logically interchangeable; what counts as "crucial" depends on the problem. The billiard player, vacuum, and leaf-maximisation examples illustrate domains of validity.
- Defends simplicity as a practical heuristic (contra Edmonds' critique of Occam's Razor).
- "Heroic assumptions" must be judged by whether they open productive analytical avenues, not by surface realism.

### ABM's Methodological Position
- ABM's roots in OOP (encapsulation, loose coupling) create structural biases in how models are built.
- The thesis distances itself from complexity-first ABM: agents are used to explore spatial economic outcomes from heterogeneous locations, not to demonstrate emergence or complexity per se.
- **Descriptive vs. functional mapping**: the chapter's central argument. Code structures should serve analytical purpose, not mirror reality.
- **Virtual worlds vs. engines of analysis**: ABM is structurally suited to virtual-world building, but generating a target phenomenon is a candidate explanation, not a confirmed one. Schelling's segregation model illustrates the distinction.

### Key Philosophical Arguments
- **Levels of explanation coexist**: the ideal gas law (macro) was never abandoned when statistical mechanics (micro) arrived. Neither macro nor micro automatically invalidates the other.
- **Zero-intelligence agents** bidding randomly under budget constraints can achieve near-perfect market efficiency -- suggesting structure matters more than cognitive sophistication for many problems.
- **Three types of prediction**: forecasting, backcasting, and "ontological prediction" (discovering structural features, like tectonic plates).

### Bridging Theory and ABM
- Fowler's failed attempt to recreate the Krugman core model in agent form demonstrates that analytic-to-ABM translation is non-trivial.
- Space disrupts market-clearing assumptions: heterogeneous locations prevent a single clearing market. ABM offers value here via Leijonhufvud's "laws of motion" (e.g. "if stock exceeds target, lower price").
- Utility and production functions are defended as analytical tools within an agent framework, not psychological claims.

---

## Chapter 4: The Model Framework

### Architecture
- **Space types**: Spaceless, two-region, continuous 1D line, continuous 2D plane -- all normalised to size 1. Space type only restricts location options; all other features remain identical.
- **Timeline**: Each "day," an Action Permuter calls all Actors. People and Firms are permuted in separate bins to avoid timing artifacts.
- **Three decision modes**: Instant (one-step optimisation), Feedback (act-wait-respond), Reflex (reactive responses outside the Timeline).

### People (Consumer Agents)
- Budget of 1 "day" per iteration, spent on commuting and/or labour/goods.
- **Bundle mechanism**: Each turn, generate candidate location-bundles (random + nearby + current), calculate best available wage minus density cost, optimise utility from spending on available goods, select the best bundle, move there.
- **Two optimisation methods**: Hill-climber (stochastic, function-agnostic) and constrained optimiser (analytic CES optimum). Both converge to the same result.
- **Density cost**: Per-agent proximity cost calculated from nearby agents, subtracted from wages.

### Firms (Producer Agents)
- Location, wage offer, good price, production function, stock level.
- **Decision-making**: DMR (Data-Meaning-Response) feedback -- perturb location, wait, check revenue change, continue or revert. A blind search.
- In transmission belt models: "granular" reflex-based price adjustments targeting stock levels.

### Space Costs
- **Goods**: Linear (P_g = p_g + c*d). The ratio p/c defines "value density."
- **People**: Asymptotic time-budget constraint (cost becomes infinite at the commute limit).
- **Density cost**: Normalised sum of nearby agents' proximity, multiplied by a factor.

### Design Principles
- No money as a flowing resource (demonstrated that random money exchange produces persistent inequality). People's time is the currency.
- Functional mapping over descriptive mapping throughout.
- Partial models fix most variables to isolate specific dynamics.

---

## Chapter 5: Testing Models

### Validation Tests
1. **CES utility test**: Love of variety property confirmed -- utility increases at a decreasing rate with more goods varieties under budget constraint.
2. **Cobb-Douglas test**: Share parameter delta exactly determines sector income. Price changes in one sector have zero effect on the other -- confirmed both analytically and in agent runs.
3. **Hill-climber vs. constrained optimiser**: Both converge to the same optimum; constrained is faster/cheaper but hill-climber is more flexible.
4. **Distance interaction**: High rho (substitutable goods) concentrates demand on nearest firms; low rho (love of variety) spreads demand across distant firms. A "double-dip" demand structure is identified analytically.
5. **Black hole test**: Without dispersive forces, all agents collapse to a single point -- confirming expected behaviour.

### Partial Model Results

**Mobile People with density cost (monocentric model, 500 People around a central Firm):**
- Spatial equilibrium emerges endogenously: utility equalises across agents regardless of distance from centre, through trade-off between density cost and distance cost.
- **Hexagonal patterning** emerges as People minimise density costs.
- **Opposite effects of spatial vs. non-spatial costs**: increasing non-spatial costs (higher wages) causes agglomeration; increasing spatial costs causes dispersion.
- **Von Thunen-like sorting**: heterogeneous agents sort by wage/commute cost, producing emergent land-use rings with no landlord mechanism.
- **Love of variety spatial effect**: with two Firms, higher love of variety shifts population toward the higher-cost Firm (to minimise expensive-good delivery costs).
- **Equilibrium breakdown**: above a density cost threshold, equilibrium breaks down progressively from outskirts inward.

**Mobile Firms (Hotelling-style line model):**
- With high love of variety + low distance costs: Firms co-locate at centre.
- With high substitutability + high distance costs: Firms separate to opposite ends (Hotelling outcome).
- **DMR coordination problem**: even in the simplest setting, Firms struggle to interpret revenue signals when competitors' actions and demand noise confound them. Love of variety amplifies this problem.

### Key Findings
- Externalities are the equilibrating mechanism (not market failures) in this ABM context.
- Sequential decision-making is essential to equilibrium emergence.
- ABM and analytic methods are complementary, not competing.
- Spatial and non-spatial cost changes have **opposite** effects on settlement morphology.

---

## Chapter 6: The Transmission Belt Model

### Mechanism
1. **People** allocate their unit of time across Firms using CES utility optimisation.
2. **Firms** receive time as input into a smooth economies of scale production function (t^2 + t).
3. **Stock targeting**: Firms adjust prices based on stock level plus first and second derivatives (a damping mechanism solving oscillation problems). Stock > 0 --> lower price; stock < 0 --> raise price.
4. **Distance cost**: Price faced = base price + distance cost. Time spent on distance does not enter production.

### Key Results

**Production regime transitions:**
- With high love of variety (low rho): symmetric equilibrium -- all Firms produce equally.
- When rho exceeds ~0.75: symmetry breaks. A tiny price perturbation triggers a feedback loop -- cheaper Firm attracts more demand, gains efficiency via economies of scale, lowers price further, dominates. Verified in both the agent model and a spreadsheet differential equation.
- The transition boundary is mapped in (rho, distance cost) parameter space. Higher distance costs push back toward symmetric production.
- **Crucially, this transition can occur without distance** -- purely through economies of scale + love of variety interaction.

**Spatial outcomes (19-Firm, 19-Person line model):**
- Reducing distance cost triggers emergence of efficient producers. The number and location of efficient producers varies with parameters, creating different spatial morphologies.

**Welfare:**
- Transitions to efficient production never make any Person worse off -- efficiency gains are a positive externality benefiting everyone.

**Mobile People:**
- People relocate toward efficient producers, permanently locking in regional advantage ("black hole" outcome).

**Within-region heterogeneity:**
- With two Firms per region, four distinct production regimes emerge -- something the GE core model cannot produce.

**Markup and competition:**
- Firms can achieve stable profits by targeting stock > 0. But beyond a tipping point, they lose too much demand and collapse.
- The model achieves four of five "general" components (demand side, supply side, profit mechanism, price system) but **lacks emergent competition** -- the fifth component.

---

## Chapter 7: Discussion and Conclusions

### Contributions
1. A working transmission belt model linking supply and demand in an ABM spatial setting.
2. A detailed examination of GE from an ABM perspective, extracting concrete tools while revealing problems outside ABM's usual concerns.
3. Identification of two major obstacles: lack of dependency research in ABM, and the "year zero" mentality.
4. A framework for comparing interaction types in ABMs (density cost, strategy-free economies of scale, DMR feedback, stock targeting).
5. Demonstration that increasing returns dynamics can emerge from minimal assumptions (two Firms, one Person, no space).

### Limitations
- No competitive market structure; no firm entry/exit.
- Wages and goods subsumed into a single exchange.
- Simple time structure (no risk, no long-term horizons, Euclidean space only).
- DMR coordination problems persist; price volatility makes market signals difficult.
- Small agent numbers (max 500).
- "Currency entropy" problem avoided by workaround (time as currency).

### Future Work
1. Competition dynamics and firm entry/exit in spatial ABM.
2. Separating wage and goods demand.
3. Alternative utility approaches (hill-climbing with different production methods).
4. Comparing density cost outcomes with explicit land market models.
5. **Time**: modelling agents across different timescales, forward/backward production linkages.
6. **Production networks and input-output modelling**: extending the transmission belt toward production morphology changes.
7. **Infrastructure and route development**.
8. **Applied questions**: food system morphology and "relocalisation" under rising fuel prices.

### Overall Assessment
The thesis is a methodological and theoretical contribution rather than an applied one. It demonstrates that spatial economic agents can produce robust rational outcomes flexibly, and that careful attention to dependencies and assumptions -- rather than striving for descriptive realism -- reveals productive modelling avenues. The transmission belt model is proof-of-concept: a simple mechanism linking supply and demand with dynamic production equilibria using generic microeconomic ideas.

---

## Key Themes Across the Thesis

| Theme | Description |
|-------|-------------|
| **Dependencies** | Model design choices constrain and determine what is possible; these constraints carry real meaning |
| **Functional vs. descriptive mapping** | Code should serve analytical purpose, not mirror reality |
| **Complementarity of ABM and analytic methods** | Neither has unique explanatory power; each surfaces things the other misses |
| **Spatial vs. non-spatial cost polarity** | Spatial and non-spatial cost changes have opposite effects on settlement morphology |
| **Emergence requires explanation** | Generating a phenomenon is not the same as explaining it |
| **History matters** | Pre-computational modelling traditions contain essential insights ABM ignores at its peril |
| **Simplicity as strength** | The most productive models are often the simplest; complexity should be earned, not assumed |

---

*Digest generated from: DanOlnerThesisPrintDraft23_6_13.pdf (290 pages, University of Leeds, 2013)*
