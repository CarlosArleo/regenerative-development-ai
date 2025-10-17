
## Getting Started

### Prerequisites

* Node.js 18+ and npm
* Firebase CLI
* Git
* Basic understanding of regenerative development (for content contributions)

### Setup Development Environment

bash

```bash
# Fork and clone
git clone https://github.com/[your-username]/regenerative-development-ai.git
cd regenerative-development-ai

# Install dependencies
cd frontend
npminstall

cd../backend/functions
npminstall

# Set up Firebase
firebase login
firebase init

# Run locally
cd../../frontend
npm run dev
```

---

## Contribution Guidelines

### Code Contributions

**Before starting:**

1. Check existing issues for similar work
2. Create an issue describing your proposed change
3. Wait for maintainer feedback
4. Fork and create a feature branch

**While coding:**

* Follow existing code style (TypeScript, ESLint)
* Write meaningful commit messages
* Add tests for new features
* Update documentation

**When submitting:**

* Create PR with clear description
* Reference related issues
* Include screenshots for UI changes
* Ensure all tests pass

### Documentation Contributions

**What we need:**

* More case studies (especially non-Western contexts)
* Better onboarding guides
* Video tutorials
* Translation to other languages
* FAQ additions

**Format:**

* Use Markdown
* Include examples
* Keep language accessible (avoid jargon where possible)
* Provide context for practitioners new to regenerative development

### Case Study Contributions

**Required elements:**

1. Complete walkthrough (all 4 stages)
2. Anonymized stakeholder data
3. Actual outputs from system
4. Practitioner reflection
5. Community feedback
6. Outcome/impact

**Template:** Use [case-studies/template/case-study-template.md](case-studies/template/case-study-template.md)

---

## Code of Conduct

### Our Pledge

This project is committed to:

* **Community sovereignty** - Communities always have final say
* **Epistemic humility** - We don't claim to have all answers
* **Anti-extraction** - No contributions that enable extractive use
* **Accessibility** - Technology should serve all, not just elites
* **Transparency** - Open processes and honest communication

### Expected Behavior

* Be respectful and inclusive
* Prioritize community benefit over technical elegance
* Listen to practitioners and community members
* Acknowledge uncertainty
* Cite sources and give credit

### Unacceptable Behavior

* Any contribution that enables bypassing community consent
* Features that extract value from communities
* Disrespect toward practitioners or communities
* Plagiarism or uncredited use of others' work
* Harassment or discrimination

---

## Review Process

### For Code PRs

1. **Automated checks** - Tests, linting, build
2. **Maintainer review** - Technical quality
3. **Ethics review** - Alignment with community sovereignty principles
4. **Practitioner review** (for major features) - Real-world utility

**Timeline:** Typically 3-7 days for initial review

### For Documentation/Case Studies

1. **Content review** - Accuracy, completeness
2. **Accessibility review** - Language, formatting
3. **Ethics review** - Community consent, anonymization
4. **Practitioner feedback** (optional)

**Timeline:** Typically 5-10 days

---

## Bug Reports

### What to Include

markdown

```markdown
**Description:** Clear, concise description of the bug

**Steps to Reproduce:**
1. Go to '...'
2. Click on '....'
3. Enter data '....'
4. See error

**Expected behavior:** What you expected to happen

**Actual behavior:** What actually happened

**Screenshots:** If applicable

**Environment:**
- Browser: [e.g., Chrome 120]
- OS: [e.g., macOS 14]
- Version: [e.g., v0.9]

**Additional context:** Anything else relevant
```

### Security Vulnerabilities

**Do NOT create public issues for security vulnerabilities.**

Email: [your-security-email]

We'll respond within 48 hours and work with you on a fix.

---

## Feature Requests

### What to Include

- **Use case:** What problem does this solve?
- **Current limitation:** What can't be done now?
- **Proposed solution:** How might this work?
- **Alternatives considered:** Other ways to solve this?
- **Community benefit:** Who benefits and how?

### Priority Considerations

Features aligned with these goals get priority:

1. Increases accessibility for under-resourced communities
2. Improves anti-capture detection
3. Supports more cultural contexts
4. Enhances practitioner effectiveness
5. Strengthens community sovereignty

---

## Documentation Standards

### File Organization

```
docs/
├── theory-guide.md         # Deep conceptual content
├── practitioner-guide.md   # Practical how-to
├── stage-X-guide.md        # Step-by-step stage guides
└── faq.md                  # Q&A format
```

### Writing Style

* **Active voice:** "Generate questions" not "Questions are generated"
* **Second person:** "You can..." not "One can..."
* **Examples:** Always include concrete examples
* **Honesty:** Acknowledge limitations and uncertainties
* **Accessibility:** Define terms, avoid unnecessary jargon

### Markdown Conventions

* Use `#` for titles, `##` for sections, `###` for subsections
* Code blocks with language: ````typescript`
* **Bold** for emphasis, *italic* for terms
* Use lists liberally for scannability
* Include table of contents for docs >2000 words

---

## Testing

### Required for Code Contributions

* [ ] All existing tests pass
* [ ] New tests added for new features
* [ ] Manual testing completed
* [ ] Edge cases considered
* [ ] Works with sample data in `examples/`

### Testing Guidelines

bash

```bash
# Run frontend tests
cd frontend
npmtest

# Run backend tests
cd backend/functions
npmtest

# Test with sample data
# Use examples/sample-stage1-input.json
```

---

## Release Process

### Versioning

We use Semantic Versioning (semver):

* **MAJOR:** Breaking changes
* **MINOR:** New features (backward compatible)
* **PATCH:** Bug fixes

### Release Checklist

* [ ] All tests pass
* [ ] Documentation updated
* [ ] CHANGELOG.md updated
* [ ] Version bumped
* [ ] Git tag created
* [ ] Release notes written

---

## Recognition

### Contributors

All contributors are acknowledged in:

* README.md contributors section
* Release notes
* Documentation (where relevant)

### Types of Recognition

* **Code contributors:** GitHub contributions graph
* **Case study authors:** Attribution in case study
* **Translators:** Language version credits
* **Practitioners:** Testimonials (with permission)

---

## Getting Help

### Questions?

* **General:** Create a Discussion on GitHub
* **Bug:** Create an Issue
* **Feature idea:** Create an Issue with `[Feature Request]` label
* **Security:** Email [security-email]
* **Partnership:** Email [contact-email]

### Response Times

* **Critical bugs:** 24-48 hours
* **General questions:** 3-7 days
* **Feature requests:** 1-2 weeks
* **PRs:** 3-7 days for initial review

---

## Contributor Checklist

Before submitting PR:

* [ ] Read and agree to Code of Conduct
* [ ] Followed contribution guidelines
* [ ] Tested changes locally
* [ ] Updated documentation (if needed)
* [ ] Added tests (for code changes)
* [ ] Used meaningful commit messages
* [ ] Referenced related issues
* [ ] Confirmed alignment with community sovereignty principles

---

## Special Thanks

To all contributors who help make regenerative development accessible to more communities!

---

**Questions about contributing?** Open a Discussion or email [contact-email]

**Thank you for contributing to community-led regenerative futures!** 🌱
`</artifact>`

---

## 4. docs/getting-started.md

<artifact identifier="getting-started-guide" type="text/markdown" title="docs/getting-started.md">
# Getting Started with Regenerative Development AI
Complete guide to installing, setting up, and running your first project.

---

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Configuration](#configuration)
4. [Your First Project](#your-first-project)
5. [Understanding the Workflow](#understanding-the-workflow)
6. [Troubleshooting](#troubleshooting)

---

## Prerequisites

### Technical Requirements

**Required:**

* Node.js 18 or higher ([Download](https://nodejs.org/))
* npm (comes with Node.js)
* Git ([Download](https://git-scm.com/))
* A Google account (for Gemini API)
* Firebase account (free tier works)

**Recommended:**

* VS Code or similar code editor
* Basic command line familiarity
* Understanding of regenerative development principles

### Knowledge Requirements

**For Practitioners:**

* Familiarity with Story of Place framework
* Community facilitation experience
* Understanding of Essential Processes

**For Developers:**

* TypeScript/JavaScript
* React/Next.js basics
* Firebase Functions
* API integration

### Check Your Setup

bash

```bash
# Verify Node.js installation
node --version
# Should show v18.0.0 or higher

# Verify npm
npm --version
# Should show 9.0.0 or higher

# Verify Git
git --version
```

---

## Installation

### Step 1: Clone the Repository

bash

```bash
# Clone from GitHub
git clone https://github.com/[your-username]/regenerative-development-ai.git

# Navigate to project
cd regenerative-development-ai
```

### Step 2: Install Frontend

bash

```bash
cd frontend

# Install dependencies
npminstall

# This will install:
# - Next.js
# - React
# - TypeScript
# - Tailwind CSS
# - Other dependencies
```

### Step 3: Install Backend

bash

```bash
cd../backend/functions

# Install dependencies
npminstall

# This will install:
# - Firebase Functions SDK
# - TypeScript
# - AI flow dependencies
# - Other dependencies
```

### Step 4: Install Firebase CLI

bash

```bash
# Install globally
npminstall -g firebase-tools

# Login to Firebase
firebase login

# This will open browser for authentication
```

---

## Configuration

### Step 1: Firebase Project Setup

bash

```bash
# From project root
cd backend

# Initialize Firebase
firebase init

# Select:
# ✓ Functions
# ✓ Firestore
# ? Use existing project or create new? Create new
# ? Project name: regenerative-dev-ai-[yourname]
# ? Language: TypeScript
# ? ESLint: Yes
# ? Install dependencies: Yes
```

### Step 2: Get Gemini API Key

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Click "Get API Key"
3. Create a new key
4. Copy the key (you'll need it in next step)

### Step 3: Configure Environment Variables

**Frontend (.env.local):**

bash

```bash
cd../frontend

# Create environment file
cat> .env.local <<EOF
NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
EOF
```

**Backend (functions/.env):**

bash

```bash
cd../backend/functions

# Create environment file
cat> .env <<EOF
GEMINI_API_KEY=your_gemini_api_key_here
EOF

# Set in Firebase (for deployed functions)
firebase functions:config:set gemini.api_key="your_gemini_api_key_here"
```

### Step 4: Initialize Firestore

bash

```bash
# From backend directory
firebase firestore:indexes

# Create initial indexes (if prompted)
```

---

## Your First Project

### Step 1: Start Development Server

bash

```bash
# Start frontend
cd frontend
npm run dev

# Server starts at http://localhost:3000
```

### Step 2: Load Sample Data

**Option A: Use Carrington Moss Example**

Navigate to `http://localhost:3000` and enter:

**Project Name:** `Carrington Moss Alternative Vision`

**Location:** `Carrington, Greater Manchester`

**Tensions:** `6500 home development on green belt, peatland destruction`

**Historical Patterns:** `peatland commons, local food production`

**Bioregion:** `Greater Manchester Wetlands`

**Stakeholders:** Select `long_term_residents`, `environmental_groups`, `local_farmers`

**Option B: Load from File**

bash

```bash
# Copy sample data
cp examples/sample-stage1-input.json /tmp/test-input.json

# Manually copy values into the form
```

### Step 3: Run Stage 1

1. Click **"Run Stage 1: Generate Inquiry Questions"**
2. Wait for processing (1-2 minutes)
3. Review generated questions
4. Download or copy questions for workshops

**Expected Output:**

* 15-20 questions per stakeholder group
* Complete workshop protocol
* Facilitation guidance
* Materials list

### Step 4: Simulate Stage 2

For testing without real workshops:

bash

```bash
# Use sample responses
cp examples/sample-stage2-input.json /tmp/stage2-test.json
```

Enter sample responses in Stage 2 form:

**Elder Responses:**

```
We used to gather on the moss for community events
The peatland provided us with fuel and food
Young people don't understand its value anymore
```

**Environmental Group Responses:**

```
The moss stores massive amounts of carbon
Rare species depend on this habitat
Development would be irreversible damage
```

Click **"Run Stage 2: Process Responses"**

**Expected Output:**

- Essential Processes health assessment
- Refined place essence
- Priority intervention identified
- Confidence level and next steps

### Step 5: Continue Through Stages

- **Stage 3:** Generate design brief
- **Stage 4:** Test governance pathways with VDK

---

## Understanding the Workflow

### The Four-Stage Process

```
Stage 1: Generate Questions
    ↓ (Conduct Workshops)
Stage 2: Synthesize Responses
    ↓ (Validate with Community)
Stage 3: Create Design Brief
    ↓ (Work with Designers)
Stage 4: Test Governance
    ↓ (Choose Pathway)
Implementation
```

### Time Estimates

| Stage   | AI Processing | Human Work                              | Total    |
| ------- | ------------- | --------------------------------------- | -------- |
| Stage 1 | 2 min         | 2-3 weeks (workshop planning + conduct) | ~3 weeks |
| Stage 2 | 2 min         | 2 hours (data entry + validation)       | ~1 day   |
| Stage 3 | 3 min         | 1 day (review + adaptation)             | ~2 days  |
| Stage 4 | 10 min        | 1 day (document gathering + review)     | ~2 days  |

**Traditional consulting:** 4-8 months, £50k-£200k
**With this system:** 5-7 weeks, £0 (pilot) to £500-2000 (future pricing)

### Data Flow

```
Community Input (workshops, documents)
    ↓
Frontend (data entry, visualization)
    ↓
Firebase Functions (API layer)
    ↓
AI Flows (processing logic)
    ↓
Gemini API (AI generation)
    ↓
VDK (capture detection, validation)
    ↓
Outputs (questions, assessments, briefs, pathways)
    ↓
Community Review & Decision
```

---

## Troubleshooting

### Common Issues

#### Frontend won't start

bash

```bash
# Clear cache and reinstall
cd frontend
rm -rf node_modules package-lock.json
npminstall
npm run dev
```

#### "API key not found" error

bash

```bash
# Check environment variables are set
cat frontend/.env.local
cat backend/functions/.env

# Ensure no extra spaces or quotes
# Format: KEY=value (no quotes)
```

#### Firebase deployment fails

bash

```bash
# Check Firebase login
firebase login --reauth

# Check project is selected
firebase use --add

# Deploy with verbose logging
firebase deploy --only functions --debug
```

#### Gemini API errors

**Error: "API key invalid"**

* Verify key in Google AI Studio
* Check for copy-paste errors
* Ensure no extra spaces

**Error: "Rate limit exceeded"**

* Free tier: 60 requests/minute
* Wait a minute and retry
* Consider upgrading plan

**Error: "Model not found"**

* Check model name: `gemini-2.5-pro-latest`
* Verify API access in Google AI Studio

#### Stage 1 generates poor questions

**Issue:** Questions feel generic or inappropriate

**Solutions:**

* Add more context in "tensions" and "historical patterns"
* Be specific about place characteristics
* Include cultural context
* Try running again with refined inputs
* Manually adapt generated questions

#### Stage 2 confidence is LOW

**Issue:** "Need more inquiry" message

**Solutions:**

* Add more stakeholder responses
* Include more diverse perspectives
* Provide richer detail in responses
* Consider conducting additional workshops
* Don't proceed to Stage 3 if confidence is low

#### VDK rejects all pathways (Stage 4)

**Issue:** No governance pathways validated

**Solutions:**

* Review uploaded governance documents
* Check constitution selection
* Verify community design brief is clear
* Try different constitutional framework
* May indicate fundamental misalignment (good catch!)

---

## Next Steps

### Learn the System

* [ ] Read [Practitioner Guide](practitioner-guide.md)
* [ ] Study [Carrington Moss Case Study](../case-studies/carrington-moss/)
* [ ] Review [Stage Guides](stage-1-guide.md)
* [ ] Understand [VDK](stage-4-vdk-guide.md)

### Test with Real Data

* [ ] Plan community workshops
* [ ] Generate Stage 1 questions
* [ ] Conduct engagement
* [ ] Process through all stages

### Connect with Community

* [ ] Join GitHub Discussions
* [ ] Share feedback
* [ ] Report bugs or issues
* [ ] Consider contributing case study

---

## Getting Help

### Resources

* **Documentation:** [docs/](.)
* **FAQ:** [faq.md](faq.md)
* **Case Studies:** [case-studies/](../case-studies/)
* **Issues:** [GitHub Issues](https://github.com/%5Byour-username%5D/regenerative-development-ai/issues)

### Support Channels

* **Technical issues:** Create GitHub Issue
* **Practitioner questions:** GitHub Discussions
* **Partnership inquiries:** [your-email]

---

## Checklist: Ready to Use?

* [ ] Installation complete (frontend + backend)
* [ ] Firebase project configured
* [ ] Gemini API key set
* [ ] Environment variables configured
* [ ] Development server running
* [ ] Tested with sample data
* [ ] Reviewed stage guides
* [ ] Understood workflow

**If all checked: You're ready to support your first community project!**
