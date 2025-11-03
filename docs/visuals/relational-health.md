
%%{init: {"theme": "base", "themeVariables": {
  "primaryColor": "transparent",
  "tertiaryColor": "transparent",
  "edgeLabelBackground": "transparent",
  "fontFamily": "Inter, Helvetica, Arial, sans-serif",
  "fontSize": "15px",
  "lineColor": "#000",
  "textColor": "#000"
}}}%%
graph TD
    Start([`<b>`User Request`</b>`]) --> Init["`<b>`Initialize Pipeline`</b><br/>`sessionId · logger · timestamp"]

    Init --> LoadConst["`<b>`Load Constitution v3.1`</b>`"]

    LoadConst --> RAG["`<b>`RAG:`</b>` Retrieve Context`<br/><i>`retrieveRelevantContext()`</i>`"]

    RAG --> Phase1{{"`<b>`PHASE 1`</b><br/>`Diagnostic Assessment"}}

    Phase1 --> RH["Assess Relational Health`<br/><i>`assessRelationalHealth()`</i>`"]

    RH --> RHScore["`<b>`RH Score:`</b>` 0.0–1.0`<br/>`Structural Violations · Recommendations"]

    RHScore --> ModeDecision{"`<b>`Mode Selection Logic`</b>`"}

    %% Mode Selection Branches
    ModeDecision -- "Force Synthesis`<br/>`(override flag)" --> ForcedSynth["`<b>`SYNTHESIS_WITH_WARNINGS`</b>`"]
    ModeDecision -- "Generate Both`<br/>`(research mode)" --> BothModes["`<b>`Generate BOTH`</b><br/>`Diagnostic + Proposal"]
    ModeDecision -- "RH ≥ 0.7`<br/>`(healthy)" --> HealthySynth["`<b>`SYNTHESIS MODE`</b>`"]
    ModeDecision -- "RH 0.4–0.7`<br/>`(messy)" --> MessySynth["`<b>`SYNTHESIS_WITH_WARNINGS`</b>`"]
    ModeDecision -- "RH < 0.4`<br/>`(compromised)" --> Transform["`<b>`TRANSFORMATION MODE`</b>`"]

    %% Synthesis Path
    ForcedSynth --> SynthMode["runSynthesisMode()"]
    BothModes --> DiagMode["runTransformationMode()"]
    DiagMode --> SynthMode
    HealthySynth --> SynthMode
    MessySynth --> SynthMode

    SynthMode --> DialecticalLoop{{"`<b>`Dialectical Loop`</b><br/>`(Iterative Refinement)"}}

    %% Transformation Path
    Transform --> DiagnosticLoop{{"`<b>`Diagnostic Loop`</b><br/>`(Single Pass)"}}

    %% Dialectical Loop Detail
    DialecticalLoop --> Generate1["`<b>`GENERATE:`</b>` Initial Proposal"]
    Generate1 --> Iterate["Iteration Loop`<br/>`(max 10 attempts)"]
    Iterate --> Critique["`<b>`CRITIQUE:`</b>` Evaluate`<br/>`Against Constitution"]
    Critique --> Scores["`<b>`Calculate Scores:`</b><br/>`principleScores · finalAlignmentScore"]
    Scores --> Converged{"`<b>`Converged?`</b><br/>`Score ≥ 100%"}

    Converged -- Yes --> LoopComplete["Loop Complete"]
    Converged -- "No · Max Iterations" --> LoopComplete
    Converged -- "No · Continue" --> Correct["`<b>`CORRECT:`</b>` Refine Proposal"]
    Correct --> Iterate

    %% Diagnostic Loop Detail
    DiagnosticLoop --> DiagGen["`<b>`GENERATE:`</b>` Diagnostic Report"]
    DiagGen --> DiagComplete["Diagnostic Complete"]

    %% Convergence
    LoopComplete --> AddMeta["`<b>`Add Metadata:`</b><br/>`mode · rhScore · warnings · diagnostic"]
    DiagComplete --> AddMeta

    AddMeta --> Valuation{"`<b>`SYNTHESIS Mode?`</b>`"}

    Valuation -- Yes --> GenQuestionnaire["Generate Valuation Questionnaire"]
    Valuation -- No --> FinalAnalysis

    GenQuestionnaire --> FinalAnalysis["Generate Final Analysis Report"]

    FinalAnalysis --> SaveSession["Save to Firestore`<br/>`Log Complete Session"]

    SaveSession --> End([`<b>`Return Result`</b>`])

    %% Styling
    style Start stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style End stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style Phase1 stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style DialecticalLoop stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style DiagnosticLoop stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style ModeDecision stroke:#000,stroke-dasharray:4 3,fill:transparent,color:#000
    style Converged stroke:#000,stroke-dasharray:4 3,fill:transparent,color:#000
    style Valuation stroke:#000,stroke-dasharray:4 3,fill:transparent,color:#000
