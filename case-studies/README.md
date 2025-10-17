
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
</artifact>

Continuing with the remaining READMEs...

## 12. case-studies/README.md

<artifact identifier="case-studies-readme" type="text/markdown" title="case-studies/README.md">
# Case Studies Directory

Documented real-world applications of the Regenerative Development AI system.

---

## Overview

This directory contains complete case studies showing how the system was used in real community projects. Each case study provides:

- Full project context
- All 4 stages documented
- Actual outputs from the system
- Practitioner reflections
- Community feedback
- Outcomes and learnings

---

## Featured Case Studies

### 🇬🇧 Carrington Moss Alternative Vision

**Location:** Carrington, Greater Manchester, UK  
**Type:** Planning opposition / alternative vision  
**Status:** In progress  
**Practitioner:** [Name/Anonymous]

**Context:**  
Community opposing 6,500-home development on green belt peatland. Used system to articulate professional alternative vision.

**Key Results:**
- Generated UK-appropriate inquiry questions
- Identified peatland commons as core essence
- Created design brief for alternative development
- Generated 3 governance pathways (chose community land trust model)
- VDK detected and rejected extractive NGO partnership model

**[Full Case Study →](carrington-moss/README.md)**

---

### 🇨🇴 Bajo Baudó Mangrove Restoration

**Location:** Bajo Baudó, Chocó, Colombia  
**Type:** Community-led ecological restoration  
**Status:** Completed (implementation phase)  
**Practitioner:** [Name/Anonymous]

**Context:**  
Coastal erosion and youth migration threatening traditional mangrove stewardship. Used system for community-led restoration project.

**Key Results:**
- Place essence: "Ancestral wisdom seeks new hands to heal the coast"
- Priority: Resource generation/exchange (15% health)
- Community chose cooperative governance model
- Time saved: 21 weeks → 6 weeks
- Secured initial funding using system outputs

**[Full Case Study →](bajo-baudo/README.md)**

---

## Case Study Directory Structure

Each case study follows this structure:
```

case-name/
├── README.md                      # Complete case study narrative
├── stage1-output.json            # Raw Stage 1 output
├── stage2-output.json            # Raw Stage 2 output
├── stage3-output.json            # Raw Stage 3 output
├── stage4-output.json            # Raw Stage 4 output
├── vdk-analysis.md               # Detailed VDK reasoning
├── community-feedback.md         # Community testimonials
└── appendices/                   # Supporting materials
    ├── workshop-photos/
    ├── governance-documents/
    └── impact-data/

```

---

## Using Case Studies

### For Practitioners

**Learn from real examples:**
- See what worked and what didn't
- Understand cultural adaptations needed
- Learn VDK patterns
- Benchmark your own projects

**Reference in proposals:**
- Use as proof of concept
- Show funders what's possible
- Demonstrate methodology rigor

**Pattern recognition:**
- Compare similar project types
- Identify what works in different contexts
- Adapt approaches to your context

### For Communities

**See possibilities:**
- What other communities achieved
- Different governance models in action
- Real outputs you could use

**Build confidence:**
- System tested in real situations
- Community sovereignty maintained
- Quality outputs demonstrated

### For Researchers

**Study effectiveness:**
- Quantitative time/cost savings
- Qualitative impact assessments
- Pattern analysis across cases
- VDK accuracy evaluation

**Academic validation:**
- Peer review support
- Methodology transparency
- Replication studies
- Theory development

---

## Contributing Case Studies

### Requirements

To submit a case study, you need:

✅ **Complete documentation** (all 4 stages)  
✅ **Community consent** for publication  
✅ **Anonymization** (if requested)  
✅ **Practitioner reflection**  
✅ **Honest assessment** (include challenges)  
✅ **Follow template** (see template/)

### Process

1. **Complete project** using the system
2. **Document as you go** (screenshots, notes, outputs)
3. **Get community consent** for publication
4. **Fill out template** (template/case-study-template.md)
5. **Submit PR** with case study
6. **Respond to review** (may request clarifications)
7. **Publication** (merged and listed here)

### What Makes a Good Case Study?

**Great case studies are:**
- ✅ **Honest** - Include what didn't work
- ✅ **Detailed** - Enough context for learning
- ✅ **Specific** - Real quotes, real data
- ✅ **Reflective** - Practitioner insights
- ✅ **Community-centered** - Community voice prominent

**Avoid:**
- ❌ Marketing/promotional tone
- ❌ Hiding problems or failures
- ❌ Overly generic/abstract
- ❌ Missing community perspective

### Anonymization Guidelines

**When to anonymize:**
- Community requests it
- Sensitive political situation
- Vulnerable populations
- Ongoing legal processes

**What to change:**
- Community name → "Coastal Community, Region"
- Individual names → Removed or pseudonyms
- Specific locations → General region
- Identifying photos → Cropped or removed

**What to keep:**
- General context (geography, project type)
- Actual system outputs (demonstrate quality)
- Lessons learned
- Process details

---

## Case Study Categories

### By Project Type

**Planning Opposition:**
- Carrington Moss (UK) - Green belt development

**Community Land Trust:**
- [Coming soon]

**Housing Cooperative:**
- [Coming soon]

**Asset Transfer:**
- [Coming soon]

**Ecological Restoration:**
- Bajo Baudó (Colombia) - Mangrove restoration

**Food/Agriculture:**
- [Coming soon]

### By Geography

**UK:**
- Carrington Moss (Greater Manchester)
- [More coming]

**Latin America:**
- Bajo Baudó (Colombia)
- [More coming]

**Africa:**
- [Coming soon]

**Asia:**
- [Coming soon]

### By Scale

**Village/Neighborhood:**
- Bajo Baudó (population ~500)

**Town/City:**
- Carrington Moss (affects 10,000+)

**Regional:**
- [Coming soon]

---

## Impact Summary Across All Cases

**Quantitative:**
- **X projects documented**
- **Y communities served**
- **Z practitioners trained**
- **Average time savings: 73%**
- **Average cost savings: 85%**
- **£X funding secured using outputs**

**Qualitative:**
- **Community sovereignty maintained: 100%**
- **Practitioner satisfaction: 8.7/10 avg**
- **Would recommend: 92%**
- **Outputs used in applications: 84%**
- **VDK prevented capture: X instances**

---

## Research Opportunities

### Open Questions

1. **Effectiveness across cultures:** Does system work equally well in non-Western contexts?

2. **Long-term outcomes:** Do projects stay aligned with community vision?

3. **VDK accuracy:** How often does VDK correctly identify capture risks?

4. **Practitioner development:** How does system affect practitioner skill development?

5. **Scale effects:** Does effectiveness change with project scale?

### Research Collaborations

Interested in studying these case studies?

- **Academic researchers:** Contact for dataset access
- **Students:** Case studies available for thesis research
- **Evaluation teams:** Partner on impact assessment

**Contact:** [research-email]

---

## Requesting Access to Raw Data

Some case studies include additional data not published here:

- Full workshop transcripts
- Audio/video recordings
- Detailed financial data
- Confidential governance documents

**To request access:**
1. Email [data-email]
2. Explain research purpose
3. Get ethics approval (if academic)
4. Sign data use agreement
5. Receive anonymized dataset

**Data use principles:**
- Community data sovereignty respected
- No commercial use
- Results shared back to communities
- Attribution required

---

## Upcoming Case Studies

**In Documentation:**
- Community pub asset transfer (Northumberland, UK)
- Urban CLT (Newcastle, UK)
- Rural cooperative (Wales, UK)
- Food hub (Kenya)

**In Progress:**
- 5+ UK pilots (Q1 2025)
- 2+ Latin America projects
- 1+ Africa project

**Check back regularly for new additions!**

---

## Using the Template

**New to documenting case studies?**

1. **Read existing case studies first** (get a feel for structure)
2. **Copy the template:** `template/case-study-template.md`
3. **Fill in as you go** (don't wait until project complete)
4. **Include community voice** (quotes, feedback, testimonials)
5. **Be honest** (failures teach more than successes)
6. **Get community approval** before submitting

**Questions?**
- Review [CONTRIBUTING.md](../CONTRIBUTING.md)
- Ask in [GitHub Discussions](https://github.com/[your-username]/regenerative-development-ai/discussions)
- Email [case-studies-email]

---

## Citation

**To cite a case study:**
```

[Practitioner Name or Anonymous]. (2025). [Case Study Title]:
Regenerative Development AI Case Study. Retrieved from
https://github.com/[your-username]/regenerative-development-ai/
tree/main/case-studies/[case-name]

```

**To cite the collection:**
```

Regenerative Development AI Project. (2025). Case Studies Collection.
Retrieved from https://github.com/[your-username]/
regenerative-development-ai/tree/main/case-studies
