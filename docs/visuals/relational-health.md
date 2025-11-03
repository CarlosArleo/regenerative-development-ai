
%%{init: {"theme": "base", "themeVariables": {
  "primaryColor": "transparent",
  "tertiaryColor": "transparent",
  "edgeLabelBackground":"transparent",
  "fontFamily": "Inter, Helvetica, Arial, sans-serif",
  "fontSize": "14px",
  "lineColor": "#000",
  "textColor": "#000"
}}}%%
flowchart TD
    Start(["`<b>`User Request`</b>`"]) --> Init["`<b>`Initialize Pipeline`</b><br/>`sessionId · logger · timestamp"]

    Init --> LoadConst["`<b>`Load Constitution v3.1`</b>`"]

    LoadConst --> RAG["`<b>`RAG:`</b>` Retrieve Context`<br/>`retrieveRelevantContext()"]

    RAG --> Phase1{{"`<b>`PHASE 1:`</b><br/>`Diagnostic Assessment"}}

    Phase1 --> RH["Assess Relational Health`<br/>`assessRelationalHealth()"]

    RH --> RHScore["`<b>`RH Score:`</b>` 0.0–1.0`<br/>`Structural Violations · Recommendations"]

    RHScore --> ModeDecision{"`<b>`Mode Selection Logic`</b>`"}

    %% Mode Selection Branches
    ModeDecision -->|"Force Synthesis`<br/>`(override flag)"| ForcedSynth["SYNTHESIS_WITH_WARNINGS"]
    ModeDecision -->|"Generate Both`<br/>`(research mode)"| BothModes["Generate BOTH:`<br/>`Diagnostic + Proposal"]
    ModeDecision -->|"RH ≥ 0.7`<br/>`(healthy)"| HealthySynth["SYNTHESIS MODE"]
    ModeDecision -->|"RH 0.4–0.7`<br/>`(messy)"| MessySynth["SYNTHESIS_WITH_WARNINGS"]
    ModeDecision -->|"RH < 0.4`<br/>`(compromised)"| Transform["TRANSFORMATION MODE"]

    %% Synthesis Path
    ForcedSynth --> SynthMode["runSynthesisMode()"]
    BothModes --> DiagMode["runTransformationMode()"]
    DiagMode --> SynthMode
    HealthySynth --> SynthMode
    MessySynth --> SynthMode

    SynthMode --> DialecticalLoop{{"Dialectical Loop`<br/>`Iterative Refinement"}}

    %% Transformation Path
    Transform --> DiagnosticLoop{{"Diagnostic Loop`<br/>`Single Pass"}}

    %% Dialectical Loop Detail
    DialecticalLoop --> Generate1["GENERATE:`<br/>`Initial Proposal"]
    Generate1 --> Iterate["Iteration Loop`<br/>`max 10 attempts"]
    Iterate --> Critique["CRITIQUE:`<br/>`Evaluate Against Constitution"]
    Critique --> Scores["Calculate Scores:`<br/>`principleScores · finalAlignmentScore"]
    Scores --> Converged{"Converged?`<br/>`Score ≥ 100%"}

    Converged -->|Yes| LoopComplete["Loop Complete"]
    Converged -->|"No · Max Iterations"| LoopComplete
    Converged -->|"No · Continue"| Correct["CORRECT:`<br/>`Refine Proposal"]
    Correct --> Iterate

    %% Diagnostic Loop Detail
    DiagnosticLoop --> DiagGen["GENERATE:`<br/>`Diagnostic Report"]
    DiagGen --> DiagComplete["Diagnostic Complete"]

    %% Convergence
    LoopComplete --> AddMeta["Add Metadata:`<br/>`mode · rhScore · warnings · diagnostic"]
    DiagComplete --> AddMeta

    AddMeta --> Valuation{"SYNTHESIS Mode?"}

    Valuation -->|Yes| GenQuestionnaire["Generate Valuation Questionnaire"]
    Valuation -->|No| FinalAnalysis["Generate Final Analysis Report"]

    GenQuestionnaire --> FinalAnalysis

    FinalAnalysis --> SaveSession["Save to Firestore`<br/>`Log Complete Session"]

    SaveSession --> End(["`<b>`Return Result `</b>`"])
