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
    Title["`<b>`The Epistemic Innovation Space`</b><br/>`Where Three Frameworks Intersect"]

    Regen["`<b>`REGENERATIVE`<br/>`DEVELOPMENT`</b><br/>``<br/>`• Story of Place`<br/>`• Essential Processes`<br/>`• Three Spheres`<br/>`• Nested Scales`<br/>`• Systems Ecology`<br/>`• Place-based Design`<br/>`• Bioregional Thinking"]

    Critical["`<b>`CRITICAL`<br/>`URBAN THEORY`</b><br/>``<br/>`• Spatial Justice`<br/>`• Right to the City`<br/>`• Metabolic Rift`<br/>`• Abstract vs Lived Space`<br/>`• Gentrification Analysis`<br/>`• State Rescaling`<br/>`• Anti-Extraction"]

    AI["`<b>`CONSTITUTIONAL`<br/>`AI`</b><br/>``<br/>`• Value Alignment`<br/>`• Constitutional Constraints`<br/>`• Dialectical Iteration`<br/>`• Verification Mechanisms`<br/>`• Bounded Exploration`<br/>`• Pattern Detection"]

    RegCrit["`<b>`Regenerative Justice`</b><br/>`Healing land requires`<br/>`healing social relations"]

    CritAI["`<b>`Capture Detection`</b><br/>`AI identifies extractive`<br/>`patterns in real-time"]

    RegenAI["`<b>`Ecological AI`</b><br/>`Algorithms grounded in`<br/>`living systems principles"]

    Center["`<b>`THE INNOVATION:`</b><br/>``<br/><b>`Governance as`<br/>`Living Process`</b><br/>``<br/>`Constitutional constraints that`<br/>`enforce ecological coherence`<br/>`AND spatial justice`<br/>`simultaneously"]

    Questions["`<b>`Core Questions:`</b><br/>`Regen: What makes systems alive?`<br/>`Critical: Who benefits? Who's harmed?`<br/>`AI: How to verify alignment?"]

    Title --> Regen
    Title --> Critical
    Title --> AI
    Regen --> RegCrit
    Critical --> RegCrit
    Critical --> CritAI
    AI --> CritAI
    Regen --> RegenAI
    AI --> RegenAI
    RegCrit --> Center
    CritAI --> Center
    RegenAI --> Center
    Center --> Questions

    style Title stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style Regen stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style Critical stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style AI stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style RegCrit stroke:#000,stroke-width:1px,fill:transparent,color:#000
    style CritAI stroke:#000,stroke-width:1px,fill:transparent,color:#000
    style RegenAI stroke:#000,stroke-width:1px,fill:transparent,color:#000
    style Center stroke:#000,stroke-width:3px,fill:transparent,color:#000
    style Questions stroke:#000,stroke-width:2px,fill:transparent,color:#000
