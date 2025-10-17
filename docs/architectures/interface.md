`<svg viewBox="0 0 1400 1600" xmlns="http://www.w3.org/2000/svg">`
  `<defs>`
    `<style>`
      .browser { fill: transparent; stroke: #000; stroke-width: 2; }
      .form { fill: transparent; stroke: #000; stroke-width: 1; }
      .input { fill: transparent; stroke: #000; stroke-width: 1; }
      .button { fill: transparent; stroke: #000; stroke-width: 2; }
      .button-text { fill: #000; font-family: Inter, Arial, sans-serif; font-size: 14px; font-weight: bold; text-anchor: middle; }
      .label { font-family: Inter, Arial, sans-serif; font-size: 13px; font-weight: bold; fill: #000; text-anchor: start; }
      .help-text { font-family: Inter, Arial, sans-serif; font-size: 11px; fill: #000; text-anchor: start; font-style: italic; }
      .input-text { font-family: Inter, Arial, sans-serif; font-size: 12px; fill: #000; text-anchor: start; }
      .title { font-family: Inter, Arial, sans-serif; font-size: 20px; font-weight: bold; fill: #000; text-anchor: middle; }
    `</style>`
  `</defs>`
  `<text x="700" y="30" style="font-family: Inter, Arial, sans-serif; font-size: 26px; font-weight: bold; fill: #000; text-anchor: middle;">`
    What The Interface Actually Looks Like
  `</text>`

<!-- Browser Window -->

<rect class="browser" x="100" y="60" width="1200" height="1500" rx="10"/>
  <!-- Browser bar -->
  <rect x="100" y="60" width="1200" height="40" fill="transparent" stroke="#000" stroke-width="2" rx="10"/>
  <circle cx="130" cy="80" r="8" fill="transparent" stroke="#000" stroke-width="2"/>
  <circle cx="155" cy="80" r="8" fill="transparent" stroke="#000" stroke-width="2"/>
  <circle cx="180" cy="80" r="8" fill="transparent" stroke="#000" stroke-width="2"/>
  <text x="700" y="85" style="font-family: Inter, Arial, sans-serif; font-size: 13px; fill: #000; text-anchor: middle;">
    regenerative-ai.app/stage-1
  </text>
  <!-- Form content -->
  <rect class="form" x="150" y="130" width="1100" height="1380" rx="5"/>
  <!-- Title -->
<text x="700" y="170" class="title">Stage 1: Generate Inquiry Questions</text>
<text x="700" y="195" style="font-family: Inter, Arial, sans-serif; font-size: 14px; fill: #000; text-anchor: middle;">
Answer these questions about your project. We'll generate Story of Place questions for your workshops.
</text>

<!-- Field 1: Project Name -->

<text x="180" y="240" class="label">Project Name *</text>
<text x="180" y="258" class="help-text">What do you call this initiative?</text>
<rect class="input" x="180" y="265" width="1040" height="35" rx="3"/>
<text x="195" y="288" class="input-text">Carrington Moss Alternative Vision</text>

<!-- Field 2: Location -->

<text x="180" y="330" class="label">Location *</text>
<text x="180" y="348" class="help-text">Where is this place? (City, region, country)</text>
<rect class="input" x="180" y="355" width="1040" height="35" rx="3"/>
<text x="195" y="378" class="input-text">Carrington, Greater Manchester, UK</text>

<!-- Field 3: Bioregion -->

<text x="180" y="420" class="label">Bioregion *</text>
<text x="180" y="438" class="help-text">Watershed, ecological region, or natural boundaries</text>
<rect class="input" x="180" y="445" width="1040" height="35" rx="3"/>
<text x="195" y="468" class="input-text">Greater Manchester Wetlands / Mersey Basin</text>

<!-- Field 4: Current Tensions -->

<text x="180" y="510" class="label">Current Tensions *</text>
<text x="180" y="528" class="help-text">What conflicts or pressures exist? (Add at least 2)</text>

<rect class="input" x="180" y="535" width="1040" height="35" rx="3"/>
  <text x="195" y="558" class="input-text">Proposed 6,500-home development on green belt</text>
  <rect class="input" x="180" y="580" width="1040" height="35" rx="3"/>
  <text x="195" y="603" class="input-text">Peatland destruction and carbon release</text>
  <rect class="input" x="180" y="625" width="1040" height="35" rx="3"/>
  <text x="195" y="648" class="input-text">Loss of community commons and connection to land</text>
  <rect class="button" x="180" y="670" width="140" height="30" rx="3"/>
  <text x="250" y="690" class="button-text" style="font-size: 12px;">+ Add Tension</text>
  <!-- Field 5: Historical Patterns -->
<text x="180" y="735" class="label">Historical Patterns *</text>
<text x="180" y="753" class="help-text">What happened here in the past? What patterns shaped this place?</text>

<rect class="input" x="180" y="760" width="1040" height="35" rx="3"/>
  <text x="195" y="783" class="input-text">Peatland commons - shared community resource</text>
  <rect class="input" x="180" y="805" width="1040" height="35" rx="3"/>
  <text x="195" y="828" class="input-text">Local food production and peat harvesting</text>
  <rect class="input" x="180" y="850" width="1040" height="35" rx="3"/>
  <text x="195" y="873" class="input-text">Working-class solidarity and mutual aid traditions</text>
  <rect class="button" x="180" y="895" width="140" height="30" rx="3"/>
  <text x="250" y="915" class="button-text" style="font-size: 12px;">+ Add Pattern</text>
  <!-- Field 6: Stakeholder Types -->
<text x="180" y="960" class="label">Stakeholder Groups *</text>
<text x="180" y="978" class="help-text">Who should we generate questions for? (Select or add custom)</text>

<!-- Checkboxes -->

<rect x="180" y="990" width="20" height="20" rx="3" fill="#000" stroke="#000" stroke-width="1"/>
  <text x="185" y="1005" style="font-family: Inter, Arial, sans-serif; font-size: 16px; fill: white; font-weight: bold;">✓</text>
  <text x="210" y="1006" class="input-text">Long-term residents / Elders</text>
  <rect x="180" y="1020" width="20" height="20" rx="3" fill="#000" stroke="#000" stroke-width="1"/>
  <text x="185" y="1035" style="font-family: Inter, Arial, sans-serif; font-size: 16px; fill: white; font-weight: bold;">✓</text>
  <text x="210" y="1036" class="input-text">Youth (ages 18-30)</text>
  <rect x="180" y="1050" width="20" height="20" rx="3" fill="#000" stroke="#000" stroke-width="1"/>
  <text x="185" y="1065" style="font-family: Inter, Arial, sans-serif; font-size: 16px; fill: white; font-weight: bold;">✓</text>
  <text x="210" y="1066" class="input-text">Environmental groups</text>
  <rect x="180" y="1080" width="20" height="20" rx="3" fill="transparent" stroke="#000" stroke-width="1"/>
  <text x="210" y="1096" class="input-text">Local farmers</text>
  <rect x="180" y="1110" width="20" height="20" rx="3" fill="transparent" stroke="#000" stroke-width="1"/>
  <text x="210" y="1126" class="input-text">Council staff / Planners</text>
  <rect class="button" x="180" y="1145" width="160" height="30" rx="3"/>
  <text x="260" y="1165" class="button-text" style="font-size: 12px;">+ Custom Group</text>
  <!-- Optional: Additional Context -->
<text x="180" y="1210" class="label">Additional Context (Optional)</text>
<text x="180" y="1228" class="help-text">Anything else we should know about this place?</text>
<rect class="input" x="180" y="1235" width="1040" height="80" rx="3"/>
<text x="195" y="1258" class="input-text">This is ancestral wetland. Recent archaeological findings</text>
<text x="195" y="1275" class="input-text">show continuous habitation for 8,000 years. Strong</text>
<text x="195" y="1292" class="input-text">community opposition to development.</text>

<!-- Generate Button -->

<rect class="button" x="480" y="1360" width="440" height="60" rx="5"/>
  <text x="700" y="1395" class="button-text" style="font-size: 18px;">🌱 Generate Inquiry Questions</text>
  <!-- Footer note -->
  <text x="700" y="1445" style="font-family: Inter, Arial, sans-serif; font-size: 12px; fill: #000; text-anchor: middle;">
    This will take 10-20 seconds. Questions will be unique to your project.
  </text>
  <text x="700" y="1465" style="font-family: Inter, Arial, sans-serif; font-size: 12px; fill: #000; text-anchor: middle;">
    Not from a template - AI generates contextually-appropriate questions.
  </text>
  <!-- Bottom note -->
  <rect x="250" y="1495" width="900" height="50" rx="5" fill="transparent" stroke="#000" stroke-width="2"/>
  <text x="700" y="1518" style="font-family: Inter, Arial, sans-serif; font-size: 13px; font-weight: bold; fill: #000; text-anchor: middle;">
    💡 After generation: Download questions → Conduct workshops → Return for Stage 2
  </text>
  <text x="700" y="1535" style="font-family: Inter, Arial, sans-serif; font-size: 12px; fill: #000; text-anchor: middle;">
    (Workshops typically take 2-3 weeks)
  </text>
</svg>
