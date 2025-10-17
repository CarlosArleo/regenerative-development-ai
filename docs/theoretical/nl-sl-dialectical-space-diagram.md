%%{init: {"theme": "base", "themeVariables": {
  "primaryColor": "transparent",
  "tertiaryColor": "transparent",
  "edgeLabelBackground":"transparent",
  "fontFamily": "Inter, Helvetica, Arial, sans-serif",
  "fontSize": "15px",
  "lineColor": "#000",
  "textColor": "#000"
}}}%%
graph TB
    Title["`<b>`The Dialectical Constraint Space`</b><br/>`Constitutional Viability = P ∈ (NL ∩ SL)"]

    Intro["`<b>`KEY INSIGHT:`</b><br/>`Most governance systems fail by optimizing ONE constraint`<br/>`while ignoring the other.`<br/>`Constitutional AI enforces BOTH simultaneously."]

    NL["`<b>`NATURAL LAW (NL)`</b><br/>`Physical Necessity`<br/><br/>`• Thermodynamics`<br/>`• Ecology`<br/>`• Biology`<br/>`• Physical Impossibility"]

    SL["`<b>`SOCIAL LAW (SL)`</b><br/>`Ethical Obligation`<br/><br/>`• Justice & Equity`<br/>`• Legitimacy`<br/>`• Ethics`<br/>`• Ethical Unacceptability"]

    Viable["`<b>`✓ VIABLE SPACE`</b><br/>`P ∈ (NL ∩ SL)`<br/><br/>`Constitutionally Valid Solutions`<br/>`• Community land trusts`<br/>`• Regenerative design`<br/>`• With equity mandates`<br/>`• System resilience through`<br/>`dual coherence"]

    FailNL["`<b>`⚠ FAILURE 1:`</b><br/>`NL Only - Technocratic Efficiency`<br/><br/>`Physically viable but unjust`<br/>`• Smart cities with surveillance`<br/>`• Profit-driven infrastructure`<br/>`• Industrial monoculture`<br/>`• Result: Social alienation`<br/>`→ Political instability"]

    FailSL["`<b>`⚠ FAILURE 2:`</b><br/>`SL Only - Aspirational Idealism`<br/><br/>`Ethically sound but non-viable`<br/>`• Utopian communes ignoring capacity`<br/>`• Post-growth without transition`<br/>`• Processes that can't scale`<br/>`• Result: Entropic decay`<br/>`→ Resource depletion"]

    FailBoth["`<b>`⚠ FAILURE 3:`</b><br/>`Neither - Extractive Chaos`<br/><br/>`Ignores both constraints`<br/>`• Unconstrained extraction`<br/>`• Authoritarian petrostates`<br/>`• Colonial economies`<br/>`• Result: Rapid collapse"]

    Title --> Intro
    Intro --> NL
    Intro --> SL
    Intro --> Viable
    NL --> FailNL
    NL --> Viable
    SL --> FailSL
    SL --> Viable
    FailNL --> FailBoth
    FailSL --> FailBoth

    style Title stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style Intro stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style NL stroke:#000,stroke-width:1px,fill:transparent,color:#000
    style SL stroke:#000,stroke-width:1px,fill:transparent,color:#000
    style Viable stroke:#000,stroke-width:3px,fill:transparent,color:#000
    style FailNL stroke:#000,stroke-width:1px,fill:transparent,color:#000
    style FailSL stroke:#000,stroke-width:1px,fill:transparent,color:#000
    style FailBoth stroke:#000,stroke-width:2px,fill:transparent,color:#000
