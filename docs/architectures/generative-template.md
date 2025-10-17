


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
    Title["`<b>`System Data Flow: What Actually Happens`</b><br/>`Follow the data through all four stages"]

    subgraph Stage1["`<b>`STAGE 1: Generate Inquiry Questions`</b>`"]
        S1Input["`<b>`YOU INPUT:`</b><br/>`• Project name`<br/>`• Place tensions list`<br/>`• Historical patterns list`<br/>`• Bioregion`<br/>`• Stakeholder types`<br/><br/>``<i>`Web Form - Takes 10-20 minutes`</i>`"]

    S1AI["`<b>`AI GENERATES:`</b><br/>``<br/><b>`Prompt Built:`</b><br/>`'You are regenerative practitioner for Carrington Moss...`<br/>`Tensions: green belt development, peatland destruction...`<br/>`Generate 15-20 questions per group elders, youth...'`<br/><br/>``<b>`Gemini Generates NEW Questions:`</b><br/>`Elders: 'What was harvested from moss when you were young?'`<br/>`Youth: 'What would make you want to stay here?'`<br/><br/>``<i>`Questions unique to YOUR place!`</i>`"]

    S1Output["`<b>`YOU RECEIVE:`</b><br/>`• 15-20 questions per`<br/>`  stakeholder group`<br/>`• Workshop protocol`<br/>`• Facilitation guidance`<br/><br/>``<i>`JSON Response`</i><br/>`Download/Print`<br/>`Ready for workshops"]
    end

    subgraph Stage2["`<b>`STAGE 2: Process Stakeholder Responses`</b>`"]
        S2Input["`<b>`YOU INPUT:`</b><br/>`• Workshop transcripts`<br/>`  paste or upload`<br/>`• Stakeholder quotes`<br/>`• Initial essence`<br/>`  hypothesis optional`<br/><br/>``<i>`Text Upload`</i><br/>`2-3 weeks after Stage 1"]

    S2AI["`<b>`AI SYNTHESIZES:`</b><br/>``<br/><b>`Analyzes YOUR Workshop Data:`</b><br/>`Assesses Essential Processes health for THIS community`<br/>`Identifies patterns in quotes: 'moss was commons', 'youth want to stay'`<br/>`Refines essence: 'peatland commons call community to stewardship'`<br/><br/>``<b>`Not Generic Assessment:`</b><br/>`Resource Generation: 15% youth have no land-based livelihood`<br/>`Identity/Belonging: 35% strong but disconnected from place`<br/><br/>``<i>`Scores reflect YOUR community's reality`</i>`"]

    S2Output["`<b>`YOU RECEIVE:`</b><br/>`• Essential Processes`<br/>`  scores 0-100%`<br/>`• Refined essence`<br/>`• Priority intervention`<br/>`• Confidence level`<br/><br/>``<i>`Detailed Report`</i><br/>`Validate with community"]
    end

    subgraph Stage3["`<b>`STAGE 3: Generate Design Brief`</b>`"]
        S3Input["`<b>`YOU INPUT:`</b><br/>`• Validated essence`<br/>`  from Stage 2`<br/>`• Proposed intervention`<br/>`• Stakeholder`<br/>`  commitments list`<br/><br/>``<i>`Structured Form`</i><br/>`After community validation"]

    S3AI["`<b>`AI CREATES:`</b><br/>``<br/><b>`Derives Principles from YOUR Essence:`</b><br/>`'Honor Moss as Teacher' ← derived from elder quotes + youth aspirations`<br/>`'Create Pathways Wisdom→Action' ← connects commitments to design`<br/><br/>``<b>`Three Spheres for YOUR Context:`</b><br/>`Economic: Youth restoration jobs + ecotourism not generic 'jobs'`<br/>`Social: Elder-youth mentorship specific to your commitments`<br/>`Ecological: Peatland rewetting strategies place-specific`<br/><br/>``<i>`Every element traceable to your inputs!`</i>`"]

    S3Output["`<b>`YOU RECEIVE:`</b><br/>`• 4-6 design principles`<br/>`• Three Spheres analysis`<br/>`• Nested scales view`<br/>`• Success metrics`<br/>`• Workshop protocol`<br/><br/>``<i>`Design Brief`</i><br/>`For design team"]
    end

    subgraph Stage4["`<b>`STAGE 4: Governance Harmonization VDK`</b>`"]
        S4Input["`<b>`YOU INPUT:`</b><br/>`• Design brief`<br/>`  auto-imported`<br/>`• Policy PDFs`<br/>`  upload multiple`<br/>`• Constitution choice`<br/>`  regenerative default`<br/><br/>``<i>`File Upload`</i><br/>`5-10 min processing`<br/>`VDK runs iterations"]

    S4AI["`<b>`VDK ITERATES:`</b><br/>``<br/><b>`For Each of 3 Pathways:`</b><br/>`1. Generate governance model e.g., 'CLT', 'Coop+Council', 'Community Benefit Society'`<br/>`2. Critique against design brief + policy docs + constitution`<br/>`3. VDK Check: Does language shift toward extraction?`<br/><br/>``<b>`⚠️ VDK DETECTS:`</b><br/>`'NGO Partnership' → 'Advisory board' = power shift → REJECT`<br/>`System reverts, tries 'Community Land Trust' instead`<br/>`✓ 'Community owns, decides, controls' → COHERENT → Accept`<br/><br/>`4. Correct based on critique → Repeat up to 5x per pathway`<br/>`5. Generate 3 different constitutionally-valid pathways`<br/><br/>``<i>`Each pathway tested against YOUR policy context!`</i>`"]

    S4Output["`<b>`YOU RECEIVE:`</b><br/>`• 3+ governance options`<br/>`• Each with:`<br/>`  - Legal structure`<br/>`  - Pros/cons`<br/>`  - Capture risk`<br/>`  - Viability score`<br/>`  - Implementation steps`<br/>`• Rejected pathways`<br/>`  with VDK reasoning`<br/><br/>``<i>`Governance Portfolio`</i><br/>`Community chooses"]
    end

    Key["`<b>`KEY:`</b>` Nothing is template-based. AI generates contextually-appropriate outputs`<br/>`using regenerative frameworks as a lens."]

    Title --> Stage1
    S1Input --> S1AI
    S1AI --> S1Output
    S1Output --> Stage2

    S2Input --> S2AI
    S2AI --> S2Output
    S2Output --> Stage3

    S3Input --> S3AI
    S3AI --> S3Output
    S3Output --> Stage4

    S4Input --> S4AI
    S4AI --> S4Output
    S4Output --> Key

    style Title stroke:#000,stroke-width:3px,fill:transparent,color:#000
    style S1Input stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S1AI stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S1Output stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S2Input stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S2AI stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S2Output stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S3Input stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S3AI stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S3Output stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S4Input stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S4AI stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style S4Output stroke:#000,stroke-width:2px,fill:transparent,color:#000
    style Key stroke:#000,stroke-width:3px,fill:transparent,color:#000
