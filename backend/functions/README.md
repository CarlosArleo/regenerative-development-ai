## backend/functions/README.md

<artifact identifier="backend-functions-readme" type="text/markdown" title="backend/functions/README.md">
# Firebase Functions - Detailed Documentation

Implementation details for all Cloud Functions.

---

## Function Index

<pre class="font-ui border-border-100/50 overflow-x-scroll w-full rounded border-[0.5px] shadow-[0_2px_12px_hsl(var(--always-black)/5%)]"><table class="bg-bg-100 min-w-full border-separate border-spacing-0 text-sm leading-[1.88888] whitespace-normal"><thead class="border-b-border-100/50 border-b-[0.5px] text-left"><tr class="[tbody>&]:odd:bg-bg-500/10"><th class="text-text-000 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] px-2 [&:not(:first-child)]:border-l-[0.5px]">Function</th><th class="text-text-000 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] px-2 [&:not(:first-child)]:border-l-[0.5px]">Stage</th><th class="text-text-000 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] px-2 [&:not(:first-child)]:border-l-[0.5px]">Timeout</th><th class="text-text-000 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] px-2 [&:not(:first-child)]:border-l-[0.5px]">Memory</th><th class="text-text-000 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] px-2 [&:not(:first-child)]:border-l-[0.5px]">Description</th></tr></thead><tbody><tr class="[tbody>&]:odd:bg-bg-500/10"><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]"><code class="bg-text-200/5 border border-0.5 border-border-300 text-danger-000 whitespace-pre-wrap rounded-[0.4rem] px-1 py-px text-[0.9rem]">generateInquiryQuestions</code></td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">1</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">120s</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">512MB</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">Generate Story of Place questions</td></tr><tr class="[tbody>&]:odd:bg-bg-500/10"><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]"><code class="bg-text-200/5 border border-0.5 border-border-300 text-danger-000 whitespace-pre-wrap rounded-[0.4rem] px-1 py-px text-[0.9rem]">processStakeholderResponses</code></td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">2</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">180s</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">1GB</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">Synthesize and assess Essential Processes</td></tr><tr class="[tbody>&]:odd:bg-bg-500/10"><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]"><code class="bg-text-200/5 border border-0.5 border-border-300 text-danger-000 whitespace-pre-wrap rounded-[0.4rem] px-1 py-px text-[0.9rem]">generateDesignBrief</code></td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">3</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">180s</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">1GB</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">Create Three Spheres design brief</td></tr><tr class="[tbody>&]:odd:bg-bg-500/10"><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]"><code class="bg-text-200/5 border border-0.5 border-border-300 text-danger-000 whitespace-pre-wrap rounded-[0.4rem] px-1 py-px text-[0.9rem]">harmonizeGovernance</code></td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">4</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">540s</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">2GB</td><td class="border-t-border-100/50 [&:not(:first-child)]:-x-[hsla(var(--border-100) / 0.5)] border-t-[0.5px] px-2 [&:not(:first-child)]:border-l-[0.5px]">VDK-enhanced governance pathways</td></tr></tbody></table></pre>

---

## Function 1: generateInquiryQuestions

### Purpose

Generate culturally-appropriate inquiry questions for Story of Place workshops based on regenerative development frameworks.

### Implementation

typescript

```typescript
// src/index.ts

exportconst generateInquiryQuestions = functions
.runWith({
    memory:'512MB',
    timeoutSeconds:120,
})
.https.onRequest(async(req, res)=>{
  
// CORS
    res.set('Access-Control-Allow-Origin','*');
if(req.method==='OPTIONS'){
      res.set('Access-Control-Allow-Methods','POST');
      res.set('Access-Control-Allow-Headers','Content-Type');
      res.status(204).send('');
return;
}
  
try{
// Validate input
const input =Stage1InputSchema.parse(req.body);
    
// Call AI flow
const result =awaitstoryOfPlaceInquiryFlow(input);
    
// Return result
      res.json(result);
    
}catch(error){
console.error('Stage 1 error:', error);
      res.status(400).json({ error: error.message});
}
});
```

### AI Flow

typescript

```typescript
// src/ai/flows/storyOfPlaceInquiryFlow.ts

exportasyncfunctionstoryOfPlaceInquiryFlow(
  input:Stage1Input
):Promise<Stage1Output>{
  
const{ project_name, place_context, stakeholder_types }= input;
  
// Build context-rich prompt
const prompt =`
You are an expert regenerative development practitioner facilitating Story of Place inquiry.

Project: ${project_name}
Location: ${place_context.location_name}
Bioregion: ${place_context.bioregion}

Current Tensions:
${place_context.current_tensions.map(t =>`- ${t}`).join('\n')}

Historical Patterns:
${place_context.historical_patterns.map(p =>`- ${p}`).join('\n')}

Task: Generate 15-20 deep, open-ended inquiry questions for each stakeholder group.

Stakeholder groups: ${stakeholder_types.join(', ')}

Guidelines:
1. Questions should reveal place essence, not extract data
2. Use Story of Place framework: Potential, Aspirations, Relationships, Patterns
3. Honor cultural context and local language
4. Avoid extractive or colonial framing
5. Include questions for both human and non-human stakeholders
6. Questions should be conversational, not academic

Output as JSON:
{
  "questions": {
    "stakeholder_type": ["question1", "question2", ...],
    ...
  },
  "workshop_protocol": "Suggested workshop structure and facilitation guidance"
}
`;

// Call Gemini
const response =awaitcallGeminiAPI(prompt);
  
// Parse JSON response
const parsed =JSON.parse(response);
  
// Validate output structure
const validated =Stage1OutputSchema.parse(parsed);
  
return validated;
}
```

### Input Schema

typescript

```typescript
constStage1InputSchema= z.object({
  project_name: z.string().min(1).max(200),
  place_context: z.object({
    location_name: z.string().min(1).max(200),
    current_tensions: z.array(z.string()).min(1).max(20),
    historical_patterns: z.array(z.string()).min(1).max(20),
    bioregion: z.string().min(1).max(200)
}),
  stakeholder_types: z.array(z.string()).min(1).max(10)
});
```

### Output Schema

typescript

```typescript
constStage1OutputSchema= z.object({
  questions: z.record(z.array(z.string())),
  workshop_protocol: z.string(),
  metadata: z.object({
    model_used: z.string(),
    processing_time_ms: z.number(),
    timestamp: z.string()
})
});
```

---

## Function 2: processStakeholderResponses

### Purpose

Synthesize workshop responses, assess Essential Processes health, refine place essence.

### Implementation

typescript

```typescript
exportconst processStakeholderResponses = functions
.runWith({
    memory:'1GB',
    timeoutSeconds:180,
})
.https.onRequest(async(req, res)=>{
// Similar CORS + error handling
  
const input =Stage2InputSchema.parse(req.body);
const result =awaitessentialProcessesAssessmentFlow(input);
    res.json(result);
});
```

### AI Flow

typescript

```typescript
// src/ai/flows/essentialProcessesAssessmentFlow.ts

exportasyncfunctionessentialProcessesAssessmentFlow(
  input:Stage2Input
):Promise<Stage2Output>{
  
const{ project_name, stakeholder_responses, essence_hypothesis }= input;
  
// Build comprehensive synthesis prompt
const prompt =`
You are assessing the health of essential living processes in ${project_name}.

Stakeholder Responses:
${Object.entries(stakeholder_responses).map(([group, responses])=>`
${group}:
${responses.map(r =>`- "${r}"`).join('\n')}
`).join('\n')}

Initial Place Essence Hypothesis: "${essence_hypothesis}"

Task: Assess health of 8 Essential Processes using responses:
1. Nourishment (energy, material flows)
2. Shelter (habitat, protection)
3. Resource Generation/Exchange (economic, material flows)
4. Identity/Belonging (social bonds, sense of place)
5. Meaningful Participation (agency, contribution)
6. Spirit/Inspiration (meaning, beauty, aspiration)
7. Learning & Development (growth, adaptation)
8. Whole-System Processes (integration, emergence)

For each process, assess health across three spheres:
- Ecological: 0-100%
- Economic: 0-100%
- Social: 0-100%
- Overall: average of three

Identify:
- Priority process (most degraded)
- Leverage points (highest-impact interventions)
- Refined place essence (based on all responses)

Confidence assessment:
- High: Rich data, clear patterns, strong essence
- Medium: Adequate data, some patterns, essence emerging
- Low: Sparse data, unclear patterns, need more inquiry

Output as JSON with detailed reasoning.
`;

const response =awaitcallGeminiAPI(prompt);
const parsed =JSON.parse(response);
const validated =Stage2OutputSchema.parse(parsed);
  
return validated;
}
```

---

## Function 3: generateDesignBrief

### Purpose

Translate place intelligence into actionable design guidance using Three Spheres and Nested Scales frameworks.

### Implementation

typescript

```typescript
exportconst generateDesignBrief = functions
.runWith({
    memory:'1GB',
    timeoutSeconds:180,
})
.https.onRequest(async(req, res)=>{
const input =Stage3InputSchema.parse(req.body);
const result =awaitthreeSpheresSynthesisFlow(input);
    res.json(result);
});
```

### AI Flow

typescript

```typescript
// src/ai/flows/threeSpheresSynthesisFlow.ts

exportasyncfunctionthreeSpheresSynthesisFlow(
  input:Stage3Input
):Promise<Stage3Output>{
  
const{ 
    validated_essence, 
    proposed_intervention,
    stakeholder_commitments,
    essential_processes 
}= input;
  
const prompt =`
You are creating a regenerative design brief.

Place Essence: "${validated_essence}"
Proposed Intervention: "${proposed_intervention}"

Essential Processes Assessment:
${JSON.stringify(essential_processes,null,2)}

Stakeholder Commitments:
${stakeholder_commitments.map(c => 
`- ${c.stakeholder}: ${c.commitment} (capacity: ${c.capacity})`
).join('\n')}

Task: Create comprehensive design brief with:

1. Core Design Principles (derived from essence)
   - Each principle should be actionable
   - Traceable back to place essence
   - Guide physical and social design

2. Three Spheres Synthesis
   - Economic opportunities and risks
   - Social opportunities and risks
   - Ecological opportunities and risks
   - Sweet spots where all three align

3. Nested Scales Visualization
   - Site scale (direct intervention)
   - Watershed/neighborhood scale
   - Bioregion scale
   - Human settlement scale

4. Success Metrics
   - Ecological indicators
   - Social indicators
   - Economic indicators
   - Process health tracking

5. Design Phase Workshop Protocol
   - Co-design activities
   - Community engagement approach
   - Integration with design team

Output as structured JSON.
`;

const response =awaitcallGeminiAPI(prompt);
const parsed =JSON.parse(response);
const validated =Stage3OutputSchema.parse(parsed);
  
return validated;
}
```

---

## Function 4: harmonizeGovernance

### Purpose

Generate and test multiple governance pathways using VDK to detect extractive drift.

### Implementation

typescript

```typescript
exportconst harmonizeGovernance = functions
.runWith({
    memory:'2GB',
    timeoutSeconds:540,// 9 minutes (max for 2nd gen)
})
.https.onRequest(async(req, res)=>{
  
// Handle multipart/form-data (file uploads)
const busboy =Busboy({ headers: req.headers});
  
let fields:any={};
let files:Buffer[]=[];
  
    busboy.on('field',(fieldname, val)=>{
      fields[fieldname]= val;
});
  
    busboy.on('file',async(fieldname, file, filename)=>{
const chunks:Buffer[]=[];
      file.on('data', chunk => chunks.push(chunk));
      file.on('end',()=>{
        files.push(Buffer.concat(chunks));
});
});
  
    busboy.on('finish',async()=>{
try{
// Parse uploaded documents
const documents =awaitPromise.all(
          files.map(parsePDF)
);
      
// Run governance harmonization
const result =awaitgovernanceHarmonizationFlow({
...fields,
          policy_documents: documents
});
      
        res.json(result);
      
}catch(error){
console.error('Stage 4 error:', error);
        res.status(500).json({ error: error.message});
}
});
  
    busboy.end(req.rawBody);
});
```

### AI Flow with VDK

typescript

```typescript
// src/ai/flows/governanceHarmonizationFlow.ts

exportasyncfunctiongovernanceHarmonizationFlow(
  input:Stage4Input
):Promise<Stage4Output>{
  
const{ 
    design_brief, 
    policy_documents, 
    constitution,
    analysis_focus 
}= input;
  
// Load constitution
const constitutionText =awaitloadConstitution(constitution);
  
// Generate 3 pathways
const pathways:GovernancePathway[]=[];
const rejectedPathways:RejectedPathway[]=[];
  
for(let i =0; i <3; i++){
try{
const pathway =awaitgenerateAndRefinePathway(
        design_brief,
        policy_documents,
        constitutionText,
        pathways // Avoid duplicating previous pathways
);
    
      pathways.push(pathway);
    
}catch(error){
if(error.type==='EXTRACTIVE_DRIFT'){
        rejectedPathways.push({
          attempt: i +1,
          rejection_reason: error.message,
          vdk_analysis: error.vdkAnalysis
});
}
}
}
  
return{
    pathways,
    rejected_pathways: rejectedPathways,
    metadata:{
      constitution_used: constitution,
      documents_analyzed: policy_documents.length,
      processing_time_ms:Date.now()- startTime
}
};
}

asyncfunctiongenerateAndRefinePathway(
  designBrief:any,
  policyDocs:string[],
  constitution:string,
  existingPathways:GovernancePathway[]
):Promise<GovernancePathway>{
  
let iteration =awaitgenerateInitialGovernanceProtocol(
    designBrief,
    policyDocs,
    existingPathways
);
  
const iterationHistory:IterationRecord[]=[];
  
// Iterative refinement (max 5 iterations)
for(let i =0; i <5; i++){
// Critique current iteration
const critique =awaitcritiqueGovernance(
      iteration,
      designBrief,
      policyDocs,
      constitution
);
  
// VDK Coherence Check
const coherence =awaitvdkCoherenceCheck(
      iteration,
      i >0? iterationHistory[i-1].iteration:null,
      constitution,
      critique
);
  
    iterationHistory.push({
      iteration_number: i +1,
      iteration,
      critique,
      coherence,
      score: coherence.score
});
  
// Check for extractive drift
if(coherence.trajectory==='EXTRACTIVE_DRIFT'){
throw{
        type:'EXTRACTIVE_DRIFT',
        message: coherence.concerns.join('; '),
        vdkAnalysis: coherence
};
}
  
// If coherent and score high enough, we're done
if(coherence.trajectory==='COHERENT'&& coherence.score>0.85){
break;
}
  
// Otherwise, correct and continue
    iteration =awaitcorrectGovernance(iteration, critique);
}
  
// Format final pathway
returnformatGovernancePathway(iteration, iterationHistory);
}
```

### VDK Implementation

typescript

```typescript
// src/ai/vdk/coherenceCheck.ts

exportasyncfunctionvdkCoherenceCheck(
  currentIteration:GovernanceIteration,
  previousIteration:GovernanceIteration|null,
  constitution:string,
  critique:CritiqueResult
):Promise<CoherenceResult>{
  
// If first iteration, establish baseline
if(!previousIteration){
return{
      trajectory:'COHERENT',
      score:0.65,
      concerns:[],
      reasoning:'Baseline iteration'
};
}
  
// Language shift analysis
const languageAnalysis =analyzeLanguageShift(
    previousIteration.text,
    currentIteration.text
);
  
// Power dynamics check
const powerAnalysis =analyzePowerDynamics(currentIteration);
  
// Constitutional alignment
const alignmentScore =checkConstitutionalAlignment(
    currentIteration,
    constitution
);
  
// Pattern matching against known failures
const failurePatterns =matchKnownFailurePatterns(currentIteration);
  
// Self-justifying language detection
const selfJustifying =detectSelfJustifyingLanguage(
    currentIteration,
    previousIteration
);
  
// Compute overall coherence
const concerns:string[]=[];
let score = alignmentScore;
  
// Deduct for problematic patterns
if(languageAnalysis.extractiveShift){
    score -=0.15;
    concerns.push(`Language shifted toward extractive: ${languageAnalysis.examples}`);
}
  
if(powerAnalysis.externalControl){
    score -=0.20;
    concerns.push(`Power shifted to external entity: ${powerAnalysis.details}`);
}
  
if(failurePatterns.length>0){
    score -=0.25;
    concerns.push(`Matches known failure patterns: ${failurePatterns.map(p => p.name).join(', ')}`);
}
  
if(selfJustifying.detected){
    score -=0.20;
    concerns.push(`Self-justifying language detected: ${selfJustifying.examples}`);
}
  
// Determine trajectory
let trajectory:'COHERENT'|'EXTRACTIVE_DRIFT'|'UNCERTAIN';
  
if(failurePatterns.length>0|| selfJustifying.detected|| score <0.6){
    trajectory ='EXTRACTIVE_DRIFT';
}elseif(score >0.75&& concerns.length===0){
    trajectory ='COHERENT';
}else{
    trajectory ='UNCERTAIN';
}
  
return{
    trajectory,
    score,
    concerns,
    reasoning:generateReasoningExplanation({
      languageAnalysis,
      powerAnalysis,
      alignmentScore,
      failurePatterns,
      selfJustifying
})
};
}
```

---

## Shared Utilities

### Gemini API Client

typescript

```typescript
// src/utils/geminiClient.ts

import{GoogleGenerativeAI}from'@google/generative-ai';

const genAI =newGoogleGenerativeAI(process.env.GEMINI_API_KEY!);

exportasyncfunctioncallGeminiAPI(
  prompt:string,
  model:'pro'|'flash'='pro'
):Promise<string>{
  
const modelName = model ==='pro' 
?'gemini-2.5-pro-latest'
:'gemini-2.5-flash-latest';
  
const generativeModel = genAI.getGenerativeModel({ 
    model: modelName 
});
  
const result =await generativeModel.generateContent(prompt);
const response =await result.response;
  
return response.text();
}
```

### Retry Logic

typescript

```typescript
exportasyncfunctionwithRetry<T>(
fn:()=>Promise<T>,
  maxRetries:number=3
):Promise<T>{
  
for(let i =0; i < maxRetries; i++){
try{
returnawaitfn();
}catch(error){
if(i === maxRetries -1)throw error;
    
// Exponential backoff
const delay =Math.pow(2, i)*1000;
awaitsleep(delay);
    
console.log(`Retry ${i +1}/${maxRetries} after ${delay}ms`);
}
}
  
thrownewError('Should not reach here');
}
```

---

## Testing Functions Locally

### Unit Tests

bash

```bash
cd functions
npmtest
```

typescript

```typescript
// test/storyOfPlaceInquiry.test.ts

import{ storyOfPlaceInquiryFlow }from'../src/ai/flows/storyOfPlaceInquiryFlow';

describe('Story of Place Inquiry Flow',()=>{
  
it('generates questions for all stakeholder types',async()=>{
const input ={
      project_name:'Test Project',
      place_context:{
        location_name:'Test Location',
        current_tensions:['tension1','tension2'],
        historical_patterns:['pattern1'],
        bioregion:'Test Bioregion'
},
      stakeholder_types:['elders','youth']
};
  
const result =awaitstoryOfPlaceInquiryFlow(input);
  
expect(result.questions.elders).toBeDefined();
expect(result.questions.youth).toBeDefined();
expect(result.questions.elders.length).toBeGreaterThan(10);
});
  
it('includes workshop protocol',async()=>{
// ... test
});
});
```

### Integration Tests with Emulator

bash

```bash
# Start emulator
firebase emulators:start

# In another terminal
npm run test:integration
```

typescript

```typescript
// test/integration/stage1.integration.test.ts

importaxiosfrom'axios';

constFUNCTION_URL='http://localhost:5001/your-project/us-central1/generateInquiryQuestions';

describe('Stage 1 Integration Tests',()=>{
  
it('returns valid response',async()=>{
const response =await axios.post(FUNCTION_URL,{
      project_name:'Integration Test',
      place_context:{
        location_name:'Test',
        current_tensions:['test'],
        historical_patterns:['test'],
        bioregion:'test'
},
      stakeholder_types:['elders']
});
  
expect(response.status).toBe(200);
expect(response.data.questions.elders).toBeDefined();
});
});
```

---

## Deployment

### Deploy All Functions

bash

```bash
firebase deploy --only functions
```

### Deploy Specific Function

bash

```bash
firebase deploy --only functions:generateInquiryQuestions
```

### View Logs

bash

```bash
# Live tail
firebase functions:log --only generateInquiryQuestions

# Last 100 lines
firebase functions:log --limit 100
```

---

## Contributing

When adding new functions:

1. Create flow in `src/ai/flows/`
2. Export function in `src/index.ts`
3. Add input/output schemas
4. Write unit tests
5. Test with emulator
6. Document here
7. Update main README

---

## License

CC BY-NC-SA 4.0 - See [LICENSE](../../LICENSE)
`</artifact>`
