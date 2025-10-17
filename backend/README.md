## Regenerative Development AI - Backend

Firebase Functions backend for the Regenerative Development AI system.

---

## Overview

Serverless backend built on Firebase Functions that handles:

* AI flow orchestration (Gemini API)
* VDK (Verified Dialectical Kernel) processing
* Document parsing and analysis
* Data validation and storage
* API endpoints for frontend

---

## Architecture

```
Frontend Request
    ↓
Firebase Functions (API Gateway)
    ↓
AI Flow Orchestration
    ├─→ Gemini 2.5 Pro API
    ├─→ VDK Processing
    └─→ Document Analysis
    ↓
Response to Frontend
```

---

## Tech Stack

* **Runtime:** Node.js 18
* **Framework:** Firebase Functions (2nd gen)
* **Language:** TypeScript
* **AI:** Google Gemini 2.5 Pro API
* **Database:** Firestore (optional persistence)
* **Storage:** Cloud Storage (file uploads)

---

## Project Structure

```
backend/
├── functions/                 # Firebase Functions code
│   ├── src/
│   │   ├── index.ts          # Function exports
│   │   ├── ai/               # AI flows
│   │   │   ├── flows/        # Stage implementations
│   │   │   │   ├── storyOfPlaceInquiryFlow.ts
│   │   │   │   ├── essentialProcessesAssessmentFlow.ts
│   │   │   │   ├── threeSpheresSynthesisFlow.ts
│   │   │   │   └── governanceHarmonizationFlow.ts
│   │   │   └── vdk/          # VDK implementation
│   │   │       ├── coherenceCheck.ts
│   │   │       └── trajectoryAnalysis.ts
│   │   ├── types/            # TypeScript types
│   │   └── utils/            # Helper functions
│   ├── package.json
│   └── tsconfig.json
├── constitutions/            # Constitutional templates
│   ├── regenerative.md
│   └── uk-commons-governance.md
└── README.md (this file)
```

---

## Getting Started

### Prerequisites

* Node.js 18+
* Firebase CLI installed
* Firebase project created
* Gemini API key

### Installation

bash

```bash
cd backend/functions

# Install dependencies
npminstall

# Login to Firebase
firebase login

# Initialize project
firebase init functions
```

### Configuration

bash

```bash
# Create .env file
cd functions
cat> .env <<EOF
GEMINI_API_KEY=your_gemini_api_key_here
EOF

# Set in Firebase (for deployed functions)
firebase functions:config:set gemini.api_key="your_key_here"

# Verify
firebase functions:config:get
```

### Development

bash

```bash
# Start emulator
cd backend/functions
npm run serve

# Functions available at:
# http://localhost:5001/[project-id]/us-central1/[function-name]
```

### Deployment

bash

```bash
# Deploy all functions
firebase deploy --only functions

# Deploy specific function
firebase deploy --only functions:generateInquiryQuestions

# View logs
firebase functions:log
```

---

## API Endpoints

### Stage 1: Generate Inquiry Questions

**Endpoint:** `/generateInquiryQuestions`

**Method:** POST

**Auth:** None (rate limited)

**Request Body:**

json

```json
{
"project_name":"Carrington Moss Commons",
"place_context":{
"location_name":"Carrington, Greater Manchester",
"current_tensions":["green belt development","peatland destruction"],
"historical_patterns":["peatland commons","local food production"],
"bioregion":"Greater Manchester Wetlands"
},
"stakeholder_types":["long_term_residents","environmental_groups"]
}
```

**Response:**

json

```json
{
"questions":{
"long_term_residents":["Question 1","Question 2", ...],
"environmental_groups":["Question 1","Question 2", ...]
},
"workshop_protocol":"...",
"metadata":{
"model_used":"gemini-2.5-pro",
"processing_time_ms":2341,
"timestamp":"2025-01-15T10:30:00Z"
}
}
```

---

### Stage 2: Process Stakeholder Responses

**Endpoint:** `/processStakeholderResponses`

**Method:** POST

**Request Body:**

json

```json
{
"project_name":"Carrington Moss Commons",
"stakeholder_responses":{
"elders":["Quote 1","Quote 2", ...],
"youth":["Quote 1","Quote 2", ...]
},
"essence_hypothesis":"Initial hypothesis",
"essential_processes_from_stage1":{...}
}
```

**Response:**

json

```json
{
"essential_processes_assessment":{
"nourishment":{"ecological":20,"economic":30,"social":25,"overall":25},
"resource_generation":{"ecological":15,"economic":10,"social":20,"overall":15},
    ...
},
"refined_essence":"A place where ancestral wisdom seeks new hands...",
"priority_intervention":"Create paid restoration work...",
"confidence_level":"HIGH",
"next_steps":"Proceed to Stage 3"
}
```

---

### Stage 3: Generate Design Brief

**Endpoint:** `/generateDesignBrief`

**Method:** POST

**Request Body:**

json

```json
{
"validated_essence":"Community-validated essence",
"proposed_intervention":"Description of intervention",
"stakeholder_commitments":[
{
"stakeholder":"elders",
"commitment":"Provide traditional knowledge",
"capacity":"high"
}
],
"essential_processes":{...}
}
```

**Response:**

json

```json
{
"core_design_principles":["Principle 1","Principle 2", ...],
"three_spheres_synthesis":{
"economic":{...},
"social":{...},
"ecological":{...},
"sweet_spots":[...]
},
"nested_scales":{...},
"success_metrics":{...},
"workshop_protocol":"..."
}
```

---

### Stage 4: Governance Harmonization

**Endpoint:** `/harmonizeGovernance`

**Method:** POST

**Content-Type:** multipart/form-data

**Request Body:**

json

```json
{
"design_brief":{...},
"constitution":"regenerative.md",
"analysis_focus":["governance","capture_risks","implementation"]
}
```

**Files:** Multiple PDFs/Word docs (policy documents)

**Response:**

json

```json
{
"pathways":[
{
"name":"Municipal Partnership Model",
"governance_model":"...",
"legal_framework":"...",
"viability_score":0.89,
"pros":[...],
"cons":[...],
"capture_risk":"MEDIUM",
"vdk_trajectory":"COHERENT",
"best_for":"Communities with strong municipal relationships"
},
{...},
{...}
],
"rejected_pathways":[
{
"name":"NGO Partnership (Rejected)",
"rejection_reason":"EXTRACTIVE_DRIFT",
"vdk_analysis":"..."
}
],
"iteration_history":[...]
}
```

---

## AI Flows

### Flow Structure

Each stage is implemented as a separate flow:

typescript

```typescript
// src/ai/flows/storyOfPlaceInquiryFlow.ts

exportasyncfunctionstoryOfPlaceInquiry(
  input:StoryOfPlaceInput
):Promise<StoryOfPlaceOutput>{
// 1. Validate input
const validated =validateInput(input);
  
// 2. Build prompt
const prompt =buildPrompt(validated);
  
// 3. Call Gemini API
const response =awaitcallGemini(prompt);
  
// 4. Parse and validate output
const parsed =parseOutput(response);
  
// 5. Return structured result
return parsed;
}
```

### Prompt Engineering

Prompts are carefully engineered for:

* **Regenerative Development framework** grounding
* **Cultural sensitivity**
* **Place-specificity**
* **Anti-extraction** principles

Example prompt structure:

typescript

```typescript
const prompt =`
You are an expert regenerative development practitioner trained in:
- Story of Place inquiry (Pamela Mang, Bill Reed)
- Essential Processes framework
- Place-based design
- Community sovereignty principles

Context:
${JSON.stringify(context)}

Task:
Generate 15-20 deep, culturally-sensitive inquiry questions...

Requirements:
- Questions should reveal essence, not extract data
- Honor community wisdom
- Avoid extractive language
- Respect place uniqueness

Output format: JSON
`;
```

---

## VDK (Verified Dialectical Kernel)

### What is VDK?

The VDK detects when governance refinements drift toward extractive patterns during Stage 4.

### How It Works

typescript

```typescript
// Simplified VDK flow

1.Generate initial governance protocol
2.Critique against constitution + design brief
3.VDKCoherenceCheck:
-Analyze language shifts
-Detect power imbalances
-Checkfor self-justifying patterns
-Compare to known failure patterns
4.IfCOHERENT:Continue refinement
5.IfEXTRACTIVE_DRIFT:Revert,try alternative
6.Repeatfor multiple pathways
```

### VDK Implementation

typescript

```typescript
// src/ai/vdk/coherenceCheck.ts

exportfunctioncheckCoherence(
  iteration:GovernanceIteration,
  previousIteration:GovernanceIteration,
  constitution:Constitution
):CoherenceResult{
  
// Language analysis
const languageShift =analyzeLanguageShift(
    iteration.text,
    previousIteration.text
);
  
// Power dynamics
const powerBalance =analyzePowerDynamics(iteration.structure);
  
// Constitutional alignment
const alignment =checkConstitutionalAlignment(
    iteration,
    constitution
);
  
// Pattern matching
const knownPattern =matchKnownFailurePatterns(iteration);
  
// Compute coherence score
const score =computeCoherenceScore({
    languageShift,
    powerBalance,
    alignment,
    knownPattern
});
  
// Determine trajectory
if(score >0.85&&!knownPattern){
return{ trajectory:'COHERENT', score };
}elseif(knownPattern || score <0.6){
return{ trajectory:'EXTRACTIVE_DRIFT', score, concerns:[...]};
}else{
return{ trajectory:'UNCERTAIN', score };
}
}
```

### Known Failure Patterns

VDK checks against patterns from documented failed projects:

typescript

```typescript
constFAILURE_PATTERNS=[
{
    name:'External Asset Ownership',
    indicators:['NGO owns','community has access','usage rights'],
    severity:'HIGH'
},
{
    name:'Technical Oversight Capture',
    indicators:['technical oversight','expert approval','capacity building required'],
    severity:'MEDIUM'
},
{
    name:'Advisory Role Tokenism',
    indicators:['advisory board','consultative role','stakeholder input'],
    severity:'HIGH'
},
// ... more patterns
];
```

---

## Document Processing

### PDF Parsing

typescript

```typescript
// src/utils/documentParser.ts

importpdffrom'pdf-parse';

exportasyncfunctionparsePDF(buffer:Buffer):Promise<string>{
const data =awaitpdf(buffer);
return data.text;
}
```

### Word Document Parsing

typescript

```typescript
importmammothfrom'mammoth';

exportasyncfunctionparseDocx(buffer:Buffer):Promise<string>{
const result =await mammoth.extractRawText({ buffer });
return result.value;
}
```

### Document Chunking

Large documents are chunked for processing:

typescript

```typescript
exportfunctionchunkDocument(text:string, maxChunkSize:number=4000):string[]{
const sentences = text.split(/[.!?]+/);
const chunks:string[]=[];
let currentChunk ='';
  
for(const sentence of sentences){
if(currentChunk.length+ sentence.length< maxChunkSize){
      currentChunk += sentence +'. ';
}else{
      chunks.push(currentChunk.trim());
      currentChunk = sentence +'. ';
}
}
  
if(currentChunk) chunks.push(currentChunk.trim());
  
return chunks;
}
```

---

## Error Handling

### Retry Logic

typescript

```typescript
exportasyncfunctioncallGeminiWithRetry(
  prompt:string,
  maxRetries:number=3
):Promise<string>{
  
for(let i =0; i < maxRetries; i++){
try{
returnawaitcallGemini(prompt);
}catch(error){
if(i === maxRetries -1)throw error;
    
// Exponential backoff
awaitsleep(Math.pow(2, i)*1000);
}
}
  
thrownewError('Max retries exceeded');
}
```

### Error Responses

typescript

```typescript
exportfunctionhandleError(error:any):HttpsError{
if(error.code==='RESOURCE_EXHAUSTED'){
returnnewHttpsError('resource-exhausted','API rate limit exceeded');
}
  
if(error.code==='INVALID_ARGUMENT'){
returnnewHttpsError('invalid-argument', error.message);
}
  
// Generic error
console.error('Function error:', error);
returnnewHttpsError('internal','An error occurred processing your request');
}
```

---

## Performance Optimization

### Caching

typescript

```typescript
// Cache common responses
const cache =newMap<string,any>();

exportasyncfunctiongetCachedOrCompute(
  key:string,
computeFn:()=>Promise<any>,
  ttl:number=3600000// 1 hour
):Promise<any>{
  
const cached = cache.get(key);
if(cached &&Date.now()- cached.timestamp< ttl){
return cached.data;
}
  
const data =awaitcomputeFn();
  cache.set(key,{ data, timestamp:Date.now()});
  
return data;
}
```

### Parallel Processing

typescript

```typescript
// Process multiple stakeholder groups in parallel
const results =awaitPromise.all(
  stakeholderTypes.map(type => 
generateQuestionsForStakeholder(type, context)
)
);
```

---

## Rate Limiting

### Gemini API Limits

**Free tier:**

* 15 requests/minute
* 1,500 requests/day
* 1M tokens/day

**Paid tier:**

* 1,000 requests/minute
* 10M tokens/day

### Implementation

typescript

```typescript
importrateLimitfrom'express-rate-limit';

const limiter =rateLimit({
  windowMs:60*1000,// 1 minute
  max:10,// 10 requests per minute per IP
  message:'Too many requests, please try again later'
});

exportconst rateLimitedFunction = functions
.runWith({ memory:'1GB', timeoutSeconds:300})
.https.onRequest(limiter,async(req, res)=>{
// Function logic
});
```

---

## Testing

### Unit Tests

bash

```bash
# Run tests
npmtest

# Watch mode
npm run test:watch

# Coverage
npm run test:coverage
```

### Integration Tests

typescript

```typescript
// functions/test/stage1.test.ts

import{ generateInquiryQuestions }from'../src/ai/flows/storyOfPlaceInquiryFlow';

describe('Stage 1: Inquiry Questions',()=>{
it('should generate questions for each stakeholder type',async()=>{
const input ={
      project_name:'Test Project',
      place_context:{
        location_name:'Test Location',
        current_tensions:['tension1'],
        historical_patterns:['pattern1'],
        bioregion:'Test Region'
},
      stakeholder_types:['elders','youth']
};
  
const result =awaitgenerateInquiryQuestions(input);
  
expect(result.questions.elders).toHaveLength(15);
expect(result.questions.youth).toHaveLength(15);
});
});
```

### Emulator Testing

bash

```bash
# Start emulators
firebase emulators:start

# Test functions locally
curl -X POST http://localhost:5001/[project]/us-central1/generateInquiryQuestions \
  -H "Content-Type: application/json"\
  -d @test-data/stage1-input.json
```

---

## Monitoring & Logging

### Firebase Console

View logs in Firebase Console:

* Functions → Logs
* Filter by function name
* View error rates
* Monitor execution times

### Structured Logging

typescript

```typescript
import*as functionsfrom'firebase-functions';

functions.logger.info('Stage 1 started',{
  projectName: input.project_name,
  stakeholderCount: input.stakeholder_types.length
});

functions.logger.error('Gemini API error',{
  error: error.message,
  projectName: input.project_name
});
```

### Performance Monitoring

typescript

```typescript
import{performance}from'perf_hooks';

const start =performance.now();
// ... operation
const duration =performance.now()- start;

functions.logger.info('Operation completed',{ 
  duration_ms: duration 
});
```

---

## Security

### Environment Variables

Never commit:

* API keys
* Service account credentials
* Database passwords

Use:

* Firebase config (`firebase functions:config:set`)
* Environment variables (`.env` for local, gitignored)
* Secret Manager (for production)

### Input Validation

typescript

```typescript
import*as zfrom'zod';

constStage1Schema= z.object({
  project_name: z.string().min(1).max(200),
  place_context: z.object({
    location_name: z.string().min(1),
    current_tensions: z.array(z.string()).min(1),
    historical_patterns: z.array(z.string()).min(1),
    bioregion: z.string()
}),
  stakeholder_types: z.array(z.string()).min(1).max(10)
});

exportfunctionvalidateStage1Input(input:unknown){
returnStage1Schema.parse(input);
}
```

### CORS

typescript

```typescript
importcorsfrom'cors';

const corsHandler =cors({
  origin:[
'https://yourdomain.com',
'http://localhost:3000'// Development
]
});

exportconst secureFunction = functions.https.onRequest((req, res)=>{
corsHandler(req, res,async()=>{
// Function logic
});
});
```

---

## Troubleshooting

### "Function deployment failed"

bash

```bash
# Check logs
firebase functions:log

# Common issues:
# - TypeScript compilation errors
npm run build

# - Missing dependencies
npminstall

# - Memory/timeout issues
# Increase in function config:
functions.runWith({ memory: '2GB', timeoutSeconds: 540})
```

### "Gemini API rate limit exceeded"

typescript

```typescript
// Implement exponential backoff
// Use caching for repeated requests
// Consider upgrading to paid tier
```

### "Cold start latency"

typescript

```typescript
// Use min instances (costs more but faster)
functions.runWith({ 
  minInstances:1,// Keep 1 instance warm
  memory:'1GB'
})
```

### "Out of memory"

typescript

```typescript
// Increase memory allocation
functions.runWith({ memory:'2GB'})

// Process documents in chunks
// Stream large files instead of loading fully
```

---

## Cost Optimization

### Estimated Costs (USD)

**Per project (4 stages):**

* Gemini API: $0.50-$2.00
* Cloud Functions: $0.10-$0.50
* Storage: $0.01
* **Total: ~$0.60-$2.50**

**At scale (100 projects/month):**

* ~$60-$250/month

### Optimization Tips

1. **Use Flash model for simple tasks:**

typescript

```typescript
// Use Pro for complex (Stage 4)
// Use Flash for simple (Stage 1 question generation)
```

2. **Cache common queries:**

typescript

```typescript
// Cache constitutional templates
// Cache common governance patterns
```

3. **Batch operations:**

typescript

```typescript
// Process multiple stakeholder types in one call
```

4. **Set appropriate timeouts:**

typescript

```typescript
// Don't use 540s timeout if 60s sufficient
```

---

## Contributing

See [CONTRIBUTING.md](../CONTRIBUTING.md)

### Backend-Specific Guidelines

* All functions in TypeScript
* Use Zod for input validation
* Include JSDoc comments
* Write unit tests for complex logic
* Log important events
* Handle errors gracefully
* Update this README for major changes

---

## Resources

* [Firebase Functions Docs](https://firebase.google.com/docs/functions)
* [Gemini API Docs](https://ai.google.dev/docs)
* [TypeScript Handbook](https://www.typescriptlang.org/docs/)

---

## License

CC BY-NC-SA 4.0 - See [LICENSE](../LICENSE)
