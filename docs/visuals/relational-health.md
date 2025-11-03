
flowchart TD
    Start([User Request]) --> Init[Initialize Pipeline\nsessionId · logger · timestamp]

    Init --> LoadConst[Load Constitution v3.1]

    LoadConst --> RAG[RAG: Retrieve Context\nretrieveRelevantContext()]

    RAG --> Phase1{{PHASE 1:\nDiagnostic Assessment}}

    Phase1 --> RH[Assess Relational Health\nassessRelationalHealth()]

    RH --> RHScore[RH Score: 0.0–1.0\nStructural Violations · Recommendations]

    RHScore --> ModeDecision{"Mode Selection Logic"}

    %% Mode Selection Branches
    ModeDecision -->|Force Synthesis\n(override flag)| ForcedSynth[SYNTHESIS_WITH_WARNINGS]
    ModeDecision -->|Generate Both\n(research mode)| BothModes[Generate BOTH:\nDiagnostic + Proposal]
    ModeDecision -->|RH ≥ 0.7\n(healthy)| HealthySynth[SYNTHESIS MODE]
    ModeDecision -->|RH 0.4–0.7\n(messy)| MessySynth[SYNTHESIS_WITH_WARNINGS]
    ModeDecision -->|RH < 0.4\n(compromised)| Transform[TRANSFORMATION MODE]

    %% Synthesis Path
    ForcedSynth --> SynthMode[runSynthesisMode()]
    BothModes --> DiagMode[runTransformationMode()]
    DiagMode --> SynthMode
    HealthySynth --> SynthMode
    MessySynth --> SynthMode

    SynthMode --> DialecticalLoop{{Dialectical Loop\n(Iterative Refinement)}}

    %% Transformation Path
    Transform --> DiagnosticLoop{{Diagnostic Loop\n(Single Pass)}}

    %% Dialectical Loop Detail
    DialecticalLoop --> Generate1[GENERATE: Initial Proposal]
    Generate1 --> Iterate[Iteration Loop\n(max 10 attempts)]
    Iterate --> Critique[CRITIQUE: Evaluate\nAgainst Constitution]
    Critique --> Scores[Calculate Scores:\nprincipleScores · finalAlignmentScore]
    Scores --> Converged{"Converged?\nScore ≥ 100%"}

    Converged -->|Yes| LoopComplete[Loop Complete]
    Converged -->|"No · Max Iterations"| LoopComplete
    Converged -->|"No · Continue"| Correct[CORRECT: Refine Proposal]
    Correct --> Iterate

    %% Diagnostic Loop Detail
    DiagnosticLoop --> DiagGen[GENERATE: Diagnostic Report]
    DiagGen --> DiagComplete[Diagnostic Complete]

    %% Convergence
    LoopComplete --> AddMeta[Add Metadata:\nmode · rhScore · warnings · diagnostic]
    DiagComplete --> AddMeta

    AddMeta --> Valuation{"SYNTHESIS Mode?"}

    Valuation -->|Yes| GenQuestionnaire[Generate Valuation Questionnaire]
    Valuation -->|No| FinalAnalysis

    GenQuestionnaire --> FinalAnalysis[Generate Final Analysis Report]

    FinalAnalysis --> SaveSession[Save to Firestore\nLog Complete Session]

    SaveSession --> End([Return Result])
