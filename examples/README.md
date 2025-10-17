`<artifact identifier="examples-readme" type="text/markdown" title="examples/README.md">`

# Examples Directory

Sample data and documents for testing the Regenerative Development AI system.

---

## Contents

This directory contains:

1. **Sample Input Data** - JSON files for testing each stage
2. **Sample Governance Documents** - Policy docs for Stage 4 testing
3. **Test Templates** - Structured data for different project types
4. **Expected Outputs** - Reference outputs for validation

---

## Sample Input Files

### sample-stage1-input.json

**Purpose:** Test Stage 1 (Generate Inquiry Questions)

**Contents:**

json

```json
{
"project_name":"Carrington Moss Alternative Vision",
"place_context":{
"location_name":"Carrington, Greater Manchester",
"current_tensions":[
"6500 home development on green belt",
"peatland destruction",
"community displacement"
],
"historical_patterns":[
"peatland commons",
"local food production",
"working class community"
],
"bioregion":"Greater Manchester Wetlands / Mersey Basin"
},
"stakeholder_types":[
"long_term_residents",
"environmental_groups",
"local_farmers",
"council_staff"
]
}
```

**How to use:**

1. Copy contents
2. Paste into Stage 1 form on frontend
3. Click "Run Stage 1"
4. Compare output with expected results

---

### sample-stage2-input.json

**Purpose:** Test Stage 2 (Process Stakeholder Responses)

**Contents:**

json

```json
{
"project_name":"Carrington Moss Alternative Vision",
"stakeholder_responses":{
"elders":[
"The moss was our commons, we all shared it",
"Young folk don't understand what's been lost",
"It provided for us - fuel, food, water"
],
"youth":[
"We want to stay but there's nothing for us here",
"The moss is special, we just don't know how to protect it",
"Need jobs that connect us to place"
],
"environmental_groups":[
"The peatland stores massive amounts of carbon",
"Rare species depend on this habitat",
"Development would be irreversible damage"
]
},
"essence_hypothesis":"A place where common land holds community together"
}
```

**How to use:**

1. After running Stage 1 successfully
2. Copy contents to Stage 2 form
3. Click "Run Stage 2"
4. Review Essential Processes assessment

---

### sample-stage3-input.json

**Purpose:** Test Stage 3 (Generate Design Brief)

**Contents:**

json

```json
{
"validated_essence":"A place where peatland commons call community to collective stewardship",
"proposed_intervention":"Community-led peatland restoration with sustainable land use",
"stakeholder_commitments":[
{
"stakeholder":"long_term_residents",
"commitment":"Share traditional knowledge of peatland management",
"capacity":"high"
},
{
"stakeholder":"environmental_groups",
"commitment":"Provide technical expertise and funding connections",
"capacity":"high"
},
{
"stakeholder":"youth",
"commitment":"Participate in restoration work and skill-building",
"capacity":"medium"
}
],
"essential_processes":{
"resource_generation":15,
"identity_belonging":35,
"nourishment":25
}
}
```

**How to use:**

1. After validating Stage 2 essence with community
2. Input commitments from stakeholder workshops
3. Click "Run Stage 3"
4. Review design brief for designers

---

## Sample Governance Documents

Located in `sample-governance-docs/` subdirectory.

### For UK Planning Opposition Projects

Use these documents:

* `uk-planning-policy-extract.md` - NPPF extracts
* `local-authority-development-plan.md` - Council policy
* `community-land-trust-bylaws.md` - CLT governance example

### For Community Asset Projects

Use these documents:

* `community-land-trust-bylaws.md` - Asset governance
* `cooperative-articles.md` - Cooperative structure

### For Learning About Capture

Use this document:

* `failed-ngo-project-report.md` - Example of captured project

**Purpose:** Test Stage 4's VDK ability to detect extractive patterns

---

## Test Templates by Project Type

### Planning Opposition

**Input files:**

* `sample-stage1-input.json` (Carrington Moss example)
* `sample-governance-docs/uk-planning-policy-extract.md`
* `sample-governance-docs/local-authority-development-plan.md`

**Expected outcomes:**

* Questions about loss, commons, alternatives
* Essence around place protection
* Governance pathways including CLT option
* VDK detecting external control patterns

---

### Community Land Trust

**Input template:**

json

```json
{
"project_name":"[Your CLT Name]",
"place_context":{
"location_name":"[Location]",
"current_tensions":[
"housing affordability",
"gentrification",
"community displacement"
],
"historical_patterns":[
"cooperative traditions",
"mutual aid",
"community solidarity"
],
"bioregion":"[Your bioregion]"
},
"stakeholder_types":[
"prospective_residents",
"local_authority",
"housing_association",
"community_members"
]
}
```

**Governance documents:**

* `community-land-trust-bylaws.md`
* Relevant local housing policy

---

### Worker Cooperative

**Input template:**

json

```json
{
"project_name":"[Cooperative Name]",
"place_context":{
"location_name":"[Location]",
"current_tensions":[
"precarious employment",
"lack of worker ownership",
"extractive business models"
],
"historical_patterns":[
"craft traditions",
"mutual support",
"skill sharing"
],
"bioregion":"[Your bioregion]"
},
"stakeholder_types":[
"prospective_members",
"existing_workers",
"community",
"customers"
]
}
```

**Governance documents:**

* `cooperative-articles.md`
* Local cooperative law

---

## Expected Outputs

### Stage 1 Expected Output

**Questions should:**

* Be 15-20 per stakeholder group
* Include mix of:
  * Memory/history questions
  * Relationship/pattern questions
  * Aspiration/potential questions
  * Non-human stakeholder questions
* Be open-ended and deep
* Avoid extractive framing
* Be culturally appropriate

**Workshop protocol should include:**

* Opening ritual/activity
* Core inquiry process
* Synthesis activity
* Closing

---

### Stage 2 Expected Output

**Assessment should:**

* Score all Essential Processes (0-100%)
* Identify priority process (lowest score)
* Suggest leverage points
* Refine place essence
* Provide confidence level (High/Medium/Low)
* Include reasoning for all assessments

**Confidence markers:**

* **High:** Rich data, clear patterns, strong essence
* **Medium:** Some data, emerging patterns
* **Low:** Sparse data, need more inquiry

---

### Stage 3 Expected Output

**Design brief should include:**

* 4-6 core design principles
* Three Spheres analysis (opportunities + risks per sphere)
* Sweet spots (where all three align)
* Nested scales visualization (site → bioregion)
* Success metrics (ecological, social, economic)
* Design phase workshop protocol

---

### Stage 4 Expected Output

**Should generate:**

* 3+ governance pathways
* Each pathway has:
  * Governance model
  * Legal framework
  * Pros and cons
  * Capture risk level
  * Viability score
  * VDK trajectory analysis
* Rejected pathways (if VDK detected extraction)
* Iteration history showing refinement

**VDK should detect:**

* External asset ownership
* "Technical oversight" language
* Advisory vs. decision-making roles
* Conditional asset transfer
* Self-justifying patterns

---

## How to Use These Examples

### For Learning

1. **Read through** sample inputs
2. **Understand** what makes good inputs
3. **See patterns** across different project types
4. **Note adaptations** for your context

### For Testing

1. **Copy** sample input
2. **Paste** into system
3. **Run** stage
4. **Compare** output with expected results
5. **Note** any deviations

### For Adaptation

1. **Start** with closest example
2. **Modify** for your project
3. **Keep** structure similar
4. **Test** with system
5. **Refine** based on results

---

## Creating Your Own Examples

### Good Test Data Has:

**Specificity:**

* Real place names (or realistic pseudonyms)
* Concrete tensions (not vague)
* Actual historical patterns
* Named stakeholder groups

**Richness:**

* Multiple tensions (3-5)
* Diverse stakeholders (4-8 types)
* Historical depth
* Clear bioregion context

**Authenticity:**

* Could be real project
* Tensions are genuine
* Patterns make sense together
* Stakes are clear

### Poor Test Data:

❌ Too generic ("Community project")

❌ Too vague ("Problems exist")

❌ Unrealistic ("Everyone agrees")

❌ No context ("A place somewhere")

❌ Single stakeholder type

---

## Validation Scripts

### Test All Stages

bash

```bash
# From project root
cd examples

# Test Stage 1
curl -X POST http://localhost:5001/[project]/us-central1/generateInquiryQuestions \
  -H "Content-Type: application/json"\
  -d @sample-stage1-input.json \
| jq > output/stage1-test-output.json

# Compare with expected
diff output/stage1-test-output.json expected-outputs/stage1.json
```

### Automated Testing

bash

```bash
# Run validation suite
npm run validate-examples

# This will:
# 1. Test each stage with sample data
# 2. Verify output structure
# 3. Check for expected patterns
# 4. Report any deviations
```

---

## Contributing Examples

### We Need Examples For:

**Geographic diversity:**

- [ ] More UK regions
- [ ] European contexts
- [ ] Global South
- [ ] Indigenous communities
- [ ] Island/coastal contexts
- [ ] Mountain/highland contexts
- [ ] Urban contexts

**Project types:**

- [ ] Urban food hubs
- [ ] Rural energy cooperatives
- [ ] Watershed restoration
- [ ] Cultural heritage sites
- [ ] Community gardens/farms
- [ ] Shared workspace
- [ ] Community healthcare

**Governance models:**

- [ ] Municipal partnerships
- [ ] Social enterprises
- [ ] Benefit corporations
- [ ] Charitable trusts
- [ ] Unincorporated associations

### How to Contribute

1. **Create** sample input files
2. **Test** with system
3. **Document** expected outputs
4. **Submit** PR with:
   - Input files
   - Brief context
   - Expected outputs
   - Any notes

See [CONTRIBUTING.md](../CONTRIBUTING.md)

---

## Troubleshooting Examples

### "Output doesn't match expected"

**This is normal!** AI outputs vary slightly each time.

**Check:**

- Is the *structure* the same?
- Are *key elements* present?
- Is *quality* comparable?

**Don't expect:** Exact word-for-word match

---

### "Getting errors with sample data"

**Possible causes:**

- Backend not running
- API key not set
- Model name changed
- Input schema changed

**Debug steps:**

1. Check backend logs
2. Verify API key
3. Test with minimal input first
4. Check schema validation

---

### "Sample doesn't fit my context"

**That's fine!** Adapt it:

- Change location
- Modify tensions
- Adjust stakeholders
- Keep structure similar

**The samples are starting points, not rigid templates.**

---

## License

All example files: CC BY-NC-SA 4.0

You are free to:

- Use as templates
- Adapt for your projects
- Share with others

You must:

- Attribute if sharing
- Use non-commercially
- Share adaptations under same license

See [LICENSE](../LICENSE)

---

## Questions?

**About examples:**

- Create issue with `[examples]` label
- Ask in[Discussions](https://github.com/[your-username]/regenerative-development-ai/discussions)

**Need different examples:**

- Request in issue
- Contribute your own
- Email [examples-email]

---

**Good examples make great projects!** 🌱

---

## Complete Documentation Package

I've now created **all** the remaining documentation files:

### Your Repository Structure is Now Complete:

```
regenerative-development-ai/
├── README.md ✅
├── LICENSE ✅
├── CONTRIBUTING.md ✅
├── ROADMAP.md ✅
├── docs/
│   ├── README.md ✅
│   ├── getting-started.md ✅
│   ├── faq.md ✅
│   ├── practitioner-guide.md ✅ (you have this)
│   ├── theory-guide.md ✅ (you have this)
│   └── stage-X-guides.md (you can create these next)
├── case-studies/
│   ├── README.md ✅
│   ├── carrington-moss/ (you're creating this)
│   ├── bajo-baudo/ (reference)
│   └── template/
│       └── case-study-template.md ✅
├── frontend/
│   └── README.md ✅
├── backend/
│   ├── README.md ✅
│   ├── functions/
│   │   └── README.md ✅
│   └── constitutions/ (you have these)
├── examples/
│   ├── README.md ✅
│   ├── sample-stage1-input.json ✅
│   ├── sample-stage2-input.json ✅
│   ├── sample-stage3-input.json ✅
│   └── sample-governance-docs/ ✅
│       ├── README.md ✅
│       ├── uk-planning-policy-extract.md ✅
│       ├── community-land-trust-bylaws.md ✅
│       ├── cooperative-articles.md ✅
│       ├── failed-ngo-project-report.md ✅
│       └── local-authority-development-plan.md ✅
```
