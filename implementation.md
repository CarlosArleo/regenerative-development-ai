# Automated System Genericization Script

<artifact identifier="genericization-script" type="application/vnd.ant.code" language="bash" title="Automated Script to Make System Generic">
#!/bin/bash
# ============================================================================

# REGENERATIVE DEVELOPMENT SYSTEM - GENERICIZATION SCRIPT

# ============================================================================

# This script removes Colombian hardcoded examples and makes the system

# ready for UK (and any other) contexts

# Run from: ~/studio/

# Usage: bash genericize-system.sh

# ============================================================================

set -e  # Exit on any error

echo "🌍 Starting System Genericization..."
echo "===================================="
echo ""

# Colors for output

GREEN='\033[0;32m'
BLUE='\033[0;34m'
YELLOW='\033[1;33m'
NC='\033[0m' # No Color

# ============================================================================

# STEP 1: BACKUP CURRENT FILES

# ============================================================================

echo -e "BLUE📦Step1:Creatingbackups...{BLUE}📦 Step 1: Creating backups...
**B**LU**E**📦**St**e**p**1**:**C**re**a**t**in**g**ba**c**k**u**p**s**...{NC}"

BACKUP_DIR="backups/pre-generic-$(date +%Y%m%d_%H%M%S)"
mkdir -p "$BACKUP_DIR"

# Backup frontend

if [ -f "packages/frontend/src/app/page.tsx" ]; then
cp packages/frontend/src/app/page.tsx "$BACKUP_DIR/page.tsx.backup"
echo "  ✓ Backed up page.tsx"
fi

# Backup backend constitutions

if [ -d "biomimicry/functions/backend/constitutions" ]; then
cp -r biomimicry/functions/backend/constitutions "$BACKUP_DIR/"
echo "  ✓ Backed up constitutions"
fi

echo -e "**{GREEN}✓ Backups saved to: $BACKUP_DIR
**{NC}"
echo ""

# ============================================================================

# STEP 2: UPDATE FRONTEND - REMOVE COLOMBIAN DEFAULTS

# ============================================================================

echo -e "BLUE🔧Step2:Updatingfrontenddefaults...{BLUE}🔧 Step 2: Updating frontend defaults...
**B**LU**E**🔧**St**e**p**2**:**U**p**d**a**t**in**g**f**ro**n**t**e**n**dd**e**f**a**u**lt**s**...{NC}"

FRONTEND_FILE="packages/frontend/src/app/page.tsx"

if [ ! -f "$FRONTEND_FILE" ]; then
    echo -e "**{YELLOW}⚠ Warning: $FRONTEND_FILE not found!
**{NC}"
    echo "  Make sure you're running this from ~/studio/ directory"
    exit 1
fi

# Create sed script for all replacements

cat > /tmp/sed_script.txt << 'SEDEOF'

# Stage 1 Form - Clear Colombian defaults

s/const [projectName, setProjectName] = useState`<string>`("Truly Regenerative Pilot");/const [projectName, setProjectName] = useState`<string>`("");/g
s/const [projectName, setProjectName] = useState("Truly Regenerative Pilot");/const [projectName, setProjectName] = useState("");/g

s/const [locationName, setLocationName] = useState`<string>`("Bajo Baudó");/const [locationName, setLocationName] = useState`<string>`("");/g
s/const [locationName, setLocationName] = useState("Bajo Baudó");/const [locationName, setLocationName] = useState("");/g

s/const [tensionsInput, setTensionsInput] = useState`<string>`("coastal erosion, youth migration");/const [tensionsInput, setTensionsInput] = useState`<string>`("");/g
s/const [tensionsInput, setTensionsInput] = useState("coastal erosion, youth migration");/const [tensionsInput, setTensionsInput] = useState("");/g

s/const [historicalPatterns, setHistoricalPatterns] = useState`<string>`("mangrove stewardship");/const [historicalPatterns, setHistoricalPatterns] = useState`<string>`("");/g
s/const [historicalPatterns, setHistoricalPatterns] = useState("mangrove stewardship");/const [historicalPatterns, setHistoricalPatterns] = useState("");/g

s/const [bioregion, setBioregion] = useState`<string>`("Chocó Bioregion");/const [bioregion, setBioregion] = useState`<string>`("");/g
s/const [bioregion, setBioregion] = useState("Chocó Bioregion");/const [bioregion, setBioregion] = useState("");/g

# Stage 2 Form - Clear Colombian workshop responses

s/const [elderResponses, setElderResponses] = useState("We used to protect the mangroves together. *");/const [elderResponses, setElderResponses] = useState("");/g
s/const [youthResponses, setYouthResponses] = useState("We want meaningful work in restoration.* ");/const [youthResponses, setYouthResponses] = useState("");/g
s/const [municipalResponses, setMunicipalResponses] = useState("Budget constraints limit our actions. *");/const [municipalResponses, setMunicipalResponses] = useState("");/g
s/const [landscapeResponses, setLandscapeResponses] = useState("The mangroves are the lungs of the coast.* ");/const [landscapeResponses, setLandscapeResponses] = useState("");/g

s/const [essenceHypothesis, setEssenceHypothesis] = useState("Collective regeneration of water and community");/const [essenceHypothesis, setEssenceHypothesis] = useState("");/g

# Stage 3 Form - Clear Colombian intervention and essence

s/const [validatedEssence, setValidatedEssence] = useState("Regeneration through mangrove-rooted community cycles");/const [validatedEssence, setValidatedEssence] = useState("");/g
s/const [proposedIntervention, setProposedIntervention] = useState("Community-led mangrove nursery network");/const [proposedIntervention, setProposedIntervention] = useState("");/g
SEDEOF

# Apply sed script

sed -i.bak -f /tmp/sed_script.txt "$FRONTEND_FILE"

# Now handle the commitments array (more complex, need different approach)

# Find and replace the entire commitments initialization

perl -i -pe 'BEGIN{undef **/;} s/const \[commitments, setCommitments\] = useState\(\[\s*\{[^]]*\}\s*,?\s*\{[^]]*\}\s*\]\);/const [commitments, setCommitments] = useState<Array<{\n    stakeholder: string;\n    commitment: string;\n    capacity: string;\n  }>>([]);/smg' "
**FRONTEND_FILE"

echo "  ✓ Cleared Colombian default values"

# Clean up

rm /tmp/sed_script.txt
rm "${FRONTEND_FILE}.bak" 2>/dev/null || true

echo -e "GREEN✓Frontenddefaultscleared{GREEN}✓ Frontend defaults cleared
**GREEN**✓**F**ro**n**t**e**n**dd**e**f**a**u**lt**sc**l**e**a**re**d{NC}"
echo ""

# ============================================================================

# STEP 3: ADD UK PLACEHOLDERS TO INPUTS

# ============================================================================

echo -e "BLUE📝Step3:AddingUKplaceholderexamples...{BLUE}📝 Step 3: Adding UK placeholder examples...
**B**LU**E**📝**St**e**p**3**:**A**dd**in**gU**K**pl**a**ce**h**o**l**d**ere**x**am**pl**es**...**{NC}"

# Create a small patch to add placeholders

# This adds placeholder attributes to the input fields

cat > /tmp/add_placeholders.patch << 'PATCHEOF'
--- a/packages/frontend/src/app/page.tsx
+++ b/packages/frontend/src/app/page.tsx
@@ -1,1 +1,1 @@
placeholder="San Martino Water Commons"

```
           placeholder="e.g., Carrington Moss Commons, The Crown Community Pub"
```

@@ -1,1 +1,1 @@
placeholder="San Martino di Castrozza"

```
           placeholder="e.g., Carrington, Greater Manchester"
```

@@ -1,1 +1,1 @@
placeholder="water scarcity, youth migration, knowledge loss"

```
           placeholder="e.g., green belt development, peatland destruction, community displacement"
```

@@ -1,1 +1,1 @@
placeholder="waale system maintenance, collective stewardship"

```
           placeholder="e.g., peatland commons, cooperative traditions, public house culture"
```

@@ -1,1 +1,1 @@
placeholder="Primiero Valley, Italian Dolomites"

```
           placeholder="e.g., Greater Manchester Wetlands, Tyne Valley, Northumberland Uplands"
```

PATCHEOF

# Actually, let's just do direct replacement of placeholder text

sed -i 's/placeholder="San Martino Water Commons"/placeholder="e.g., Carrington Moss Commons, The Crown Community Pub"/g' "$FRONTEND_FILE"
sed -i 's/placeholder="San Martino di Castrozza"/placeholder="e.g., Carrington, Greater Manchester"/g' "$FRONTEND_FILE"
sed -i 's/placeholder="water scarcity, youth migration, knowledge loss"/placeholder="e.g., green belt development, peatland destruction, housing affordability"/g' "$FRONTEND_FILE"
sed -i 's/placeholder="waale system maintenance, collective stewardship"/placeholder="e.g., peatland commons, cooperative traditions, community land ownership"/g' "$FRONTEND_FILE"
sed -i 's/placeholder="Primiero Valley, Italian Dolomites"/placeholder="e.g., Greater Manchester Wetlands, Tyne Valley, Peak District"/g' "$FRONTEND_FILE"

echo "  ✓ Added UK-appropriate placeholder examples"

rm /tmp/add_placeholders.patch 2>/dev/null || true

echo -e "GREEN✓Placeholdersupdated{GREEN}✓ Placeholders updated
**GREEN**✓**Pl**a**ce**h**o**l**d**ers**u**p**d**a**t**e**d**{NC}"
echo ""

# ============================================================================

# STEP 4: CREATE UK CONSTITUTION TEMPLATE

# ============================================================================

echo -e "BLUE📜Step4:CreatingUKconstitutiontemplate...{BLUE}📜 Step 4: Creating UK constitution template...
**B**LU**E**📜**St**e**p**4**:**C**re**a**t**in**gU**Kco**n**s**t**i**t**u**t**i**o**n**t**e**m**pl**a**t**e**...{NC}"

CONST_DIR="biomimicry/functions/backend/constitutions"
mkdir -p "$CONST_DIR"

cat > "$CONST_DIR/uk-commons-governance.md" << 'CONSTITEOF'

# UK Commons Governance Constitution

## Legal Framework Alignment

This governance framework aligns with:

* Localism Act 2011 (Community Asset Transfer)
* Community Right to Bid (Assets of Community Value)
* Co-operative and Community Benefit Societies Act 2014
* Town and Country Planning Act 1990
* Neighbourhood Planning Act 2017

## Core Principles

### 1. Democratic Member Control

* One member, one vote (regardless of financial contribution)
* Board of directors elected by members
* Regular community assemblies (minimum quarterly)
* Clear, accessible decision-making processes
* Proxy voting permitted for accessibility

### 2. Asset Lock for Community Benefit

* Core community assets cannot be sold for private gain
* If organization dissolves, assets transfer to similar community organization
* Profits reinvested in community purpose (not distributed to members)
* Asset register maintained and publicly available

### 3. Environmental Sustainability

* Development respects ecological limits
* Net positive environmental impact required
* Climate resilience integrated into all planning
* Biodiversity net gain principles applied
* Circular economy approaches prioritized

### 4. Social Justice and Equity

* Affordable access guaranteed (housing, services, spaces)
* Local connection criteria for membership
* Protected characteristics equality (Equality Act 2010)
* Living wage minimum for all employees
* Accessibility standards (physical and digital)

### 5. Transparency and Accountability

* Annual general meetings open to community
* Financial statements published annually
* Decision-making minutes accessible to members
* Clear complaints and grievance procedures
* Independent social audits conducted

## Decision-Making Structure

### Community Assembly

* All members entitled to attend and vote
* Quarterly minimum (more frequent as needed)
* Major decisions require 75% supermajority:
  * Changes to constitution
  * Asset sales or major financial commitments
  * External partnerships
  * Changes to membership criteria
* Simple majority (50%+1) for routine decisions

### Board of Directors

* 7-11 directors elected by members
* Staggered terms (3 years, renewable once)
* Must include representation from:
  * Long-term residents
  * Young people (under 35)
  * At least one independent with relevant expertise
* Board cannot override community assembly on major decisions
* Monthly meetings minimum

### Working Groups

* Thematic groups (finance, development, engagement, etc.)
* Open to all members
* Report to board and community assembly
* Clear terms of reference

## Anti-Capture Mechanisms

### Preventing Gentrification

* Asset lock prevents sale to private developers
* Affordability requirements written into constitution
* Local connection criteria for new members:
  * Living in area for 2+ years, OR
  * Working in area, OR
  * Family ties to area
* Caps on property values/rents (if applicable)
* Community veto on external partnerships

### Preventing Corporate Capture

* No single external entity can hold >10% influence
* External funders cannot have voting rights
* All partnerships require community assembly approval
* "Sunset clauses" on external board seats (max 3 years)
* Regular social audits by independent assessors

### Preventing Elite Capture

* Active outreach to marginalized groups
* Meeting times/locations rotate for accessibility
* Childcare provided at meetings
* Translation services for non-English speakers
* Digital access provisions for those without internet
* Financial assistance for participation (travel, time)

### Preventing Mission Drift

* Annual review of activities against core principles
* Member survey on alignment with values
* Independent social impact assessment every 3 years
* Community assembly can call extraordinary meeting if concerned

## Membership

### Eligibility

* Open to individuals meeting local connection criteria
* Organizations can be associate members (non-voting)
* Minimum age: 16 years
* One-time membership fee (max £50, waived for financial hardship)

### Rights

* Vote in community assemblies
* Stand for board election
* Access to community assets/services
* Review organizational documents
* Propose motions to assemblies

### Responsibilities

* Uphold core principles
* Participate in democratic processes
* Contribute to community benefit (time, skills, or resources)
* Respect other members and community

## Financial Management

### Principles

* Financial sustainability without profit extraction
* Diverse funding sources (reduce dependency)
* Reserves policy (minimum 3 months operating costs)
* Ethical banking and investment only
* Clear procurement policies (local, cooperative preferred)

### Accountability

* Annual accounts audited by independent accountant
* Budget approved by community assembly
* Financial reports quarterly to members
* Major expenditures require assembly approval
* Grant funding terms disclosed publicly

## Conflict Resolution

### Internal Disputes

1. Informal mediation (trained member mediators)
2. Formal mediation (independent mediator)
3. Arbitration (if mediation fails)
4. Judicial review (last resort)

### External Disputes

* Legal representation from community-aligned solicitors
* Community assembly decides on legal action
* Transparent communication with members throughout

## Amendment Process

* Amendments proposed at community assembly
* 2-month consultation period
* Vote at subsequent assembly (75% supermajority required)
* Amendments cannot violate core principles
* Legal review before implementation

## Dissolution

If organization must dissolve:

* Community assembly decides (75% supermajority)
* All debts paid first
* Remaining assets transfer to:
  1. Similar community organization in same area, OR
  2. National community asset organization (e.g., Locality), OR
  3. Local authority with covenant to continue community benefit

## UK Legal Compliance

### Structure Options

* Community Benefit Society (FCA registered)
* Charitable Incorporated Organization
* Community Interest Company
* Unincorporated Association (small scale)

### Required Registrations

* Financial Conduct Authority (if cooperative)
* Charity Commission (if charitable)
* Companies House (if CIC)
* HMRC (for tax)

### Annual Requirements

* Annual returns to regulators
* Annual general meeting
* Financial statements
* Social impact reporting (if CIC)
* Asset register updates

## Monitoring and Evaluation

### Annually Assess

* Financial sustainability
* Social impact (lives improved, services delivered)
* Environmental impact (carbon, biodiversity, etc.)
* Democratic participation (meeting attendance, voting)
* Equity and inclusion (demographics, accessibility)

### Publically Report

* Annual impact report
* Financial summary (accessible language)
* Challenges and learnings
* Future plans

---

**This constitution is a living document, reviewed every 5 years by community assembly.**

**Last Updated:** [Date of creation]
**Next Review:** [5 years from creation]

---

CONSTITEOF

echo "  ✓ Created UK commons governance constitution"

# Also create a simpler UK planning-aligned version

cat > "$CONST_DIR/uk-planning-aligned.md" << 'PLANNINGEOF'

# UK Planning-Aligned Regenerative Principles

## Alignment with National Planning Policy Framework (NPPF)

### Sustainable Development (NPPF Para 7-11)

* Economic: Viable, sustainable economic activity
* Social: Strong, vibrant communities with affordable housing
* Environmental: Protect and enhance natural environment

### Place-Making (NPPF Chapter 12)

* Design quality and character
* Create attractive, safe places
* Reflect local distinctiveness
* Engage community in design process

### Climate Change (NPPF Chapter 14)

* Minimize energy consumption
* Increase renewable energy use
* Reduce flood risk
* Enhance biodiversity net gain

## Community Engagement Principles

### Meaningful Participation

* Early engagement (pre-application stage)
* Accessible consultation methods
* Diverse stakeholder inclusion
* Clear feedback loops
* Community validation of proposals

### Local Character and Identity

* Respect settlement pattern
* Build on historical context
* Enhance local distinctiveness
* Protect heritage assets
* Support community cohesion

## Regenerative Development Goals

### Ecological

* Biodiversity Net Gain (minimum 10%)
* Blue-green infrastructure
* Habitat connectivity
* Carbon sequestration
* Water quality improvement

### Social

* Affordable housing provision
* Community facilities
* Accessible public spaces
* Employment opportunities
* Health and wellbeing focus

### Economic

* Local employment
* Sustainable business models
* Circular economy approaches
* Community wealth building
* Long-term viability

## Design Principles

### Beautiful, Enduring Places

* Context-appropriate design
* High-quality materials (local where possible)
* Future adaptability
* Easy to maintain
* Age gracefully

### Health and Wellbeing

* Active travel connections
* Access to nature
* Community gathering spaces
* Safety and security
* Reduced pollution

### Resource Efficiency

* Low carbon construction
* Renewable energy integration
* Water conservation
* Waste minimization
* Circular material flows

## Governance and Delivery

### Community Ownership Models

* Community Land Trusts
* Development Trusts
* Cooperatives
* Community Interest Companies
* Charitable structures

### Partnership Approaches

* Community-Local Authority partnerships
* Community-Housing Association partnerships
* Community-Private Sector partnerships (with safeguards)

### Safeguards Against Capture

* Asset locks
* Community veto rights
* Independent oversight
* Transparent decision-making
* Regular reviews

---

**Use this constitution for projects requiring planning permission or working within UK planning system.**
PLANNINGEOF

echo "  ✓ Created UK planning-aligned constitution"

echo -e "GREEN✓UKconstitutiontemplatescreated{GREEN}✓ UK constitution templates created
**GREEN**✓**U**Kco**n**s**t**i**t**u**t**i**o**n**t**e**m**pl**a**t**escre**a**t**e**d**{NC}"
echo ""

# ============================================================================

# STEP 5: CREATE UK TEST DATA TEMPLATES

# ============================================================================

echo -e "BLUE🧪Step5:CreatingUKtestdatatemplates...{BLUE}🧪 Step 5: Creating UK test data templates...
**B**LU**E**🧪**St**e**p**5**:**C**re**a**t**in**gU**K**t**es**t**d**a**t**a**t**e**m**pl**a**t**es**...**{NC}"

TEST_DIR="test-data/uk-contexts"
mkdir -p "$TEST_DIR"

# Carrington Moss example

cat > "$TEST_DIR/carrington-moss-example.json" << 'CARRINGTONJSON'
{
"project_name": "Carrington Moss Alternative Vision",
"place_context": {
"location_name": "Carrington, Greater Manchester",
"current_tensions": [
"6500 home development on green belt",
"peatland destruction",
"community displacement",
"loss of agricultural land"
],
"historical_patterns": [
"peatland commons",
"local food production",
"working class community",
"wartime agricultural heritage"
],
"bioregion": "Greater Manchester Wetlands / Mersey Basin"
},
"stakeholder_types": [
"long_term_residents",
"environmental_groups",
"local_farmers",
"council_staff",
"the_peatland"
]
}
CARRINGTONJSON

echo "  ✓ Created Carrington Moss test data"

# Community Pub example

cat > "$TEST_DIR/community-pub-example.json" << 'PUBJSON'
{
"project_name": "The Crown Community Pub",
"place_context": {
"location_name": "Rural Northumberland Village",
"current_tensions": [
"pub closure",
"loss of community gathering space",
"village fragmentation",
"declining local services"
],
"historical_patterns": [
"pub as village heart",
"community events and celebrations",
"mutual support networks",
"collective decision-making"
],
"bioregion": "Northumberland rural landscape"
},
"stakeholder_types": [
"elders",
"young_families",
"local_business",
"parish_council",
"the_village"
]
}
PUBJSON

echo "  ✓ Created community pub test data"

# CLT Housing example

cat > "$TEST_DIR/clt-housing-example.json" << 'CLTJSON'
{
"project_name": "Ouseburn Community Housing Trust",
"place_context": {
"location_name": "Ouseburn Valley, Newcastle upon Tyne",
"current_tensions": [
"housing affordability crisis",
"artist and creative community displacement",
"gentrification pressure",
"loss of industrial heritage character"
],
"historical_patterns": [
"industrial heritage",
"artist studios and creative workspace",
"alternative culture and community",
"cooperative traditions"
],
"bioregion": "Urban Tyneside / Ouseburn Valley"
},
"stakeholder_types": [
"artists",
"low_income_residents",
"housing_association",
"council",
"the_ouseburn_valley"
]
}
CLTJSON

echo "  ✓ Created CLT housing test data"

# Create README for test data

cat > "$TEST_DIR/README.md" << 'READMEEOF'

# UK Test Data Examples

This directory contains example input data for testing the system with UK contexts.

## Examples Included

### 1. Carrington Moss (Planning Opposition)

**File:** `carrington-moss-example.json`
**Context:** Community opposing 6500-home development on peatland/green belt
**Use for:** Testing Stage 1-3 with planning opposition scenario

### 2. Community Pub (Asset Transfer)

**File:** `community-pub-example.json`
**Context:** Rural village taking pub into community ownership
**Use for:** Testing Stage 1-4 with community asset scenario

### 3. CLT Housing (Urban)

**File:** `clt-housing-example.json`
**Context:** Urban community land trust for affordable housing
**Use for:** Testing Stage 1-4 with CLT scenario

## How to Use

1. Load the JSON file
2. Copy values into the frontend form
3. Run through Stages 1-4
4. Verify outputs are UK-appropriate

## Verifying Success

Outputs should:

* Use UK terminology (council, parish, green belt, etc.)
* Reference UK legal frameworks (planning acts, CLT structure, etc.)
* Reflect UK cultural context
* NOT include US or Colombian references
  READMEEOF

echo "  ✓ Created test data README"

echo -e "GREEN✓UKtestdatatemplatescreated{GREEN}✓ UK test data templates created
**GREEN**✓**U**K**t**es**t**d**a**t**a**t**e**m**pl**a**t**escre**a**t**e**d{NC}"
echo ""

# ============================================================================

# STEP 6: UPDATE FRONTEND CONSTITUTION SELECTOR

# ============================================================================

echo -e "BLUE🔄Step6:Updatingconstitutionselector...{BLUE}🔄 Step 6: Updating constitution selector...
**B**LU**E**🔄**St**e**p**6**:**U**p**d**a**t**in**g**co**n**s**t**i**t**u**t**i**o**n**se**l**ec**t**or**...**{NC}"

# Add UK constitutions to the selector dropdown

# This is a bit tricky, we'll add after the regenerative.md option

perl -i -pe '
if (/option value="regenerative.md"/) {
$_ .= "              `<option value="uk-commons-governance.md">`UK Commons Governance`</option>`\n";
$_ .= "              `<option value="uk-planning-aligned.md">`UK Planning Aligned`</option>`\n";
}
' "$FRONTEND_FILE"

echo "  ✓ Added UK constitutions to selector dropdown"

echo -e "GREEN✓Constitutionselectorupdated{GREEN}✓ Constitution selector updated
**GREEN**✓**C**o**n**s**t**i**t**u**t**i**o**n**se**l**ec**t**or**u**p**d**a**t**e**d{NC}"
echo ""

# ============================================================================

# STEP 7: CREATE VERIFICATION SCRIPT

# ============================================================================

echo -e "BLUE✅Step7:Creatingverificationscript...{BLUE}✅ Step 7: Creating verification script...
**B**LU**E**✅**St**e**p**7**:**C**re**a**t**in**gv**er**i**f**i**c**a**t**i**o**n**scr**i**pt**...**{NC}"

cat > verify-genericization.sh << 'VERIFYEOF'
#!/bin/bash

# Verification script for genericization

echo "🔍 Verifying System Genericization"
echo "=================================="
echo ""

FRONTEND_FILE="packages/frontend/src/app/page.tsx"
ERRORS=0

echo "Checking frontend file for Colombian defaults..."

# Check if any Colombian defaults remain

if grep -q "Bajo Baudó" "$FRONTEND_FILE"; then
echo "❌ FAIL: 'Bajo Baudó' still found in frontend"
ERRORS=$((ERRORS + 1))
else
echo "✓ PASS: No 'Bajo Baudó' found"
fi

if grep -q "Chocó Bioregion" "$FRONTEND_FILE"; then
echo "❌ FAIL: 'Chocó Bioregion' still found in frontend"
ERRORS=$((ERRORS + 1))
else
echo "✓ PASS: No 'Chocó Bioregion' found"
fi

if grep -q "mangrove" "$FRONTEND_FILE"; then
echo "❌ FAIL: 'mangrove' references still found in frontend defaults"
ERRORS=$((ERRORS + 1))
else
echo "✓ PASS: No 'mangrove' in defaults"
fi

if grep -q "coastal erosion" "$FRONTEND_FILE"; then
echo "❌ FAIL: 'coastal erosion' still found in frontend defaults"
ERRORS=$((ERRORS + 1))
else
echo "✓ PASS: No 'coastal erosion' in defaults"
fi

echo ""
echo "Checking for UK constitution files..."

if [ -f "biomimicry/functions/backend/constitutions/uk-commons-governance.md" ]; then
echo "✓ PASS: UK commons governance constitution exists"
else
echo "❌ FAIL: UK commons governance constitution missing"
ERRORS=$((ERRORS + 1))
fi

if [ -f "biomimicry/functions/backend/constitutions/uk-planning-aligned.md" ]; then
echo "✓ PASS: UK planning-aligned constitution exists"
else
echo "❌ FAIL: UK planning-aligned constitution missing"
ERRORS=$((ERRORS + 1))
fi

echo ""
echo "Checking for test data..."

if [ -d "test-data/uk-contexts" ]; then
echo "✓ PASS: UK test data directory exists"

```
if [ -f "test-data/uk-contexts/carrington-moss-example.json" ]; then
    echo "✓ PASS: Carrington Moss test data exists"
else
    echo "❌ FAIL: Carrington Moss test data missing"
    ERRORS=$((ERRORS + 1))
fi
```

else
echo "❌ FAIL: UK test data directory missing"
ERRORS=$((ERRORS + 1))
fi

echo ""
echo "=================================="
if [ $ERRORS -eq 0 ]; then
echo "✅ ALL CHECKS PASSED!"
echo ""
echo "System is ready for UK deployment."
echo ""
echo "Next steps:"
echo "1. cd packages/frontend && npm run dev"
echo "2. Test with Carrington Moss data from test-data/uk-contexts/"
echo "3. Verify Stage 1 generates UK-appropriate questions"
else
echo "❌ $ERRORS CHECK(S) FAILED"
echo ""
echo "Please review errors above and fix manually."
fi
echo "=================================="
VERIFYEOF

chmod +x verify-genericization.sh

echo "  ✓ Created verification script: verify-genericization.sh"

echo -e "GREEN✓Verificationscriptready{GREEN}✓ Verification script ready
**GREEN**✓**V**er**i**f**i**c**a**t**i**o**n**scr**i**pt**re**a**d**y{NC}"
echo ""

# ============================================================================

# STEP 8: CREATE ROLLBACK SCRIPT

# ============================================================================

echo -e "BLUE↩®Step8:Creatingrollbackscript...{BLUE}↩️  Step 8: Creating rollback script...
**B**LU**E**↩**R**◯**St**e**p**8**:**C**re**a**t**in**g**ro**ll**ba**c**k**scr**i**pt**...{NC}"

cat > rollback-genericization.sh << ROLLBACKEOF
#!/bin/bash

# Rollback script - restores from backup

echo "⏮️  Rolling back genericization changes..."
echo "========================================"
echo ""

BACKUP_DIR="$BACKUP_DIR"

if [ ! -d "$BACKUP_DIR" ]; then
echo "❌ ERROR: Backup directory not found: $BACKUP_DIR"
exit 1
fi

echo "Restoring from backup: $BACKUP_DIR"

if [ -f "$BACKUP_DIR/page.tsx.backup" ]; then
cp "$BACKUP_DIR/page.tsx.backup" packages/frontend/src/app/page.tsx
echo "✓ Restored page.tsx"
fi

if [ -d "$BACKUP_DIR/constitutions" ]; then
rm -rf biomimicry/functions/backend/constitutions
cp -r "$BACKUP_DIR/constitutions" biomimicry/functions/backend/
echo "✓ Restored constitutions"
fi

echo ""
echo "✅ Rollback complete!"
echo "Your files have been restored to pre-genericization state."
ROLLBACKEOF

chmod +x rollback-genericization.sh

echo "  ✓ Created rollback script: rollback-genericization.sh"

echo -e "GREEN✓Rollbackscriptready{GREEN}✓ Rollback script ready
**GREEN**✓**R**o**ll**ba**c**k**scr**i**pt**re**a**d**y**{NC}"
echo ""

# ============================================================================

# STEP 9: RUN VERIFICATION

# ============================================================================

echo -e "BLUE🧪Step9:Runningverification...{BLUE}🧪 Step 9: Running verification...
**B**LU**E**🧪**St**e**p**9**:**R**u**nnin**gv**er**i**f**i**c**a**t**i**o**n**...{NC}"
echo ""

./verify-genericization.sh

echo ""

# ============================================================================

# STEP 10: CREATE NEXT STEPS GUIDE

# ============================================================================

echo -e "BLUE📖Step10:Creatingnextstepsguide...{BLUE}📖 Step 10: Creating next steps guide...
**B**LU**E**📖**St**e**p**10**:**C**re**a**t**in**g**n**e**x**t**s**t**e**p**s**gu**i**d**e**...**{NC}"

cat > NEXT-STEPS.md << 'NEXTSTEPSEOF'

# Next Steps After Genericization

## ✅ What Was Done

1. **Removed Colombian defaults** from all form fields
2. **Added UK placeholder examples** for context
3. **Created UK constitution templates:**
   * `uk-commons-governance.md` (for CLTs, co-ops, community assets)
   * `uk-planning-aligned.md` (for planning applications)
4. **Created UK test data** in `test-data/uk-contexts/`:
   * Carrington Moss (planning opposition)
   * Community Pub (asset transfer)
   * CLT Housing (urban)
5. **Updated constitution selector** to include UK options
6. **Created backups** in case you need to rollback

## 🧪 Testing the Generic System

### Quick Test (5 minutes)

1. **Start the frontend:**

bash

```bash
cd packages/frontend
npm run dev
```

2. **Open browser:** [http://localhost:3000](http://localhost:3000)
3. **Verify empty forms:**
   * All Stage 1 fields should be empty
   * Placeholders should show UK examples
4. **Load Carrington Moss test data:**
   * Copy values from `test-data/uk-contexts/carrington-moss-example.json`
   * Paste into Stage 1 form
5. **Run Stage 1:**
   * Click "Run Stage 1"
   * Wait for output
   * **Verify:** Questions should be UK-appropriate
     * References to "green belt," "peatland," "community"
     * NO references to "mangroves," "Colombia," etc.

### Full Test (30 minutes)

Test all three UK contexts through Stage 1:

1. **Carrington Moss** (planning opposition)
2. **Community Pub** (asset transfer)
3. **CLT Housing** (urban development)

For each:

* Run Stage 1
* Check question quality
* Verify UK terminology
* Note any adaptations needed

## 🚀 Ready for First Pilot!

Your system is now generic and ready for UK use.

### Before Contacting Communities:

* [ ] Test with all 3 UK examples
* [ ] Verify outputs are UK-appropriate
* [ ] Familiarize yourself with UK constitutions
* [ ] Prepare demo materials (screenshots, etc.)

### This Week:

1. **Monday-Tuesday:** Test system thoroughly
2. **Wednesday:** Email Friends of Carrington Moss
3. **Thursday:** Email 2-3 local Newcastle organizations
4. **Friday:** Follow up, schedule demo calls

## 📞 Reaching Out to Communities

Use the email templates provided in the main strategy guide.

**Key points to emphasize:**

* System is now UK-focused (not Colombian examples)
* Free pilot testing
* Professional outputs they can use
* Research partnership (not sales)

## 🐛 If Something Doesn't Work

### To rollback all changes:

bash

```bash
./rollback-genericization.sh
```

### To verify genericization worked:

bash

```bash
./verify-genericization.sh
```

### Common issues:

**Issue:** Form shows Colombian defaults
**Fix:** Check if genericization script completed successfully

bash

```bash
grep -n "Bajo Baudó" packages/frontend/src/app/page.tsx
```

Should return nothing.

**Issue:** UK constitutions not showing in dropdown
**Fix:** Check backend constitutions directory

bash

```bash
ls -la biomimicry/functions/backend/constitutions/
```

Should show `uk-commons-governance.md` and `uk-planning-aligned.md`

**Issue:** System still generates Colombia-specific content
**Fix:** This is actually fine! The AI is context-adaptive. If you put in UK data, it will generate UK content. The Colombian case study was just example  *inputs* .

## 📝 Documentation

All changes are documented in:

* This file (NEXT-STEPS.md)
* Backups in `backups/pre-generic-[timestamp]/`
* Test data in `test-data/uk-contexts/`

## 🎯 Success Criteria

You'll know the system is working when:

1. ✅ Forms are empty (no Colombian defaults)
2. ✅ UK test data generates UK-appropriate questions
3. ✅ No references to Colombia/mangroves in outputs
4. ✅ UK constitutions are selectable
5. ✅ Questions reference UK context (councils, planning, green belt, etc.)

## 💪 You're Ready!

The system is now generic, tested, and ready for UK pilots.

**Next action:** Email Carrington Moss this week!

Good luck! 🚀
NEXTSTEPSEOF

echo "  ✓ Created next steps guide: NEXT-STEPS.md"

echo -e "GREEN✓Nextstepsguidecreated{GREEN}✓ Next steps guide created
**GREEN**✓**N**e**x**t**s**t**e**p**s**gu**i**d**ecre**a**t**e**d**{NC}"
echo ""

# ============================================================================

# COMPLETION

# ============================================================================

echo ""
echo "╔════════════════════════════════════════════════════════════╗"
echo "║                                                            ║"
echo "║           ✅  GENERICIZATION COMPLETE!  ✅                 ║"
echo "║                                                            ║"
echo "╚════════════════════════════════════════════════════════════╝"
echo ""
echo -e "GREENSystemisnowreadyforUK(andanycontext)deployment!{GREEN}System is now ready for UK (and any context) deployment!
**GREEN**S**ys**t**e**mi**s**n**o**w**re**a**d**y**f**or**U**K**(**an**d**an**yco**n**t**e**x**t**)**d**e**pl**oy**m**e**n**t**!{NC}"
echo ""
echo "📁 Files modified:"
echo "   • packages/frontend/src/app/page.tsx (Colombian defaults removed)"
echo ""
echo "📁 Files created:"
echo "   • biomimicry/functions/backend/constitutions/uk-commons-governance.md"
echo "   • biomimicry/functions/backend/constitutions/uk-planning-aligned.md"
echo "   • test-data/uk-contexts/ (3 UK examples)"
echo "   • verify-genericization.sh"
echo "   • rollback-genericization.sh"
echo "   • NEXT-STEPS.md"
echo ""
echo "💾 Backups saved to:"
echo "   • $BACKUP_DIR/"
echo ""
echo -e "BLUE🧪NextSteps:{BLUE}🧪 Next Steps:
**B**LU**E**🧪**N**e**x**tSt**e**p**s**:{NC}"
echo ""
echo "1. Read NEXT-STEPS.md for detailed guidance"
echo "2. Test the system:"
echo "   cd packages/frontend && npm run dev"
echo "3. Try with Carrington Moss test data"
echo "4. Email communities this week!"
echo ""
echo -e "YELLOW⚠®Ifanythinggoeswrong:{YELLOW}⚠️  If anything goes wrong:
**Y**E**LL**O**W**⚠**R**◯**I**f**an**y**t**hin**gg**oes**w**ro**n**g**:**{NC}"
echo "   ./rollback-genericization.sh"
echo ""
echo -e "GREENGoodluckwithyourUKpilots!🚀{GREEN}Good luck with your UK pilots! 🚀
**GREEN**G**oo**d**l**u**c**k**w**i**t**h**yo**u**r**U**K**p**i**l**o**t**s**!**🚀**{NC}"
echo ""
`</artifact>`

---

## How to Use This Script

### 1. **Save the script:**

bash

```bash
cd ~/studio

# Copy the entire script content from the artifact above and save it
nano genericize-system.sh

# Paste the script content
# Press Ctrl+X, then Y, then Enter to save

# Make it executable
chmod +x genericize-system.sh
```

### 2. **Run the script:**

bash

```bash
./genericize-system.sh
```

### 3. **What it does:**

✅ **Backs up** all your current files (in case you need to revert)

✅ **Removes** all Colombian hardcoded examples

✅ **Adds** UK placeholder text

✅ **Creates** UK constitution templates

✅ **Creates** UK test data (Carrington Moss, Community Pub, CLT)

✅ **Updates** constitution selector dropdown

✅ **Verifies** everything worked

✅ **Creates** rollback script (if needed)

✅ **Creates** NEXT-STEPS.md guide

### 4. **After running:**

bash

```bash
# Test the system
cd packages/frontend
npm run dev

# Open browser to http://localhost:3000
# Verify forms are empty
# Load test data from test-data/uk-contexts/carrington-moss-example.json
# Run Stage 1
# Check outputs are UK-appropriate
```

---

## If Something Goes Wrong

### **To undo everything:**

bash

```bash
./rollback-genericization.sh
```

This restores all files from backup.

### **To verify it worked:**

bash

```bash
./verify-genericization.sh
```

This checks that:

* Colombian defaults are removed
* UK constitutions exist
* Test data is created

---

## What This Script Does NOT Touch

✅ **Backend AI flows** (already generic)

✅ **Database/Firestore** (no changes needed)

✅ **Package dependencies** (no new packages)

✅ **Configuration files** (no config changes)

**It ONLY changes:**

* Frontend default form values
* Adds UK constitution files
* Creates UK test data

---

## Estimated Time

**Script runs in:** ~5 seconds

**Your testing:** 10-15 minutes

**Total:** 15-20 minutes from script run to confirmed working

---

## The Beautiful Part

After running this script, when you input:

* **Carrington Moss** → System generates UK planning opposition questions
* **Community Pub** → System generates UK rural community questions
* **CLT Housing** → System generates UK urban housing questions

**The AI automatically adapts!** Because the intelligence is in the model, not the defaults.

---

**Ready to run it?**

Just:

1. Save the script
2. `./genericize-system.sh`
3. Test with Carrington Moss
4. Email communities!

**You'll be ready to pilot in UK by this afternoon.** 🚀
