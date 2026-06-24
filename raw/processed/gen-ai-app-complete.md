---
marp: true
theme: default
paginate: true
footer: Gen AI in Apps
style: |
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&family=JetBrains+Mono:wght@400;600&display=swap');

  :root {
    --ink: #f7f4ea;
    --paper: #101114;
    --panel: #181a20;
    --panel-2: #20232b;
    --line: #343946;
    --muted: #a7adba;
    --dim: #727989;
    --cyan: #53d7ff;
    --green: #7ee787;
    --amber: #ffcb6b;
    --coral: #ff7a6e;
    --violet: #b692ff;
    --blue: #82aaff;
    --footer-clearance: 34px;
    --compact-gap: 12px;
  }

  section {
    background:
      radial-gradient(circle at 84% 12%, rgba(83, 215, 255, 0.10), transparent 30%),
      linear-gradient(135deg, #101114 0%, #151820 56%, #0d0f12 100%);
    color: var(--ink);
    font-family: Inter, sans-serif;
    font-weight: 300;
    line-height: 1.36;
    padding: 46px 66px;
  }

  section::after {
    color: #5c6370;
    font-size: 0.58em;
    right: 32px;
    bottom: 24px;
  }

  footer {
    color: #5c6370;
    font-size: 0.56em;
    left: 66px;
    bottom: 24px;
  }

  h1 {
    color: var(--ink);
    font-size: 2.38em;
    font-weight: 800;
    letter-spacing: 0;
    line-height: 1.02;
    margin: 0 0 12px;
  }

  h2 {
    color: var(--muted);
    font-size: 1.0em;
    font-weight: 300;
    margin: 0 0 22px;
    max-width: 900px;
  }

  h3 {
    color: var(--cyan);
    font-size: 0.58em;
    font-weight: 800;
    letter-spacing: 0.16em;
    margin: 0 0 10px;
    text-transform: uppercase;
  }

  p, li {
    color: var(--muted);
    font-size: 0.72em;
  }

  strong {
    color: var(--ink);
    font-weight: 700;
  }

  a {
    color: var(--cyan);
  }

  section.title,
  .lead {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: left;
  }

  section.title h1,
  .lead h1 {
    font-size: 3.45em;
    max-width: 980px;
  }

  section.title h2,
  .lead h2 {
    font-size: 1.05em;
    margin: 0;
  }

  section.title {
    align-items: flex-start;
    padding-left: 88px;
  }

  section.break {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
  }

  section.break h1 {
    font-size: 3.35em;
    max-width: 980px;
  }

  section.break h2 {
    margin: 0 auto;
    max-width: 820px;
  }

  .title-heading {
    align-self: flex-start;
    margin: 0;
    text-align: left;
    width: fit-content;
  }

  .title-heading h1 {
    text-align: left;
  }

  .presenter-lockup {
    align-items: center;
    display: flex;
    gap: 14px;
    justify-content: flex-start;
    margin: 8px 0 18px;
    max-width: 620px;
  }

  .presenter-logo {
    border-radius: 8px;
    display: block;
    flex: 0 0 auto;
    width: 150px;
  }

  .presenter-copy {
    text-align: left;
  }

  .presenter {
    color: var(--ink);
    font-size: 0.82em;
    font-weight: 700;
    margin: 0 0 4px;
  }

  .presenter-org {
    color: var(--cyan);
    font-size: 0.58em;
    font-weight: 800;
    letter-spacing: 0.02em;
    margin: 0;
    text-transform: none;
  }

  .kicker {
    color: var(--cyan);
    font-size: 0.64em;
    font-weight: 800;
    letter-spacing: 0.22em;
    margin-bottom: 18px;
    text-transform: uppercase;
  }

  .accent-line {
    background: linear-gradient(90deg, var(--cyan), var(--amber), var(--coral));
    border-radius: 999px;
    height: 4px;
    margin: 24px 0;
    width: 170px;
  }

  section.break .accent-line {
    margin: 24px auto;
  }

  .grid-2 {
    display: grid;
    gap: 20px;
    grid-template-columns: 1fr 1fr;
  }

  .grid-3 {
    display: grid;
    gap: 16px;
    grid-template-columns: repeat(3, 1fr);
  }

  .grid-4 {
    display: grid;
    gap: 12px;
    grid-template-columns: repeat(4, 1fr);
  }

  .route-map {
    display: grid;
    gap: 14px;
    grid-template-columns: repeat(3, 1fr);
    margin-top: 24px;
  }

  .route-stop {
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.045), rgba(255, 255, 255, 0.018));
    border: 1px solid var(--line);
    border-radius: 8px;
    min-height: 128px;
    padding: 16px;
  }

  .route-index {
    color: var(--cyan);
    font-family: JetBrains Mono, monospace;
    font-size: 0.48em;
    font-weight: 700;
    letter-spacing: 0.12em;
    margin-bottom: 10px;
    text-transform: uppercase;
  }

  .route-stop h4 {
    color: var(--ink);
    font-size: 0.78em;
    font-weight: 800;
    margin: 0 0 8px;
  }

  .route-stop p {
    color: var(--muted);
    font-size: 0.58em;
    margin: 0;
  }

  .panel {
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.045), rgba(255, 255, 255, 0.018));
    border: 1px solid var(--line);
    border-radius: 8px;
    padding: 18px;
  }

  .panel h4 {
    color: var(--ink);
    font-size: 0.76em;
    font-weight: 800;
    margin: 0 0 7px;
  }

  .panel p {
    color: var(--muted);
    font-size: 0.61em;
    margin: 0;
  }

  .tight p {
    font-size: 0.56em;
  }

  section.package-risk h1 {
    font-size: 2.12em;
    margin-bottom: 10px;
  }

  section.package-risk .grid-2 {
    gap: 16px;
  }

  section.package-risk .grid-3 {
    gap: 12px;
  }

  section.package-risk .panel {
    padding: 14px 16px;
  }

  section.package-risk .panel h4 {
    font-size: 0.7em;
    margin-bottom: 5px;
  }

  section.package-risk .panel p {
    font-size: 0.56em;
  }

  section.package-risk .tight p {
    font-size: 0.51em;
  }

  .tag {
    border: 1px solid var(--line);
    border-radius: 6px;
    color: var(--muted);
    display: inline-block;
    font-size: 0.52em;
    font-weight: 700;
    letter-spacing: 0.08em;
    margin: 0 5px 8px 0;
    padding: 5px 8px;
    text-transform: uppercase;
  }

  .tag.cyan { color: var(--cyan); border-color: rgba(83, 215, 255, 0.32); background: rgba(83, 215, 255, 0.08); }
  .tag.green { color: var(--green); border-color: rgba(126, 231, 135, 0.30); background: rgba(126, 231, 135, 0.08); }
  .tag.amber { color: var(--amber); border-color: rgba(255, 203, 107, 0.30); background: rgba(255, 203, 107, 0.08); }
  .tag.coral { color: var(--coral); border-color: rgba(255, 122, 110, 0.30); background: rgba(255, 122, 110, 0.08); }
  .tag.violet { color: var(--violet); border-color: rgba(182, 146, 255, 0.30); background: rgba(182, 146, 255, 0.08); }

  .callout {
    background: rgba(255, 203, 107, 0.08);
    border: 1px solid rgba(255, 203, 107, 0.28);
    border-radius: 8px;
    color: var(--ink);
    font-size: 0.68em;
    margin-top: 18px;
    padding: 14px 16px;
  }

  .callout.cyan {
    background: rgba(83, 215, 255, 0.08);
    border-color: rgba(83, 215, 255, 0.28);
  }

  .artifact {
    background: rgba(83, 215, 255, 0.04);
    border: 1px solid rgba(83, 215, 255, 0.28);
    border-radius: 8px;
    display: grid;
    gap: 1px;
    grid-template-columns: 1fr 1fr;
    margin-top: 18px;
    overflow: hidden;
  }

  .artifact.single {
    grid-template-columns: 1fr;
  }

  .artifact .item {
    background: rgba(16, 17, 20, 0.76);
    padding: 11px 14px 12px;
  }

  .artifact .label {
    color: var(--cyan);
    font-size: 0.48em;
    font-weight: 800;
    letter-spacing: 0.12em;
    margin-bottom: 5px;
    text-transform: uppercase;
  }

  .artifact .body {
    color: var(--muted);
    font-family: JetBrains Mono, monospace;
    font-size: 0.51em;
    line-height: 1.45;
  }

  .artifact strong {
    color: var(--ink);
    font-weight: 700;
  }

  .footer-clearance {
    margin-bottom: var(--footer-clearance);
  }

  .artifact.footer-clearance {
    margin-top: var(--compact-gap);
  }

  .artifact.footer-clearance .item {
    padding: 8px 12px 9px;
  }

  .artifact.footer-clearance .body {
    font-size: 0.48em;
    line-height: 1.34;
  }

  .callout.footer-clearance {
    font-size: 0.64em;
    margin-top: 14px;
    padding: 12px 16px;
  }

  .flow {
    align-items: center;
    display: flex;
    gap: 10px;
    justify-content: space-between;
    margin-top: 24px;
  }

  .node {
    background: var(--panel);
    border: 1px solid var(--line);
    border-radius: 8px;
    color: var(--ink);
    flex: 1;
    font-size: 0.62em;
    font-weight: 800;
    min-height: 76px;
    padding: 14px 12px;
    text-align: center;
  }

  .node span {
    color: var(--muted);
    display: block;
    font-size: 0.82em;
    font-weight: 300;
    margin-top: 5px;
  }

  .arrow {
    color: var(--cyan);
    font-size: 1.0em;
    font-weight: 800;
  }

  .split {
    align-items: center;
    display: grid;
    gap: 30px;
    grid-template-columns: 0.94fr 1.06fr;
  }

  .stack {
    display: grid;
    gap: 10px;
    margin-top: 14px;
  }

  .row {
    align-items: center;
    background: rgba(255, 255, 255, 0.035);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 8px;
    display: flex;
    gap: 13px;
    padding: 11px 14px;
  }

  .num {
    align-items: center;
    background: rgba(83, 215, 255, 0.12);
    border: 1px solid rgba(83, 215, 255, 0.28);
    border-radius: 50%;
    color: var(--cyan);
    display: flex;
    flex: 0 0 32px;
    font-size: 0.58em;
    font-weight: 800;
    height: 32px;
    justify-content: center;
    width: 32px;
  }

  .row p {
    font-size: 0.61em;
    margin: 0;
  }

  .mini-title {
    color: var(--ink);
    display: block;
    font-size: 1.02em;
    font-weight: 800;
    margin-bottom: 2px;
  }

  .mono {
    font-family: JetBrains Mono, monospace;
  }

  .small {
    color: var(--dim);
    font-size: 0.56em;
  }

  .big-word {
    color: var(--cyan);
    font-size: 1.72em;
    font-weight: 800;
    line-height: 1.08;
    margin-bottom: 12px;
  }

  .model-definition {
    color: var(--cyan);
    font-size: 0.86em;
    font-weight: 800;
    line-height: 1.2;
    margin-bottom: 12px;
  }

  .metric {
    background: var(--panel);
    border: 1px solid var(--line);
    border-radius: 8px;
    padding: 16px;
    position: relative;
    overflow: hidden;
  }

  .metric::before {
    content: "";
    background: linear-gradient(90deg, var(--cyan), transparent);
    height: 2px;
    left: 0;
    position: absolute;
    right: 0;
    top: 0;
  }

  .metric .value {
    color: var(--ink);
    font-size: 1.35em;
    font-weight: 800;
  }

  .metric .label {
    color: var(--dim);
    font-size: 0.53em;
    text-transform: uppercase;
    letter-spacing: 0.10em;
  }

  .meter {
    background: var(--panel);
    border: 1px solid var(--line);
    border-radius: 8px;
    height: 18px;
    overflow: hidden;
  }

  .meter span {
    display: block;
    height: 100%;
  }

  .quote {
    border-left: 4px solid var(--coral);
    color: var(--ink);
    font-size: 0.88em;
    font-weight: 800;
    padding-left: 18px;
  }

  .diagram {
    margin-top: 14px;
    width: 100%;
  }

  section.compact-bottom h1 {
    font-size: 2.16em;
    margin-bottom: 8px;
  }

  section.compact-bottom h2 {
    font-size: 0.88em;
    margin-bottom: 14px;
    max-width: 980px;
  }

  section.compact-bottom .flow {
    margin-top: 16px;
  }

  section.compact-bottom .node {
    font-size: 0.58em;
    min-height: 62px;
    padding: 10px;
  }

  section.compact-bottom .node span {
    font-size: 0.78em;
  }

  section.compact-bottom .grid-2,
  section.compact-bottom .grid-3,
  section.compact-bottom .grid-4 {
    gap: var(--compact-gap);
  }

  section.compact-bottom .stack {
    gap: 7px;
    margin-top: 10px;
  }

  section.compact-bottom .row {
    gap: 10px;
    padding: 8px 12px;
  }

  section.compact-bottom .num {
    flex-basis: 28px;
    font-size: 0.52em;
    height: 28px;
    width: 28px;
  }

  section.compact-bottom .row p {
    font-size: 0.55em;
    line-height: 1.28;
  }

  section.compact-bottom .quote {
    font-size: 0.78em;
    margin-bottom: 14px;
    padding-left: 14px;
  }

  section.compact-bottom .panel {
    padding: 12px 14px;
  }

  section.compact-bottom .panel h4 {
    font-size: 0.68em;
    margin-bottom: 5px;
  }

  section.compact-bottom .panel p {
    font-size: 0.52em;
    line-height: 1.3;
  }

  .good { color: var(--green); }
  .warn { color: var(--amber); }
  .bad { color: var(--coral); }
  .violet { color: var(--violet); }
---

<!-- Export PDF with HTML and SVG rendering enabled: npx @marp-team/marp-cli gen-ai-app-complete.md --html --pdf --allow-local-files -o gen-ai-app-complete/gen-ai-app-complete.pdf -->

<!-- _class: title -->
<!-- _footer: '' -->

<div class="title-heading">
  <div class="kicker">Gen AI in Apps</div>
  <h1>Generative AI Application Basics</h1>
</div>

<div class="accent-line"></div>

<div class="presenter-lockup">
  <img class="presenter-logo" src="./logo_dark.png" alt="Martin Béchard logo" />
  <div class="presenter-copy">
    <div class="presenter">Martin Béchard</div>
    <div class="presenter-org">Martin.Bechard@DevConsult.ca</div>
  </div>
</div>

## June 18, 2026

---

<div class="kicker">Overview</div>

# The route through the deck

## We move from model foundations to the application harness, then to the controls needed to ship AI features responsibly.

<div class="route-map">
  <div class="route-stop">
    <div class="route-index">Stop 1</div>
    <h4>Model foundations</h4>
    <p>What models are, how text becomes vectors, and how LLMs generate tokens.</p>
  </div>
  <div class="route-stop">
    <div class="route-index">Stop 2</div>
    <h4>Training and tuning</h4>
    <p>How pre-training, instruction tuning, alignment, and specialization shape behavior.</p>
  </div>
  <div class="route-stop">
    <div class="route-index">Stop 3</div>
    <h4>Runtime behavior</h4>
    <p>How requests, context windows, streaming, sampling, and token costs affect the product.</p>
  </div>
  <div class="route-stop">
    <div class="route-index">Stop 4</div>
    <h4>Evaluation and grounding</h4>
    <p>How answers earn trust through evidence, evals, graders, and source-backed claims.</p>
  </div>
  <div class="route-stop">
    <div class="route-index">Stop 5</div>
    <h4>Retrieval and tools</h4>
    <p>How RAG, embeddings, vector search, tool calls, and MCP add facts and actions.</p>
  </div>
  <div class="route-stop">
    <div class="route-index">Stop 6</div>
    <h4>Architecture and readiness</h4>
    <p>How harnesses, agents, workflows, permissions, and product controls turn models into apps.</p>
  </div>
</div>

---

<!-- _class: break -->

<div class="kicker">Model foundations</div>

# From model to application

<div class="accent-line"></div>

## The first layer is a practical mental model: what the model is, what it learned, and what the app sends at runtime.

---

<!-- _class: compact-bottom -->

<div class="kicker">Model foundations</div>

# Generative AI architecture

## Most generative AI apps split user interface, server orchestration, GPU model calls, and product output.

<div class="flow">
  <div class="node">Fat client<span>coding tool or interface</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Server API<span>auth, context, state, workflow</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">GPU model process<span>generate, reason, embed</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Product result<span>answer, action, artifact, trace</span></div>
</div>

<div class="grid-3" style="margin-top: 14px;">
  <div class="panel"><h4>Fat client</h4><p>A coding tool, chat interface, form, file UI, or workflow surface that gathers user intent and local context.</p></div>
  <div class="panel"><h4>Server API</h4><p>The server tier is an API that assembles context, checks permissions, manages state, and calls the model process.</p></div>
  <div class="panel"><h4>Model process</h4><p>The model process runs tensor operations on GPUs and returns generated tokens, tool requests, or embeddings.</p></div>
</div>

<div class="artifact footer-clearance">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">User asks: compare two invoices and flag policy exceptions.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">UI sends files and task &rarr; API extracts text and checks access &rarr; model drafts exception summary.</div>
  </div>
</div>

---

<div class="kicker">Model foundations</div>

# What is an AI model?

<div class="split">
  <div>
    <div class="model-definition">A learned transformation engine: converts raw inputs into values of interest such as signals or answers to a question.</div>
    <p>In modern AI, the focus is on neural networks: one or more layers of tensors that transform n-dimensional input vectors into target vectors.</p>
    <p>Tensors are like matrices with multiple dimensions. Layers apply learned weights through multiplication, addition, division, and activation functions.</p>
  </div>
  <svg class="diagram" viewBox="0 0 560 320" role="img" aria-label="neural network layer building block">
    <rect x="28" y="34" width="504" height="252" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <text x="280" y="66" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">One neural-network building block</text>
    <text x="280" y="91" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">input vector values are weighted, summed, transformed, then emitted</text>
    <circle cx="82" cy="124" r="21" fill="#181a20" stroke="#53d7ff"/>
    <circle cx="82" cy="172" r="21" fill="#181a20" stroke="#53d7ff"/>
    <circle cx="82" cy="220" r="21" fill="#181a20" stroke="#53d7ff"/>
    <text x="82" y="130" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="JetBrains Mono">x1</text>
    <text x="82" y="178" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="JetBrains Mono">x2</text>
    <text x="82" y="226" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="JetBrains Mono">x3</text>
    <path d="M106 124 C146 124 160 145 195 155" stroke="#53d7ff" stroke-width="3" fill="none" stroke-linecap="round"/>
    <path d="M106 172 H192" stroke="#53d7ff" stroke-width="3" fill="none" stroke-linecap="round"/>
    <path d="M106 220 C146 220 160 199 195 189" stroke="#53d7ff" stroke-width="3" fill="none" stroke-linecap="round"/>
    <text x="143" y="118" text-anchor="middle" fill="#727989" font-size="11" font-family="JetBrains Mono">w1*x1</text>
    <text x="145" y="164" text-anchor="middle" fill="#727989" font-size="11" font-family="JetBrains Mono">w2*x2</text>
    <text x="143" y="237" text-anchor="middle" fill="#727989" font-size="11" font-family="JetBrains Mono">w3*x3</text>
    <rect x="198" y="132" width="104" height="80" rx="14" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
    <text x="250" y="164" text-anchor="middle" fill="#ffcb6b" font-size="24" font-family="Inter" font-weight="800">sum</text>
    <text x="250" y="190" text-anchor="middle" fill="#f7f4ea" font-size="13" font-family="JetBrains Mono">+ bias</text>
    <path d="M306 172 H358" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <path d="M346 160 L362 172 L346 184" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <rect x="366" y="140" width="78" height="64" rx="14" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <text x="405" y="167" text-anchor="middle" fill="#7ee787" font-size="19" font-family="Inter" font-weight="800">f</text>
    <text x="405" y="188" text-anchor="middle" fill="#f7f4ea" font-size="11" font-family="Inter">activate</text>
    <path d="M448 172 H490" stroke="#b692ff" stroke-width="4" stroke-linecap="round"/>
    <path d="M478 160 L494 172 L478 184" fill="none" stroke="#b692ff" stroke-width="4" stroke-linecap="round"/>
    <circle cx="513" cy="172" r="22" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
    <text x="513" y="178" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="JetBrains Mono">y</text>
    <text x="82" y="265" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">input vector</text>
    <text x="252" y="265" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">multiply and add</text>
    <text x="405" y="265" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">divide and normalize</text>
    <text x="513" y="265" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">output</text>
  </svg>
</div>

<div class="callout">Large models repeat this block across many tensors and layers: vector in, transformed representation, target vector out.</div>

---

<div class="kicker">Model foundations</div>

# Custom ML model

<div class="grid-3">
  <div class="panel">
    <h4>Machine learning</h4>
    <p>Trained on data to produce desired results.</p>
  </div>
  <div class="panel">
    <h4>Industrial example</h4>
    <p>Use sensor data to predict potential equipment failure.</p>
  </div>
  <div class="panel">
    <h4>Target output</h4>
    <p>Transform recent sensor readings into a predicted time to failure.</p>
  </div>
</div>

<svg class="diagram" viewBox="0 0 920 230" role="img" aria-label="custom machine learning model trained from sensor history">
  <rect x="24" y="34" width="220" height="68" rx="12" fill="#181a20" stroke="#343946"/>
  <text x="134" y="63" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">History of operation</text>
  <text x="134" y="87" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">readings, loads, failures</text>
  <path d="M256 68 H330" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
  <path d="M318 56 L334 68 L318 80" fill="none" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
  <rect x="350" y="34" width="188" height="68" rx="12" fill="rgba(83,215,255,0.12)" stroke="#53d7ff"/>
  <text x="444" y="63" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Train model</text>
  <text x="444" y="87" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">learn useful weights</text>
  <path d="M444 108 V139" stroke="#ffcb6b" stroke-width="4" stroke-linecap="round"/>
  <path d="M432 127 L444 143 L456 127" fill="none" stroke="#ffcb6b" stroke-width="4" stroke-linecap="round"/>
  <rect x="24" y="152" width="220" height="54" rx="12" fill="#181a20" stroke="#343946"/>
  <text x="134" y="175" text-anchor="middle" fill="#f7f4ea" font-size="16" font-family="Inter" font-weight="800">Most recent readings</text>
  <text x="134" y="195" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">each reading is a vector</text>
  <path d="M256 179 H330" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
  <path d="M318 167 L334 179 L318 191" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
  <rect x="350" y="144" width="188" height="70" rx="14" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
  <text x="444" y="174" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Custom ML model</text>
  <text x="444" y="197" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">domain-specific predictor</text>
  <path d="M552 179 H636" stroke="#b692ff" stroke-width="4" stroke-linecap="round"/>
  <path d="M624 167 L640 179 L624 191" fill="none" stroke="#b692ff" stroke-width="4" stroke-linecap="round"/>
  <rect x="656" y="144" width="228" height="70" rx="14" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
  <text x="770" y="174" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Predicted time</text>
  <text x="770" y="197" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">to equipment failure</text>
</svg>

<div class="callout" style="margin-top: 8px; padding: 10px 16px;">The model is trained on a history of operation, then applies that learned pattern to the newest sensor vectors.</div>

---

<div class="kicker">Model foundations</div>

# Deep learning stacks neural network layers

<div class="split">
  <div>
    <p>Deep learning connects multiple layers of neural networks into one model.</p>
    <p>Each layer transforms a vector into a new representation. Early layers may capture simpler signals; later layers combine them into more useful patterns.</p>
    <p>The depth comes from repeating this transformation many times.</p>
  </div>
  <svg class="diagram" viewBox="0 0 560 320" role="img" aria-label="deep learning neural network layers">
    <rect x="24" y="28" width="512" height="264" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <text x="280" y="58" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Stacked neural-network layers</text>
    <text x="280" y="82" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">each layer transforms the vector it receives</text>
    <text x="72" y="112" text-anchor="middle" fill="#53d7ff" font-size="12" font-family="Inter" font-weight="800">Input</text>
    <text x="190" y="112" text-anchor="middle" fill="#ffcb6b" font-size="12" font-family="Inter" font-weight="800">Layer 1</text>
    <text x="300" y="112" text-anchor="middle" fill="#7ee787" font-size="12" font-family="Inter" font-weight="800">Layer 2</text>
    <text x="410" y="112" text-anchor="middle" fill="#b692ff" font-size="12" font-family="Inter" font-weight="800">Layer 3</text>
    <text x="506" y="112" text-anchor="middle" fill="#f7f4ea" font-size="12" font-family="Inter" font-weight="800">Output</text>
    <circle cx="72" cy="148" r="12" fill="#181a20" stroke="#53d7ff"/>
    <circle cx="72" cy="190" r="12" fill="#181a20" stroke="#53d7ff"/>
    <circle cx="72" cy="232" r="12" fill="#181a20" stroke="#53d7ff"/>
    <circle cx="190" cy="134" r="13" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
    <circle cx="190" cy="174" r="13" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
    <circle cx="190" cy="214" r="13" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
    <circle cx="190" cy="254" r="13" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
    <circle cx="300" cy="148" r="13" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <circle cx="300" cy="190" r="13" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <circle cx="300" cy="232" r="13" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <circle cx="410" cy="160" r="13" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
    <circle cx="410" cy="220" r="13" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
    <circle cx="506" cy="190" r="14" fill="#181a20" stroke="#f7f4ea"/>
    <path d="M86 148 C120 148 142 134 176 134 M86 148 C120 148 142 174 176 174 M86 190 C120 190 142 174 176 174 M86 190 C120 190 142 214 176 214 M86 232 C120 232 142 214 176 214 M86 232 C120 232 142 254 176 254" stroke="#53d7ff" stroke-width="2" fill="none" opacity="0.65"/>
    <path d="M204 134 C238 134 252 148 286 148 M204 174 H286 M204 214 H286 M204 254 C238 254 252 232 286 232 M204 174 C238 174 252 232 286 232 M204 214 C238 214 252 148 286 148" stroke="#ffcb6b" stroke-width="2" fill="none" opacity="0.62"/>
    <path d="M314 148 C348 148 364 160 396 160 M314 190 C350 190 364 160 396 160 M314 190 C350 190 364 220 396 220 M314 232 C350 232 364 220 396 220" stroke="#7ee787" stroke-width="2" fill="none" opacity="0.68"/>
    <path d="M424 160 C458 160 472 190 490 190 M424 220 C458 220 472 190 490 190" stroke="#b692ff" stroke-width="3" fill="none" opacity="0.8"/>
    <text x="72" y="272" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">raw vector</text>
    <text x="300" y="272" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">hidden representations</text>
    <text x="506" y="272" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">target</text>
  </svg>
</div>

<div class="callout" style="margin-top: 8px; padding: 10px 16px;">A deep model learns many small transformations, then composes them into a stronger overall transformation.</div>

---

<div class="kicker">Model foundations</div>

# Models can learn from sequences

<div class="split">
  <div>
    <div class="big-word">Order can<br>matter.</div>
    <p>A single sensor vector is one snapshot. Many industrial problems need multiple readings in order because trends, spikes, and timing carry signal.</p>
    <p>Training can run historical readings as a sequence and target a desired sequence of outputs.</p>
  </div>
  <svg class="diagram" viewBox="0 0 560 320" role="img" aria-label="sequence of sensor vectors mapped to sequence of predictions">
    <rect x="24" y="32" width="512" height="256" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <text x="280" y="62" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Training on ordered examples</text>
    <text x="280" y="86" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">sensor sequence in, desired output sequence out</text>
    <rect x="52" y="122" width="70" height="48" rx="10" fill="#181a20" stroke="#53d7ff"/>
    <rect x="142" y="122" width="70" height="48" rx="10" fill="#181a20" stroke="#53d7ff"/>
    <rect x="232" y="122" width="70" height="48" rx="10" fill="#181a20" stroke="#53d7ff"/>
    <rect x="322" y="122" width="70" height="48" rx="10" fill="#181a20" stroke="#53d7ff"/>
    <text x="87" y="151" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="JetBrains Mono">x1</text>
    <text x="177" y="151" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="JetBrains Mono">x2</text>
    <text x="267" y="151" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="JetBrains Mono">x3</text>
    <text x="357" y="151" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="JetBrains Mono">x4</text>
    <path d="M123 146 H139 M213 146 H229 M303 146 H319" stroke="#53d7ff" stroke-width="3" stroke-linecap="round"/>
    <path d="M410 146 H454" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <path d="M442 134 L458 146 L442 158" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <rect x="456" y="112" width="58" height="68" rx="14" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <text x="485" y="141" text-anchor="middle" fill="#7ee787" font-size="17" font-family="Inter" font-weight="800">ML</text>
    <text x="485" y="161" text-anchor="middle" fill="#f7f4ea" font-size="10" font-family="Inter">model</text>
    <rect x="72" y="214" width="70" height="44" rx="10" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
    <rect x="162" y="214" width="70" height="44" rx="10" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
    <rect x="252" y="214" width="70" height="44" rx="10" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
    <rect x="342" y="214" width="70" height="44" rx="10" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
    <text x="107" y="242" text-anchor="middle" fill="#f7f4ea" font-size="13" font-family="JetBrains Mono">y1</text>
    <text x="197" y="242" text-anchor="middle" fill="#f7f4ea" font-size="13" font-family="JetBrains Mono">y2</text>
    <text x="287" y="242" text-anchor="middle" fill="#f7f4ea" font-size="13" font-family="JetBrains Mono">y3</text>
    <text x="377" y="242" text-anchor="middle" fill="#f7f4ea" font-size="13" font-family="JetBrains Mono">y4</text>
    <path d="M485 184 C485 220 448 236 416 236" stroke="#b692ff" stroke-width="4" fill="none" stroke-linecap="round"/>
    <path d="M428 224 L412 236 L428 248" fill="none" stroke="#b692ff" stroke-width="4" stroke-linecap="round"/>
    <text x="222" y="109" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">ordered sensor vectors</text>
    <text x="240" y="278" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">target predictions over time</text>
  </svg>
</div>

<div class="callout" style="margin-top: 8px; padding: 10px 16px;">Analogous to words in a sentence: each reading means more when the model can use the sequence before it.</div>

---

<div class="kicker">Model foundations</div>

# Encoding text

<div class="split">
  <div>
    <div class="big-word">Text becomes<br>vectors.</div>
    <p>To operate on text, the user's request is transformed into a series of vectors that can be fed to the model.</p>
    <p>Each vector is called an embedding. It can represent a word, part of a word, or a concept-like pattern.</p>
    <p>The encoding technique clusters similar meanings close together in vector space.</p>
  </div>
  <svg class="diagram" viewBox="0 0 560 320" role="img" aria-label="text encoded as embeddings and clustered in vector space">
    <rect x="24" y="28" width="512" height="264" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <text x="280" y="58" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Request to embeddings</text>
    <text x="280" y="82" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">meaning is represented as positions in vector space</text>
    <rect x="48" y="112" width="132" height="54" rx="12" fill="#181a20" stroke="#53d7ff"/>
    <text x="114" y="135" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="Inter" font-weight="800">User request</text>
    <text x="114" y="154" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">fix pump 7 soon</text>
    <path d="M190 139 H226" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
    <path d="M214 127 L230 139 L214 151" fill="none" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
    <rect x="240" y="104" width="90" height="70" rx="12" fill="rgba(83,215,255,0.12)" stroke="#53d7ff"/>
    <text x="285" y="129" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="Inter" font-weight="800">Encoder</text>
    <text x="285" y="149" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">text to vectors</text>
    <path d="M340 139 H376" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <path d="M364 127 L380 139 L364 151" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <rect x="392" y="100" width="118" height="78" rx="14" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <text x="451" y="126" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="Inter" font-weight="800">Embeddings</text>
    <text x="451" y="148" text-anchor="middle" fill="#a7adba" font-size="11" font-family="JetBrains Mono">[0.42, -0.18...]</text>
    <text x="451" y="164" text-anchor="middle" fill="#a7adba" font-size="11" font-family="JetBrains Mono">[0.40, -0.16...]</text>
    <line x1="64" y1="224" x2="506" y2="224" stroke="#343946" stroke-width="2"/>
    <line x1="92" y1="258" x2="92" y2="194" stroke="#343946" stroke-width="2"/>
    <circle cx="148" cy="220" r="7" fill="#53d7ff"/>
    <circle cx="164" cy="212" r="6" fill="#53d7ff"/>
    <circle cx="176" cy="229" r="6" fill="#53d7ff"/>
    <circle cx="310" cy="205" r="7" fill="#ffcb6b"/>
    <circle cx="328" cy="214" r="6" fill="#ffcb6b"/>
    <circle cx="338" cy="196" r="6" fill="#ffcb6b"/>
    <circle cx="438" cy="232" r="7" fill="#b692ff"/>
    <circle cx="454" cy="222" r="6" fill="#b692ff"/>
    <circle cx="466" cy="240" r="6" fill="#b692ff"/>
    <text x="162" y="252" text-anchor="middle" fill="#53d7ff" font-size="11" font-family="Inter" font-weight="800">repair</text>
    <text x="326" y="244" text-anchor="middle" fill="#ffcb6b" font-size="11" font-family="Inter" font-weight="800">failure</text>
    <text x="452" y="266" text-anchor="middle" fill="#b692ff" font-size="11" font-family="Inter" font-weight="800">maintenance</text>
  </svg>
</div>

<div class="callout" style="margin-top: 8px; padding: 10px 16px;">The model does not read raw text directly. It receives numeric vectors whose distances encode useful relationships.</div>

---

<div class="kicker">Model foundations</div>

# ML, deep learning, and Gen AI

<div class="grid-3">
  <div class="panel">
    <h4>Machine Learning</h4>
    <p>Often predicts, classifies, ranks, scores, detects, or recommends instead of creating a new artifact.</p>
  </div>
  <div class="panel">
    <h4>Deep Learning</h4>
    <p>Uses multi-layer neural networks to learn patterns in high-dimensional data such as language, images, and audio.</p>
  </div>
  <div class="panel">
    <h4>Generative AI</h4>
    <p>Creates new content: prose, code, images, summaries, plans, structured data, or explanations.</p>
  </div>
</div>

<div class="callout">Many real products combine both: ML retrieves or ranks information, then generative AI writes the user-facing answer.</div>

---

<div class="kicker">Model foundations</div>

# Proprietary versus open models

<div class="grid-2">
  <div class="panel">
    <h4>Proprietary model</h4>
    <p>The weights, training process, and serving system are private. Users access the model through an API or product interface.</p>
  </div>
  <div class="panel">
    <h4>Open-weight model</h4>
    <p>The trained weights are downloadable, so people can run or adapt the model, but the training source materials may remain unavailable.</p>
  </div>
</div>

<div class="callout">Unlike traditional open source software, an open-weight release usually does not include the actual model-making code, training data, evaluation setup, or recipe needed to recreate the model.</div>

<div class="stack">
  <div class="row"><div class="num">HF</div><p><span class="mini-title">Hugging Face</span>A common place to host, discover, test, and download open-weight models.</p></div>
  <div class="row"><div class="num">AI</div><p><span class="mini-title">Commercial frontier models</span>Leading hosted model weights are usually private, though providers may release selected smaller or specialized open-weight models.</p></div>
</div>

---

<div class="kicker">Model foundations</div>

# What is a large language model?

<div class="grid-3">
  <div class="panel">
    <h4>Trained on text</h4>
    <p>Learns relationships among words, concepts, formats, facts, and tasks from large text collections.</p>
  </div>
  <div class="panel">
    <h4>Encoded request</h4>
    <p>The user's request is transformed into embedding vectors before the model operates on it.</p>
  </div>
  <div class="panel">
    <h4>Many neural layers</h4>
    <p>Stacked neural-network layers transform those vectors and predict likely next tokens.</p>
  </div>
</div>

<svg class="diagram" style="height: 220px; margin-top: 8px;" viewBox="0 0 920 230" role="img" aria-label="large language model with text training, encoding, neural layers, and token output">
  <rect x="24" y="30" width="180" height="58" rx="12" fill="#181a20" stroke="#343946"/>
  <text x="114" y="54" text-anchor="middle" fill="#f7f4ea" font-size="16" font-family="Inter" font-weight="800">Large text corpus</text>
  <text x="114" y="74" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">documents, code, dialog</text>
  <path d="M216 59 H282" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
  <path d="M270 47 L286 59 L270 71" fill="none" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
  <rect x="302" y="30" width="156" height="58" rx="12" fill="rgba(83,215,255,0.12)" stroke="#53d7ff"/>
  <text x="380" y="54" text-anchor="middle" fill="#f7f4ea" font-size="16" font-family="Inter" font-weight="800">Train weights</text>
  <text x="380" y="74" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">learn text patterns</text>
  <path d="M380 94 V119" stroke="#ffcb6b" stroke-width="4" stroke-linecap="round"/>
  <path d="M368 107 L380 123 L392 107" fill="none" stroke="#ffcb6b" stroke-width="4" stroke-linecap="round"/>
  <rect x="24" y="145" width="144" height="58" rx="12" fill="#181a20" stroke="#343946"/>
  <text x="96" y="169" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="Inter" font-weight="800">User request</text>
  <text x="96" y="189" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">prompt + context</text>
  <path d="M180 174 H226" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
  <path d="M214 162 L230 174 L214 186" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
  <rect x="246" y="138" width="122" height="72" rx="14" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
  <text x="307" y="165" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="Inter" font-weight="800">Context Window</text>
  <text x="307" y="186" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">embedding vectors</text>
  <path d="M380 174 H430" stroke="#ffcb6b" stroke-width="4" stroke-linecap="round"/>
  <path d="M418 162 L434 174 L418 186" fill="none" stroke="#ffcb6b" stroke-width="4" stroke-linecap="round"/>
  <rect x="450" y="130" width="198" height="88" rx="16" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
  <text x="549" y="154" text-anchor="middle" fill="#f7f4ea" font-size="16" font-family="Inter" font-weight="800">LLM</text>
  <text x="549" y="175" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">multiple neural-net layers</text>
  <circle cx="502" cy="198" r="7" fill="rgba(255,203,107,0.12)" stroke="#ffcb6b"/>
  <circle cx="532" cy="198" r="7" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
  <circle cx="562" cy="198" r="7" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
  <circle cx="592" cy="198" r="7" fill="#181a20" stroke="#f7f4ea"/>
  <path d="M509 198 H525 M539 198 H555 M569 198 H585" stroke="#a7adba" stroke-width="2" stroke-linecap="round"/>
  <path d="M660 174 H720" stroke="#b692ff" stroke-width="4" stroke-linecap="round"/>
  <path d="M708 162 L724 174 L708 186" fill="none" stroke="#b692ff" stroke-width="4" stroke-linecap="round"/>
  <rect x="740" y="138" width="154" height="72" rx="14" fill="rgba(182,146,255,0.12)" stroke="#b692ff"/>
  <text x="817" y="165" text-anchor="middle" fill="#f7f4ea" font-size="16" font-family="Inter" font-weight="800">Next token</text>
  <text x="817" y="186" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">then the next one</text>
  <path d="M817 214 C817 224 307 224 307 214" stroke="#b692ff" stroke-width="3" fill="none" stroke-linecap="round"/>
  <path d="M295 226 L307 210 L319 226" fill="none" stroke="#b692ff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</svg>

<div class="callout" style="margin-top: 6px; padding: 8px 16px;">A practical mental model is text in, embeddings and neural layers inside, token stream out.</div>

---

<div class="kicker">Model foundations</div>

# Training versus runtime context

## Training is what the model learned then. Context is what the application gives it now.

<ul style="margin: 0 0 16px 24px; padding: 0;">
  <li>The user's query is answered by a combination of training data and context data.</li>
</ul>

<div class="grid-2">
  <div class="panel">
    <h4>Training</h4>
    <p>Changes the model weights. It happens before use, across large datasets, supervised examples, self-supervised learning, fine-tuning, RL, or RLHF.</p>
  </div>
  <div class="panel">
    <h4>Context</h4>
    <p>Does not change the model. It is information pasted into the current request.</p>
    <ul style="margin: 8px 0 0 18px; padding: 0;">
      <li>The user's request, the prompt, is part of context.</li>
      <li>Messages, files, retrieved chunks, tool results, rules, and instructions can also be context.</li>
    </ul>
  </div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Question: Is this supplier approved?<br>Context: approved supplier table row and policy clause.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Answer from context: supplier is approved for category A, not category B. Training data is not treated as source evidence.</div>
  </div>
</div>

---

<!-- _class: break -->

<div class="kicker">Training and tuning</div>

# How model behavior is shaped

<div class="accent-line"></div>

## Training, tuning, alignment, and specialization decide what the model tends to do before the app ever calls it.

---

<!-- _class: compact-bottom -->

<div class="kicker">Training and tuning</div>

# Training phases

## Modern assistant models are usually built in layers of training and post-training.

<div class="flow">
  <div class="node">Base pre-training<span>general language and world patterns</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Instruction tuning<span>user to assistant behavior</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Preference alignment<span>helpful, harmless, honest</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Specializations<span>tools, reasoning, domain tasks</span></div>
</div>

<div class="grid-4" style="margin-top: 16px;">
  <div class="panel"><h4>Learn language</h4><p>Predict text across massive unlabeled corpora.</p></div>
  <div class="panel"><h4>Learn behavior</h4><p>Follow instructions and produce chat-style answers.</p></div>
  <div class="panel"><h4>Learn preferences</h4><p>Move toward responses people rate as safer and more useful.</p></div>
  <div class="panel"><h4>Learn interactions</h4><p>Learn patterns such as making tool calls, reasoning steps, safety behavior, and domain workflows.</p></div>
</div>

<div class="callout footer-clearance" style="margin-top: 12px; padding: 9px 16px;">Common stack: base pre-training, instruction SFT, preference alignment, then tool, safety, reasoning, and optional domain tuning.</div>

---

<div class="kicker">Training and tuning</div>

# Core pre-training

<div class="grid-2">
  <div class="panel">
    <h4>Goal</h4>
    <p>Learn general language and world knowledge before the model is asked to behave like an assistant.</p>
  </div>
  <div class="panel">
    <h4>Objective</h4>
    <p>Usually next-token prediction on massive unlabeled text, also called causal language modeling.</p>
  </div>
</div>

<div class="grid-2" style="margin-top: 16px;">
  <div class="panel">
    <h4>Data</h4>
    <p>Web scrape, books, code, forums, reference text, and many other sources.</p>
  </div>
  <div class="panel">
    <h4>Behavior</h4>
    <p>Learns patterns, facts, style, and some emergent reasoning, but not explicit instruction-following yet.</p>
  </div>
</div>

<div class="callout">This is the foundational phase: more like autocompleting a huge internet corpus than behaving as a polished assistant.</div>

---

<div class="kicker">Training and tuning</div>

# Instruction tuning

<div class="split">
  <div>
    <div class="big-word">Base model<br>to chat.</div>
    <p>Before this phase, the base LLM predicts text continuations; it has not learned how to take turns in a conversation.</p>
    <p>A common technique is Supervised Fine-Tuning, or SFT: train on curated instruction, input, output examples.</p>
    <p>The target is a good assistant response, often formatted as user to assistant dialogs.</p>
  </div>
  <svg class="diagram" viewBox="0 0 560 300" role="img" aria-label="instruction tuning example">
    <rect x="28" y="42" width="504" height="220" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <text x="280" y="74" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Examples teach conversation format</text>
    <rect x="64" y="116" width="176" height="70" rx="12" fill="#181a20" stroke="#53d7ff"/>
    <text x="152" y="145" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="Inter" font-weight="800">User</text>
    <text x="152" y="166" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">Summarize this text</text>
    <path d="M252 151 H306" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <path d="M294 139 L310 151 L294 163" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <rect x="324" y="116" width="176" height="70" rx="12" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <text x="412" y="145" text-anchor="middle" fill="#f7f4ea" font-size="15" font-family="Inter" font-weight="800">Assistant target</text>
    <text x="412" y="166" text-anchor="middle" fill="#a7adba" font-size="11" font-family="Inter">A short summary</text>
    <text x="280" y="222" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">human-written and model-generated examples are filtered and formatted</text>
  </svg>
</div>

<div class="callout" style="margin-top: 8px; padding: 10px 16px;">Instruction tuning turns a base model into something that behaves more like ChatGPT than an unconstrained text generator.</div>

---

<div class="kicker">Training and tuning</div>

# Reinforcement learning from human feedback

<div class="grid-3">
  <div class="panel"><h4>Goal</h4><p>Align responses with human preferences such as helpful, harmless, honest, concise, safe, and on-task.</p></div>
  <div class="panel"><h4>Data</h4><p>Humans compare candidate responses to the same prompt and rank what they prefer.</p></div>
  <div class="panel"><h4>Effect</h4><p>Shapes style, tone, and behavior more than it directly adds factual knowledge.</p></div>
</div>

<div class="flow" style="margin-top: 26px;">
  <div class="node">SFT model<span>starting policy</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Ranked responses<span>preference labels</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Reward model<span>predicts rankings</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">RL update<span>PPO or variants</span></div>
</div>

<div class="callout">Variants such as DPO, IPO, and RLAIF target the same preference-alignment niche with different mechanics. If done poorly, preference training can push a model toward excessive agreement, even when the user is wrong.</div>

---

<div class="kicker">Training and tuning</div>

# Tool-use training

<div class="split">
  <div>
    <div class="big-word">Answers can<br>be actions.</div>
    <p>Tool-use training teaches when and how to call APIs, databases, code executors, or other software tools.</p>
    <p>It is specialized instruction tuning where the target output is a structured tool call instead of plain prose.</p>
  </div>
  <svg class="diagram" viewBox="0 0 560 300" role="img" aria-label="tool use training flow">
    <rect x="28" y="36" width="504" height="228" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <text x="280" y="68" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Curated tool traces become examples</text>
    <rect x="54" y="116" width="112" height="62" rx="12" fill="#181a20" stroke="#53d7ff"/>
    <text x="110" y="143" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="Inter" font-weight="800">Prompt</text>
    <text x="110" y="162" text-anchor="middle" fill="#a7adba" font-size="10" font-family="Inter">needs data</text>
    <path d="M178 147 H220" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
    <path d="M208 135 L224 147 L208 159" fill="none" stroke="#53d7ff" stroke-width="4" stroke-linecap="round"/>
    <rect x="236" y="106" width="130" height="82" rx="12" fill="rgba(83,215,255,0.12)" stroke="#53d7ff"/>
    <text x="301" y="137" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="Inter" font-weight="800">Tool call</text>
    <text x="301" y="158" text-anchor="middle" fill="#a7adba" font-size="10" font-family="Inter">function name</text>
    <text x="301" y="174" text-anchor="middle" fill="#a7adba" font-size="10" font-family="Inter">structured arguments</text>
    <path d="M378 147 H420" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <path d="M408 135 L424 147 L408 159" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
    <rect x="436" y="116" width="74" height="62" rx="12" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
    <text x="473" y="143" text-anchor="middle" fill="#f7f4ea" font-size="14" font-family="Inter" font-weight="800">Result</text>
    <text x="473" y="162" text-anchor="middle" fill="#a7adba" font-size="10" font-family="Inter">answer</text>
    <text x="280" y="220" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">preference training can reward correct tool choice</text>
    <text x="280" y="238" text-anchor="middle" fill="#a7adba" font-size="12" font-family="Inter">and discourage invented outputs</text>
  </svg>
</div>

<div class="callout" style="margin-top: 8px; padding: 10px 16px;">The base mechanics are similar to instruction tuning; the semantics of the target output are different. Less advanced models may not support tool calling because this training phase was skipped.</div>

---

<div class="kicker">Training and tuning</div>

# Reasoning-oriented training

<div class="grid-2">
  <div class="panel"><h4>Chain-of-thought SFT</h4><p>Examples include step-by-step reasoning in the target output.</p></div>
  <div class="panel"><h4>Process supervision</h4><p>Intermediate steps are rated or corrected, not just final answers.</p></div>
</div>

<div class="grid-2" style="margin-top: 16px;">
  <div class="panel"><h4>Reasoning RL</h4><p>Rewards can reflect answer correctness and quality of intermediate traces.</p></div>
  <div class="panel"><h4>Think first</h4><p>Training and architecture can separate internal reasoning from the external answer.</p></div>
</div>

<div class="callout">Reasoning training often sits on top of instruction tuning and alignment: first make a good assistant, then push it to be more systematic. It can make the model more powerful, but also slower.</div>

---

<div class="kicker">Training and tuning</div>

# Domain and task fine-tuning

<div class="split">
  <div>
    <div class="big-word">Optional<br>specialization.</div>
    <p>Domain fine-tuning adapts a model for finance, code, legal, medical, customer support, or a specific workflow.</p>
    <p>It can happen after base pre-training, after instruction tuning, or as a small adapter on an aligned chat model.</p>
  </div>
  <div class="stack">
    <div class="row"><div class="num">SFT</div><p><span class="mini-title">Domain-specific examples</span>Curated tasks and target outputs from the target field.</p></div>
    <div class="row"><div class="num">PEFT</div><p><span class="mini-title">LoRA and adapters</span>Parameter-efficient tuning for narrow workflows.</p></div>
    <div class="row"><div class="num">RAG</div><p><span class="mini-title">RAG-aware behavior</span>Train or evaluate the model to use retrieved documents well.</p></div>
  </div>
</div>

<div class="callout">This is separate from alignment: specialization teaches what to be good at; alignment shapes how the model should behave.</div>

---

<div class="kicker">Training and tuning</div>

# Fine-tuning for patterns

<div class="grid-2">
  <div class="panel">
    <h4>What it is good at</h4>
    <p>Fine-tuning teaches response patterns: terminology, formats, workflows, escalation rules, citation habits, and how to handle domain tasks.</p>
  </div>
  <div class="panel">
    <h4>What it is poor at</h4>
    <p>Facts in weights are hard to inspect, cite, update, remove, or reconcile with newer context.</p>
  </div>
</div>

<div class="grid-3" style="margin-top: 18px;">
  <div class="panel tight"><h4>Can learn some facts</h4><p>Repeated facts may become part of model behavior, but recall is not guaranteed.</p></div>
  <div class="panel tight"><h4>Use RAG or tools for facts</h4><p>Policies, prices, procedures, product facts, and legal text should come from retrievable sources.</p></div>
  <div class="panel tight"><h4>Best mix</h4><p>Fine-tune the behavior. Retrieve the evidence. Let tools supply current state.</p></div>
</div>

<div class="callout">Use fine-tuning to teach how to work in the domain; use RAG, databases, and tools for knowledge that must be accurate, cited, or updated.</div>

---

<div class="kicker">Training and tuning</div>

# RAG-aware tuning teaches evidence use

<div class="grid-2">
  <div class="panel">
    <h4>Retrieval-grounded SFT</h4>
    <p>Train on examples shaped as user question plus retrieved context, with a grounded answer as the target.</p>
  </div>
  <div class="panel">
    <h4>Retriever tuning</h4>
    <p>Tune embeddings or search so domain queries retrieve the right chunks, names, acronyms, and clauses.</p>
  </div>
</div>

<div class="grid-2" style="margin-top: 16px;">
  <div class="panel">
    <h4>Reranker tuning</h4>
    <p>Train a model to put the most useful evidence near the top of the context.</p>
  </div>
  <div class="panel">
    <h4>Query and tool tuning</h4>
    <p>Teach when retrieval is needed, how to write better searches, and when to abstain or ask for more context.</p>
  </div>
</div>

<div class="callout">The goal is not to memorize the document store. The goal is to retrieve better context and answer from the evidence supplied.</div>

---

<!-- _class: break -->

<div class="kicker">Runtime behavior</div>

# What happens during a request

<div class="accent-line"></div>

## Runtime choices determine context size, latency, cost, response shape, and how much progress the user can see.

---

<!-- _class: compact-bottom -->

<div class="kicker">Runtime behavior</div>

# Inference generates one output token at a time

<div class="flow">
  <div class="node">Input tokens<span>prompt and context</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Predict one token<span>scores across vocabulary</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Append token<span>new context grows</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Repeat until done<span>stop, limit, or tool call</span></div>
</div>

<div class="grid-3" style="margin-top: 16px;">
  <div class="metric"><div class="label">Goal</div><div class="value">next token</div><p class="small">Produce one token after another until the answer, stop signal, or tool call is complete.</p></div>
  <div class="metric"><div class="label">GPU work</div><div class="value">tensors</div><p class="small">GPUs parallelize matrix and tensor operations across many cores.</p></div>
  <div class="metric"><div class="label">Rough scale</div><div class="value">140B</div><p class="small">A dense 70B model is roughly 140B weight operations per generated token, plus context overhead.</p></div>
</div>

<div class="callout footer-clearance">A 100-token answer from that rough 70B example can mean around 14 trillion weight operations. Attention adds context-length work; batching improves GPU use but may queue requests; KV cache avoids recomputing prior tokens; serving adds routing, sampling, and memory overhead.</div>

---

<div class="kicker">Runtime behavior</div>

# Typical input and output sizes

<h2 style="margin: 0 0 14px; max-width: 1040px;">Token counts vary by model, language, code, formatting, history, and retrieved context.</h2>

<div class="grid-3">
  <div class="metric"><div class="label">Short chat</div><div class="value">100-1K in</div><p class="small">A direct question with little history often returns 100-500 output tokens.</p></div>
  <div class="metric"><div class="label">RAG answer</div><div class="value">2K-20K in</div><p class="small">Retrieved documents dominate the input; output is often 300-1.5K tokens.</p></div>
  <div class="metric"><div class="label">Code or docs</div><div class="value">10K-100K+ in</div><p class="small">Files, logs, and tool results dominate input; output is often 500-5K tokens.</p></div>
</div>

<div class="grid-2" style="margin-top: 14px;">
  <div class="panel">
    <h4>Example input: 4,200 tokens</h4>
    <p>700 system and rules, 300 user prompt, 700 conversation history, 2,500 retrieved context.</p>
  </div>
  <div class="panel">
    <h4>Example output: 650 tokens</h4>
    <p>A concise answer with citations or steps. Longer reports, code patches, and tool loops can be much larger.</p>
  </div>
</div>

<div class="callout" style="margin-top: 12px; padding: 10px 16px;">Input tokens mostly shape cost and context quality. Output tokens shape latency because each new token requires another model step.</div>

---

<!-- _class: compact-bottom -->

<div class="kicker">Runtime behavior</div>

# Request parts

<div class="stack">
  <div class="row"><div class="num">S</div><p><span class="mini-title">System prompt</span>Role, rules, style, safety boundaries, source restrictions.</p></div>
  <div class="row"><div class="num">H</div><p><span class="mini-title">History</span>Prior turns, summaries, forks, tool results, decisions.</p></div>
  <div class="row"><div class="num">C</div><p><span class="mini-title">Context</span>Files, retrieved chunks, business rules, product data.</p></div>
  <div class="row"><div class="num">U</div><p><span class="mini-title">User message</span>The latest request, correction, instruction, or question.</p></div>
  <div class="row"><div class="num">F</div><p><span class="mini-title">Output format</span>Markdown, structured output, citation requirements, schema, DSL.</p></div>
</div>

<div class="artifact footer-clearance">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">System: answer only from policy. Context: travel clause. User: can I book business class?</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Allowed only for flights over 6 hours with director approval, citing the supplied travel clause.</div>
  </div>
</div>

---

<div class="kicker">Runtime behavior</div>

# Prompt engineering

<div class="grid-3">
  <div class="panel"><h4>Zero-shot</h4><p>Ask directly with no example.</p></div>
  <div class="panel"><h4>One-shot</h4><p>Give one example to establish the pattern.</p></div>
  <div class="panel"><h4>Few-shot</h4><p>Give several examples for classification, extraction, formatting, or style.</p></div>
</div>

<div class="grid-2" style="margin-top: 18px;">
  <div class="panel">
    <h4>Chain-of-thought prompting</h4>
    <p>Can help multi-step tasks, but visible reasoning should not be treated as proof of the hidden process.</p>
  </div>
  <div class="panel">
    <h4>Tree-of-thought prompting</h4>
    <p>Explores multiple candidate paths, useful for planning and search, usually at higher cost.</p>
  </div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Few-shot classifier: invoice text plus two examples of approved and rejected expense labels.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Label: needs review. Reason: meal amount exceeds policy threshold and attendee list is missing.</div>
  </div>
</div>

---

<div class="kicker">Runtime behavior</div>

# Markdown is plain text with formatting rules

## A Markdown document is a simple text file plus lightweight conventions that tell apps how to render structure.

<div class="grid-3">
  <div class="panel">
    <h4>Headings</h4>
    <p><span class="mono">### Section title</span> creates a third-level heading.</p>
  </div>
  <div class="panel">
    <h4>Bold text</h4>
    <p><span class="mono">**important**</span> marks text for bold emphasis.</p>
  </div>
  <div class="panel">
    <h4>Bullets</h4>
    <p><span class="mono">- item</span> starts a list item.</p>
  </div>
</div>

<div class="callout cyan">The file stays readable as plain text, but can render as formatted content in a chat, wiki, documentation site, or slide deck.</div>

---

<div class="kicker">Runtime behavior</div>

# Conversation simulation

## The model is stateless and is not keeping track of the messages exchanged with a caller. Continuity comes from the application resending or summarizing earlier information.

<div class="grid-3">
  <div class="panel"><h4>Conversation history</h4><p>Stored prior user messages, assistant responses, tool calls, results, and summaries.</p></div>
  <div class="panel"><h4>Application state</h4><p>Files, workflow progress, user preferences, retrieved documents, and decisions.</p></div>
  <div class="panel"><h4>Forking</h4><p>Starting a new run from a selected earlier point, sharing a common trunk then branching.</p></div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Turn 1: analyze renewal contract. Turn 2: make it shorter. App resends summary, source terms, and previous answer.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">The model can shorten the same contract analysis because the relevant state is included again.</div>
  </div>
</div>

---

<div class="kicker">Runtime behavior</div>

# Streaming displays tokens as they are generated

<div class="grid-2">
  <div class="panel">
    <h4>Request and response API</h4>
    <p>The caller sends one request and waits until the full response is ready.</p>
  </div>
  <div class="panel">
    <h4>Streaming API</h4>
    <p>The caller receives partial events as tokens, tool updates, or status messages become available.</p>
  </div>
</div>

<svg class="diagram" viewBox="0 0 900 160" role="img" aria-label="streaming generation">
  <rect x="60" y="48" width="780" height="64" rx="12" fill="#181a20" stroke="#343946"/>
  <g font-family="JetBrains Mono" font-size="20" font-weight="600">
    <text x="100" y="88" fill="#7ee787">The</text>
    <text x="160" y="88" fill="#53d7ff"> answer</text>
    <text x="270" y="88" fill="#ffcb6b"> appears</text>
    <text x="390" y="88" fill="#b692ff"> as</text>
    <text x="445" y="88" fill="#ff7a6e"> each</text>
    <text x="525" y="88" fill="#7ee787"> token</text>
    <text x="625" y="88" fill="#53d7ff"> is</text>
    <text x="670" y="88" fill="#f7f4ea"> produced.</text>
  </g>
</svg>

<div class="callout">It is not that the complete answer is ready and the server sends it slowly. Each next token requires real-time computation.</div>

---

<div class="kicker">Runtime behavior</div>

# Token counts drive cost, latency, and limits

<div class="grid-4">
  <div class="metric"><div class="label">Input</div><div class="value">prompt</div><p class="small">System, history, context, files.</p></div>
  <div class="metric"><div class="label">Cached</div><div class="value">prefix</div><p class="small">Repeated recent input may cost less.</p></div>
  <div class="metric"><div class="label">Output</div><div class="value">answer</div><p class="small">Visible response tokens.</p></div>
  <div class="metric"><div class="label">Reasoning</div><div class="value">hidden</div><p class="small">Extra work before the final answer.</p></div>
</div>

<div class="grid-2" style="margin-top: 22px;">
  <div class="panel">
    <h4>Non-reasoning models</h4>
    <p>Cost is often estimated from expected input size and output size.</p>
  </div>
  <div class="panel">
    <h4>Reasoning models</h4>
    <p>Hidden reasoning tokens can dominate cost and add latency, even when the visible answer is short.</p>
  </div>
</div>

---

<div class="kicker">Runtime behavior</div>

# Temperature controls token sampling

## Temperature changes sampling randomness; it does not make unsupported facts more reliable.

<div class="split">
  <div>
    <p>The service chooses among likely next tokens. Temperature controls how willing it is to pick a less probable token.</p>
    <p>Lower temperature makes output more predictable and grounded. Higher temperature makes output more varied, creative, or surprising.</p>
  </div>
  <div>
    <div class="meter"><span style="width: 22%; background: var(--green);"></span></div>
    <p class="small">Low: deterministic-feeling, safer for exact tasks</p>
    <div class="meter"><span style="width: 62%; background: var(--amber);"></span></div>
    <p class="small">Medium: variation with coherence</p>
    <div class="meter"><span style="width: 100%; background: var(--coral);"></span></div>
    <p class="small">High: fanciful, hallucinated, or incoherent if pushed too far</p>
  </div>
</div>

<div class="artifact footer-clearance" style="margin-top: 12px;">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Task: extract invoice total and due date from supplied text. Set low temperature for repeatable extraction.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Stable fields: total = 4,820.00, due date = 2026-07-15. Missing fields stay blank instead of invented.</div>
  </div>
</div>

---

<div class="kicker">Runtime behavior</div>

# Showing task progress

<div class="grid-2">
  <div class="panel">
    <h4>Reasoning summary</h4>
    <p>A visible summary of progress, assumptions, or plan shape. Useful, but not proof of the hidden path.</p>
  </div>
  <div class="panel">
    <h4>Work trace</h4>
    <p>Status updates, tool requests, tool results, verification notes, retries, errors, and final response.</p>
  </div>
</div>

<div class="callout cyan">AG-UI is an open, event-based protocol for connecting agent backends to user-facing applications and showing progress, tool activity, interruptions, and UI-relevant updates.</div>

<div class="artifact footer-clearance">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Agent task: inspect three invoices, request approval, then draft an exception summary.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Progress events: retrieved files, found policy gap, waiting for approval, generated draft with unresolved items.</div>
  </div>
</div>

---

<!-- _class: break -->

<div class="kicker">Evaluation and grounding</div>

# How outputs earn trust

<div class="accent-line"></div>

## Fluent text is not enough; the application needs evidence, tests, grading logic, and clear limits on factual claims.

---

<!-- _class: compact-bottom -->

<div class="kicker">Evaluation and grounding</div>

# Verification is required for reliable answers

<div class="quote">A fluent answer can still be wrong.</div>

<div class="grid-3" style="margin-top: 14px;">
  <div class="panel"><h4>Use context rules</h4><p>Tell the model to answer only from provided context.</p></div>
  <div class="panel"><h4>Allow uncertainty</h4><p>Tell it that insufficient information is an acceptable answer.</p></div>
  <div class="panel"><h4>Ask followups</h4><p>Allow the LLM to turn missing context into questions instead of forced answers.</p></div>
  <div class="panel"><h4>Extract first</h4><p>Ask for a citation or presence of something objective before concluding.</p></div>
  <div class="panel"><h4>Validation tool</h4><p>A compiler, linter or other program can give valuable feedback to the LLM.</p></div>
  <div class="panel"><h4>LLM Eval</h4><p>An LLM call is the semantic judge.</p></div>
</div>

<div class="artifact footer-clearance">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Claim: this code builds. Evidence request: run build and report the command result.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Verified: build passed. Or blocked: build failed with import error and the answer cannot claim success.</div>
  </div>
</div>

---

<div class="kicker">Evaluation and grounding</div>

# Evals test model behavior

## An eval is a structured test: inputs, model output, and defined grading logic that produces a score or pass/fail.

<div class="flow" style="margin-top: 18px;">
  <div class="node">Inputs<span>prompts, context, tasks</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Model output<span>answer, code, tool call</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Grade<span>score or pass/fail</span></div>
</div>

<div class="grid-3">
  <div class="panel">
    <h4>Test data</h4>
    <p>Prompts, context, expected behavior, examples, or tasks that exercise the model.</p>
  </div>
  <div class="panel">
    <h4>Model under test</h4>
    <p>The model, prompt, tools, retrieval, and app logic being evaluated together.</p>
  </div>
  <div class="panel">
    <h4>Grader</h4>
    <p>Exact match, code validation, human review, or an LLM judge against a rubric.</p>
  </div>
</div>

<div class="callout">The grader does not have to be an LLM. LLM-as-judge is one pattern, especially for open-ended tasks.</div>

---

<div class="kicker">Evaluation and grounding</div>

# Evals can test releases or guide generation

<div class="grid-2">
  <div class="panel">
    <h4>QA before release</h4>
    <p>Run a fixed suite against prompts, tools, retrieval, and app logic to catch regressions before shipping.</p>
  </div>
  <div class="panel">
    <h4>Feedback during generation</h4>
    <p>Use a grader while the system is working, then retry, revise, choose a candidate, or ask for missing context.</p>
  </div>
</div>

<div class="grid-2" style="margin-top: 18px;">
  <div class="panel">
    <h4>Program feedback</h4>
    <p>Unit tests, linters, compilers, type checkers, and validators can tell the LLM what failed and what to fix.</p>
  </div>
  <div class="panel">
    <h4>Semantic feedback</h4>
    <p>An LLM judge can compare competing designs, answers, or plans and choose the one that best matches a rubric.</p>
  </div>
</div>

<div class="callout">In products, evals are not only final inspection. They can be part of the loop that improves the generated result.</div>

---

<div class="kicker">Evaluation and grounding</div>

# Graders can be tools or models

<div class="grid-2">
  <div class="panel">
    <h4>Deterministic validators</h4>
    <p>Linters, type checkers, unit tests, security scanners, regex checks, and schema validation are eval graders when they produce pass/fail or score.</p>
  </div>
  <div class="panel">
    <h4>LLM-as-judge</h4>
    <p>Use an LLM judge when there is no single ground truth, such as explanation quality, helpfulness, coherence, relevance, tone, or safety.</p>
  </div>
</div>

<div class="grid-2" style="margin-top: 18px;">
  <div class="panel">
    <h4>Code generation example</h4>
    <p>Run ESLint, mypy, ruff, a compiler, or unit tests on generated code and fail above a chosen severity.</p>
  </div>
  <div class="panel">
    <h4>Mature eval suites mix signals</h4>
    <p>Hard checks measure correctness and policy. LLM judges handle semantic quality that is hard to encode as pure rules.</p>
  </div>
</div>

<div class="callout">A linter can be part of an eval, or the whole eval, when its result is the grading logic.</div>

---

<div class="kicker">Evaluation and grounding</div>

# Evals combine deterministic checks and judgment

<div class="grid-2">
  <div class="panel">
    <div class="tag green">Objective</div>
    <h4>Machine-checkable truth</h4>
    <p>Compiler, linter, type checker, schema validator, unit test, integration test, browser check, static analysis, and security scan.</p>
    <p><strong>Strength:</strong> repeatable and fast. <strong>Limit:</strong> only catches what it knows how to measure.</p>
  </div>
  <div class="panel">
    <div class="tag violet">Subjective</div>
    <h4>Judgment and quality</h4>
    <p>Human review, product review, architecture review, rubric-based LLM-as-judge, and pair comparison.</p>
    <p><strong>Strength:</strong> catches usefulness and taste. <strong>Limit:</strong> needs calibration and examples.</p>
  </div>
</div>

<div class="callout">The best eval set mixes both: hard gates for correctness, rubrics for quality, and examples of known failure modes the system must stop repeating.</div>

---

<div class="kicker">Evaluation and grounding</div>

# Grounding separates creative output from factual claims

<div class="grid-3">
  <div class="panel">
    <h4 class="good">Useful invention</h4>
    <p>Brainstorming, examples, metaphors, options, sketches, drafts.</p>
  </div>
  <div class="panel">
    <h4 class="bad">Exact truth</h4>
    <p>Legal facts, numbers, citations, private records, business rules, source claims.</p>
  </div>
  <div class="panel">
    <h4 class="warn">Grounding</h4>
    <p>Connect the answer to supplied context, retrieved evidence, tool results, or sources.</p>
  </div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Claim: the refund exception is allowed. Sources: policy text, order record, support note.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Grounded answer cites the policy clause and order status; unsupported customer intent is left as unknown.</div>
  </div>
</div>

<div class="callout footer-clearance">A practical tactic: require citations or source links for important claims, then verify that the source actually supports the statement.</div>

---

<div class="kicker">Evaluation and grounding</div>

# Model explanations are not proof of internal reasoning

<div class="grid-2">
  <div class="panel">
    <h4>What the model can do</h4>
    <p>Generate a plausible explanation of why an answer might be correct.</p>
  </div>
  <div class="panel">
    <h4>What it cannot prove</h4>
    <p>That the explanation is the real cause of the answer or hidden computation.</p>
  </div>
</div>

<div class="callout">Interpretability is active research. Techniques such as feature mapping, sparse autoencoders, circuit tracing, and influence functions can reveal clues, but this is not a solved product feature.</div>

---

<!-- _class: break -->

<div class="kicker">Retrieval and tools</div>

# How apps supply facts and actions

<div class="accent-line"></div>

## Retrieval, attachments, tools, and MCP turn the model from a text generator into a governed application component.

---

<div class="kicker">Retrieval and tools</div>

# The model does not open files by itself

<div class="flow">
  <div class="node">Attachment<span>UI concept: user adds a file</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Extraction<span>parse PDF, doc, image, text</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">File markers<span>show starts, ends, labels</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Prompt context<span>sent with the request</span></div>
</div>

<div class="callout">The model usually runs on a remote server. The client or app must extract and send any file contents. More context can increase cost, latency, and confusion.</div>

---

<div class="kicker">Retrieval and tools</div>

# RAG retrieves context ahead of the request

<div class="flow">
  <div class="node">User asks<span>question or task</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Search documents<span>find relevant sources</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Add context<span>attach retrieved text</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Model answers<span>using supplied context</span></div>
</div>

<div class="grid-3">
  <div class="panel">
    <h4>Why it helps</h4>
    <p>Instead of making the user pick the document, the app searches and adds the likely useful text to the request.</p>
  </div>
  <div class="panel">
    <h4>Full-text search</h4>
    <p>Finds literal terms, names, phrases, IDs, and exact matches inside documents.</p>
  </div>
  <div class="panel">
    <h4>Semantic search</h4>
    <p>Uses embeddings to find nearby meanings, even when the exact words are different.</p>
  </div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Question: what is the refund window for enterprise plans?</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Retriever adds billing policy paragraph. Model answers from that paragraph and cites the policy section.</div>
  </div>
</div>

---

<div class="kicker">Retrieval and tools</div>

# Text embeddings make meaning searchable

<div class="split">
  <div>
    <p>An embedding is a numeric vector that represents the meaning of text.</p>
    <p>A useful mental model is that a paragraph can become one vector by combining its token vectors and normalizing the sum.</p>
    <p>Classic analogy: king - man + woman = queen.</p>
    <p>The app embeds the user prompt, compares vector distance, and retrieves the closest meanings as context.</p>
  </div>
  <svg class="diagram" viewBox="0 0 560 320" role="img" aria-label="paragraph embedding and vector distance">
    <rect x="28" y="28" width="504" height="264" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <text x="280" y="64" text-anchor="middle" fill="#f7f4ea" font-size="18" font-family="Inter" font-weight="800">Paragraph to one vector</text>
    <g font-family="Inter">
      <rect x="58" y="104" width="86" height="42" rx="10" fill="#181a20" stroke="#53d7ff"/>
      <rect x="156" y="104" width="86" height="42" rx="10" fill="#181a20" stroke="#53d7ff"/>
      <rect x="254" y="104" width="86" height="42" rx="10" fill="#181a20" stroke="#53d7ff"/>
      <text x="101" y="130" text-anchor="middle" fill="#f7f4ea" font-size="12" font-weight="800">token</text>
      <text x="199" y="130" text-anchor="middle" fill="#f7f4ea" font-size="12" font-weight="800">token</text>
      <text x="297" y="130" text-anchor="middle" fill="#f7f4ea" font-size="12" font-weight="800">token</text>
      <path d="M352 125 H414" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
      <path d="M402 113 L418 125 L402 137" fill="none" stroke="#7ee787" stroke-width="4" stroke-linecap="round"/>
      <rect x="430" y="98" width="82" height="54" rx="12" fill="rgba(126,231,135,0.10)" stroke="#7ee787"/>
      <text x="471" y="121" text-anchor="middle" fill="#f7f4ea" font-size="13" font-weight="800">paragraph</text>
      <text x="471" y="139" text-anchor="middle" fill="#a7adba" font-size="11">vector</text>
      <circle cx="190" cy="226" r="9" fill="#53d7ff"/>
      <circle cx="252" cy="208" r="9" fill="#7ee787"/>
      <circle cx="376" cy="232" r="9" fill="#ffcb6b"/>
      <circle cx="411" cy="190" r="9" fill="#ff7a6e"/>
      <path d="M190 226 L252 208" stroke="#7ee787" stroke-width="2" stroke-dasharray="5 5"/>
      <text x="216" y="192" text-anchor="middle" fill="#a7adba" font-size="12">closest meaning</text>
      <text x="364" y="260" text-anchor="middle" fill="#a7adba" font-size="12">farther meanings</text>
    </g>
  </svg>
</div>

<div class="callout">Vector distance lets the system retrieve text that is meaningfully close to the prompt, then add that text to the request.</div>

---

<div class="kicker">Retrieval and tools</div>

# Vector databases store searchable meaning

<div class="grid-3">
  <div class="panel">
    <h4>Definition</h4>
    <p>A vector database is a database that makes storing vectors and searching by vector distance easy.</p>
  </div>
  <div class="panel">
    <h4>Stored record</h4>
    <p>Embeddings, source text, document IDs, chunk metadata, filters, and sometimes full-text indexes.</p>
  </div>
  <div class="panel">
    <h4>Search behavior</h4>
    <p>The app embeds the query, finds nearby chunk vectors, applies filters, then sends selected source text to the model.</p>
  </div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Query: refund exception policy. Filters: product = support, permission = manager.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Top chunks: policy 4.2 score .82, order-status note score .77, escalation guide score .73.</div>
  </div>
</div>

<div class="callout footer-clearance">Common choices include hosted vector services, open source vector databases, and Postgres extensions. The decision depends on scale, filtering, operations, and existing data systems.</div>

---

<div class="kicker">Retrieval and tools</div>

# Chunking splits documents into searchable passages

<div class="grid-3">
  <div class="panel">
    <h4>Chunk</h4>
    <p>A smaller piece of a document prepared for indexing, retrieval, and prompt assembly.</p>
  </div>
  <div class="panel">
    <h4>Chunking strategy</h4>
    <p>Rules for size, overlap, headings, metadata, permissions, and nearby relationships.</p>
  </div>
  <div class="panel">
    <h4>Failure mode</h4>
    <p>Split the claim from its explanation and retrieval returns fragments too vague to ground the answer.</p>
  </div>
</div>

<div class="flow" style="margin-top: 24px;">
  <div class="node">Document<span>policy, code, transcript</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Chunks<span>sections with metadata</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Embeddings<span>one vector per chunk</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Retrieval<span>best matches become context</span></div>
</div>

<div class="callout">The best chunking strategy follows the shape of the source: sections for policies, functions for code, turns for transcripts, slides for decks. Beware that a chunk on its own could have a different meaning than combined with other chunks.</div>

---

<div class="kicker">Retrieval and tools</div>

# Reranking is second-pass retrieval

<div class="flow">
  <div class="node">Broad search<span>keyword, semantic, hybrid, filters</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Candidate chunks<span>more than you want to send</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Reranker<span>score query versus candidate</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Final context<span>smaller, more precise set</span></div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">First-stage retrieval returns 30 chunks, including old policy drafts and duplicate meeting notes.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Reranker keeps the current policy clause, approval matrix, and audit note as the final context.</div>
  </div>
</div>

<div class="callout footer-clearance">Reranking adds latency and cost, so it is most useful when first-stage retrieval returns noisy or overlapping candidates.</div>

---

<div class="kicker">Retrieval and tools</div>

# Dynamic context tools

<div class="grid-2">
  <div class="panel">
    <h4>App-provided context</h4>
    <p>The application assembles the user prompt, context files, and RAG results before the model is called.</p>
  </div>
  <div class="panel">
    <h4>LLM-requested context</h4>
    <p>The model can return a special response asking for more information based on its reasoning.</p>
  </div>
</div>

<div class="flow" style="margin-top: 26px;">
  <div class="node">Initial request<span>prompt plus known context</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Need more info<span>special context request</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Retrieve context<span>search, file, tool, record</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Restart request<span>additional context included</span></div>
</div>

<div class="callout">On-demand context lets the system avoid guessing when a targeted retrieval step can supply the missing information.</div>

---

<div class="kicker">Retrieval and tools</div>

# Client action tools

<div class="grid-2">
  <div class="panel">
    <h4>Action</h4>
    <p>Something the product can do: search, calculate, schedule, read, write, update, transform, generate.</p>
  </div>
  <div class="panel">
    <h4>Tool</h4>
    <p>The technical interface that lets the model request an action with arguments and receive a result.</p>
  </div>
</div>

<div class="flow">
  <div class="node">Tool request<span>model asks</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">App validates<span>permissions, schema, limits</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Tool call<span>software executes</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Tool result<span>new context</span></div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">User asks: schedule a follow-up with the account owner next Tuesday.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Model requests calendar tool with attendee, date, title. App validates permission before creating the event.</div>
  </div>
</div>

---

<div class="kicker">Retrieval and tools</div>

# Tool call execution flow

<svg class="diagram" style="height: 430px; margin-top: 2px;" viewBox="0 0 1050 430" role="img" aria-label="client server llm tool call sequence">
  <defs>
    <marker id="seq-arrow" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto">
      <path d="M0,0 L8,4 L0,8 Z" fill="#53d7ff"/>
    </marker>
    <marker id="seq-arrow-green" markerWidth="8" markerHeight="8" refX="7" refY="4" orient="auto">
      <path d="M0,0 L8,4 L0,8 Z" fill="#7ee787"/>
    </marker>
  </defs>
  <g font-family="Inter">
    <rect x="34" y="28" width="982" height="388" rx="18" fill="rgba(255,255,255,0.026)" stroke="#343946"/>
    <g font-weight="800" font-size="17" fill="#f7f4ea">
      <text x="145" y="68" text-anchor="middle">Client</text>
      <text x="385" y="68" text-anchor="middle">App server</text>
      <text x="665" y="68" text-anchor="middle">LLM</text>
      <text x="905" y="68" text-anchor="middle">Tool</text>
    </g>
    <g stroke="#6f7b8f" stroke-width="2" stroke-dasharray="6 7">
      <line x1="145" y1="84" x2="145" y2="388"/>
      <line x1="385" y1="84" x2="385" y2="388"/>
      <line x1="665" y1="84" x2="665" y2="388"/>
      <line x1="905" y1="84" x2="905" y2="388"/>
    </g>
    <g stroke="#53d7ff" stroke-width="2.5" marker-end="url(#seq-arrow)">
      <line x1="145" y1="112" x2="376" y2="112"/>
      <line x1="385" y1="156" x2="656" y2="156"/>
      <line x1="665" y1="200" x2="394" y2="200"/>
      <line x1="385" y1="312" x2="656" y2="312"/>
      <line x1="665" y1="350" x2="394" y2="350"/>
      <line x1="385" y1="382" x2="154" y2="382"/>
    </g>
    <g stroke="#7ee787" stroke-width="2.5" marker-end="url(#seq-arrow-green)">
      <line x1="385" y1="238" x2="896" y2="238"/>
      <line x1="905" y1="274" x2="394" y2="274"/>
    </g>
    <g font-size="14" fill="#a7adba">
      <text x="260" y="102" text-anchor="middle">1. User request</text>
      <text x="525" y="146" text-anchor="middle">2. Request to LLM with context and available tools</text>
      <text x="530" y="190" text-anchor="middle">3. Tool call request</text>
      <text x="646" y="228" text-anchor="middle">4. Validate and execute tool call</text>
      <text x="646" y="264" text-anchor="middle">5. Tool response</text>
      <text x="525" y="302" text-anchor="middle">6. Continuation request with tool response</text>
      <text x="530" y="340" text-anchor="middle">7. Final answer</text>
      <text x="260" y="372" text-anchor="middle">8. Final answer to client</text>
    </g>
  </g>
</svg>

<div class="callout" style="margin-top: 2px; padding: 8px 16px;">The tool result is added to the context. The app sends a continuation request so the model can produce the final answer.</div>

---

<div class="kicker">Retrieval and tools</div>

# Tool calls add power, cost, and latency

<div class="grid-2">
  <div class="panel">
    <h4>Upfront context without tool</h4>
    <p>More efficient when the app can predict what information is needed before the model call.</p>
  </div>
  <div class="panel">
    <h4>Tool retrieval</h4>
    <p>Useful when the app does not know whether information is needed or the possible source material is too large to include just in case.</p>
  </div>
</div>

<div class="callout">A tool loop often sends conversation state plus the new tool answer through another model step. That is why many small tool calls can become expensive.</div>

---

<div class="kicker">Retrieval and tools</div>

# MCP standardizes tool access

<div class="grid-3">
  <div class="panel">
    <h4>MCP server</h4>
    <p>Exposes tools such as file access, browser access, database queries, calendar operations, or issue tracking.</p>
  </div>
  <div class="panel">
    <h4>MCP client</h4>
    <p>The application component that connects to the server, lists tools, and runs selected tools.</p>
  </div>
  <div class="panel">
    <h4>Model</h4>
    <p>Requests tool use through the app. It does not directly control the external service.</p>
  </div>
</div>

<div class="callout cyan">Anthropic contributed MCP to the Agentic AI Foundation under the Linux Foundation. Google contributed Agent2Agent to a Linux Foundation project for agent-to-agent interoperability. The key product idea is that MCP decouples external-service authentication from the LLM.</div>

---

<!-- _class: compact-bottom -->

<div class="kicker">Retrieval and tools</div>

# MCP exposes typed tools and protects credentials

## Tools are described, typed, logged, and invoked outside the model.

<div class="grid-4">
  <div class="panel">
    <h4>Tool schema</h4>
    <p>The model sees a named operation, required fields, descriptions, and allowed outputs.</p>
  </div>
  <div class="panel">
    <h4>Credentials</h4>
    <p>Secrets stay in the server or connector. The harness decides whether a request runs.</p>
  </div>
  <div class="panel">
    <h4>Dev inspection</h4>
    <p>Use development data only, read-only users, and bounded analysis scripts.</p>
  </div>
  <div class="panel">
    <h4>Enterprise sources</h4>
    <p>Connect wikis, issue trackers, UI references, and internal docs through governed tools.</p>
  </div>
</div>

<div class="artifact footer-clearance">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Available tool: read_ticket with ticket_id. Credential stays in the MCP server.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Model asks for read_ticket 1421. Server checks access, fetches the ticket, and returns bounded text.</div>
  </div>
</div>

---

<!-- _class: break -->

<div class="kicker">Application architecture</div>

# The harness around the model

<div class="accent-line"></div>

## Production value comes from process design: schemas, workflow state, agents, frameworks, and validation loops around inference.

---

<div class="kicker">Application architecture</div>

# Structured output makes model intent executable

<div class="grid-3">
  <div class="panel">
    <h4>Structured output</h4>
    <p>A predictable response shape: typed fields, schema-constrained output, table-like data, or command language.</p>
  </div>
  <div class="panel">
    <h4>DSL</h4>
    <p>A small domain-specific language for filters, transformations, workflow steps, UI changes, or business actions.</p>
  </div>
  <div class="panel">
    <h4>AST</h4>
    <p>A tree representation that the application can parse, validate, and interpret safely.</p>
  </div>
</div>

<div class="artifact footer-clearance">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">User intent: show overdue invoices over 10K grouped by account owner.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">filter(status = overdue, amount &gt; 10000) &rarr; group_by(owner) &rarr; sort(total desc)</div>
  </div>
</div>

---

<div class="kicker">Application architecture</div>

# Drafter pattern: generate a DSL, then execute code

## The model drafts a small structured artifact. Deterministic code validates and executes it.

<div class="flow">
  <div class="node">Intent<span>human request</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Draft<span>schema or DSL</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Validate<span>types and policy</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Execute<span>backend code</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Report<span>result and evidence</span></div>
</div>

<div class="grid-3" style="margin-top: 26px;">
  <div class="panel"><h4>Accuracy</h4><p>A small DSL reduces ambiguity and makes invalid output easier to reject before it touches production systems.</p></div>
  <div class="panel"><h4>Cost</h4><p>The model does the fuzzy translation; normal code handles validation, execution, retries, and audit.</p></div>
  <div class="panel"><h4>Security</h4><p>The model never receives direct authority to run arbitrary code or call privileged systems by itself.</p></div>
</div>

---

<div class="kicker">Application architecture</div>

# Harness software coordinates AI workflows

<div class="stack">
  <div class="row"><div class="num">1</div><p><span class="mini-title">Choose workflow</span>Which prompt, agent, retrieval step, tool, or verifier runs next.</p></div>
  <div class="row"><div class="num">2</div><p><span class="mini-title">Manage state</span>Conversation history, files, tool results, forks, checkpoints, compaction.</p></div>
  <div class="row"><div class="num">3</div><p><span class="mini-title">Run tools</span>APIs, files, browser, database, code, shell, calendar, search.</p></div>
  <div class="row"><div class="num">4</div><p><span class="mini-title">Use a REPL</span>An execution scratchpad where the agent can run code, inspect results, and continue.</p></div>
</div>

<div class="callout">Teams usually use frameworks instead of building every harness capability from scratch.</div>

---

<div class="kicker">Application architecture</div>

# Common AI application frameworks

<div class="grid-4">
  <div class="panel tight"><h4>Workflow orchestration</h4><p>LangChain, LangGraph, Deep Agents, and Microsoft Agent Framework coordinate state, tools, checkpoints, and approvals.</p></div>
  <div class="panel tight"><h4>Data and retrieval</h4><p>LlamaIndex, Haystack, and DSPy help with document pipelines, retrieval quality, and eval-driven generation.</p></div>
  <div class="panel tight"><h4>Provider and product SDKs</h4><p>OpenAI Agents SDK, Google ADK, and Vercel AI SDK package tools, handoffs, streaming, tracing, and UI integration.</p></div>
  <div class="panel tight"><h4>Team and durable agents</h4><p>CrewAI and durable-agent frameworks package roles, tasks, workspace state, tool access, and long-running work.</p></div>
</div>

<div class="artifact footer-clearance">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Need a support workflow that searches policies, drafts answers, asks for approval, and streams progress.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Choose retrieval, orchestration, product UI, and approval tooling based on state, tools, latency, and audit needs.</div>
  </div>
</div>

---

<div class="kicker">Application architecture</div>

# Assistants versus agents

<div class="grid-2">
  <div class="panel">
    <h4>Assistant</h4>
    <p>Can use tools, but is focused on question and answer: respond to the current request, ask a follow-up question, or return a result.</p>
  </div>
  <div class="panel">
    <h4>Agent</h4>
    <p>Can use tools too, but is trained to own a goal and execute multiple tool calls, inference turns, and validations without requiring human intervention.</p>
  </div>
</div>

<div class="callout">The distinction is not tools versus no tools. It is how much autonomy the model and application are built to take.</div>

---

<div class="kicker">Application architecture</div>

# Agent teams

<div class="grid-2">
  <div class="panel">
    <h4>User-facing agent</h4>
    <p>The visible chat or workflow surface that understands intent and owns the product experience.</p>
  </div>
  <div class="panel">
    <h4>Internal specialist agents</h4>
    <p>Planner, retriever, worker, verifier, writer, analyst, or tool specialist roles coordinated by software.</p>
  </div>
</div>

<div class="flow" style="margin-top: 24px;">
  <div class="node">User-facing agent<span>one visible conversation</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Planner<span>break down work</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Worker<span>use tools and context</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Verifier<span>check output</span></div>
</div>

<div class="callout">Users see one assistant handling the request; developers build multiple specialized model calls for planning, execution, and verification.</div>

---

<div class="kicker">Application architecture</div>

# AI workflows split complex tasks into controlled steps

<div class="grid-3">
  <div class="panel"><h4>Multi-step</h4><p>Complex tasks need orientation, planning, execution, inspection, repair, and final reporting.</p></div>
  <div class="panel"><h4>Agents</h4><p>Agents encapsulate a role, rules, tools, state, and stopping conditions for a bounded class of work.</p></div>
  <div class="panel"><h4>Harnesses</h4><p>Harnesses drive deterministic behavior around an uncertain model: tool schemas, permissions, retries, and logs.</p></div>
  <div class="panel"><h4>Granularity</h4><p>Use different context and models for each step to optimize cost, latency, and accuracy.</p></div>
  <div class="panel"><h4>Validation loops</h4><p>One shot rarely works for complex tasks. Feedback loops converge through errors, tests, reviews, and retries.</p></div>
  <div class="panel"><h4>Process layer</h4><p>Production AI work usually becomes a workflow engine between user intent and backend systems.</p></div>
</div>

---

<div class="kicker">Application architecture</div>

# AI features need a process layer between UI and backend

## The AI part usually sits between the front-end and backend, coordinating context, models, tools, validation, and state.

<div class="flow">
  <div class="node">Front-end<span>intent and UX state</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">AI process layer<span>retrieve, route, call tools</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Backend<span>systems of record</span></div>
</div>

<div class="grid-3" style="margin-top: 22px;">
  <div class="panel">
    <h4>Context and routing</h4>
    <p>Collect the right docs, code, records, logs, and user state, then choose the model and context size for the step.</p>
  </div>
  <div class="panel">
    <h4>Tools and state</h4>
    <p>Expose allowed API or MCP actions, keep credentials outside the model, and persist task status, traces, approvals, and cost.</p>
  </div>
  <div class="panel">
    <h4>Validation and observability</h4>
    <p>Check schemas, permissions, tests, compiler output, human gates, retrieval sets, tool calls, latency, token use, and failures.</p>
  </div>
</div>

---

<div class="kicker">Application architecture</div>

# Harness design trades control for speed and flexibility

## More precise control usually reduces hallucination, but can make the system slower, narrower, and less useful.

<div class="grid-3">
  <div class="panel">
    <div class="tag coral">Loose</div>
    <h4>Fast and creative</h4>
    <p>Great for brainstorming, prototypes, and exploration. Risk is drift, made-up facts, and unverified implementation.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Guided</div>
    <h4>Balanced workflow</h4>
    <p>Use instructions, tool limits, retrieval, schemas, and verification while still letting the model solve.</p>
  </div>
  <div class="panel">
    <div class="tag green">Deterministic</div>
    <h4>Slow but controlled</h4>
    <p>Use narrow DSLs, fixed steps, explicit approvals, and strict validators for regulated or high-risk paths.</p>
  </div>
</div>

<div class="callout cyan">Control is not free. Every gate adds latency, tokens, product complexity, and a chance to make a capable model feel like a form-filling engine.</div>

---

<div class="kicker">Application architecture</div>

# Reasoning models can run longer multi-step workflows

<div class="grid-3">
  <div class="panel"><h4>File creation</h4><p>Draft, edit, reorganize, and verify local artifacts.</p></div>
  <div class="panel"><h4>API calling</h4><p>Search, query systems, update records, fetch fresh data.</p></div>
  <div class="panel"><h4>Transformation</h4><p>Convert, summarize, classify, generate images, compile, test.</p></div>
</div>

<div class="callout">Less powerful non-reasoning models can still be kept going by a harness, but recent reasoning models make longer uninterrupted task sequences more natural.</div>

---

<!-- _class: break -->

<div class="kicker">Product readiness</div>

# Shipping means controlling risk

<div class="accent-line"></div>

## AI application design has to account for security, permissions, context limits, and product-level truth controls.

---

<div class="kicker">Product readiness</div>

# AI systems expand the attack surface

<div class="grid-3">
  <div class="panel">
    <h4>Prompt injection</h4>
    <p>Hostile instructions hidden in user text, documents, webpages, emails, tickets, or retrieved chunks.</p>
  </div>
  <div class="panel">
    <h4>Data leakage</h4>
    <p>Private data exposed through answers, summaries, logs, tool results, or copied context.</p>
  </div>
  <div class="panel">
    <h4>Tool abuse</h4>
    <p>The model is tricked into requesting harmful, excessive, private, or unauthorized actions.</p>
  </div>
</div>

<div class="callout">Red teams try to break the system. Blue teams build defenses, monitoring, procedures, and tests.</div>

---

<!-- _class: package-risk -->

<div class="kicker">Product readiness</div>

# The risk of package installs by agents

<div class="grid-2">
  <div class="panel">
    <h4>Why agents reach for packages</h4>
    <p>As part of useful work, an LLM may create Python or TypeScript helpers to process large files, extract logs, clean data, or crunch numbers.</p>
  </div>
  <div class="panel">
    <h4>Why this creates risk</h4>
    <p>The helper may need an open source package. Installing it can execute code, pull deep dependencies, and run on machines that hold source, tokens, or credentials.</p>
  </div>
</div>

<div class="grid-3" style="margin-top: 16px;">
  <div class="panel tight"><h4>Hijacked trust</h4><p>Compromised maintainers or CI pipelines publish malicious updates to trusted packages.</p></div>
  <div class="panel tight"><h4>Look-alikes</h4><p>Typosquats, fake names, and hallucinated package names trick installs into infostealers or backdoors.</p></div>
  <div class="panel tight"><h4>Deep chains</h4><p>Small utilities can pull large dependency trees where one weak link can compromise the build.</p></div>
  <div class="panel tight"><h4>Confused sources</h4><p>Dependency confusion, fake registries, and mirrors can inject attacker-controlled packages.</p></div>
  <div class="panel tight"><h4>Install-time code</h4><p>Lifecycle scripts, Python init modules, and .pth files can run before the helper does useful work.</p></div>
  <div class="panel tight"><h4>Mitigations</h4><p>Use approved packages, pinned lockfiles, isolated sandboxes, no secrets, scanners, and human approval for new installs.</p></div>
</div>

---

<div class="kicker">Product readiness</div>

# Securing agents

<div class="stack">
  <div class="row"><div class="num">1</div><p><span class="mini-title">Prompts are not access control</span>Instructions can guide behavior, but application code enforces access, permissions, and data boundaries.</p></div>
  <div class="row"><div class="num">2</div><p><span class="mini-title">Permission checks</span>Code decides whether the user or workflow may read data or perform an action.</p></div>
  <div class="row"><div class="num">3</div><p><span class="mini-title">Least privilege</span>Give the model access only to the tools and data needed for the current task.</p></div>
  <div class="row"><div class="num">4</div><p><span class="mini-title">Audit log</span>Record prompts, tool requests, approvals, tool results, outputs, and errors.</p></div>
  <div class="row"><div class="num">5</div><p><span class="mini-title">Validation</span>Check inputs, tool arguments, outputs, facts, permissions, and formats.</p></div>
</div>

---

<div class="kicker">Product readiness</div>

# Bigger context is not automatically better

<div class="grid-3">
  <div class="panel"><h4>Too-big history</h4><p>History, files, retrieval, and tool results exceed what the model accepts.</p></div>
  <div class="panel"><h4>Request rejection</h4><p>The provider refuses the request because it exceeds limits.</p></div>
  <div class="panel"><h4>Compaction</h4><p>The app summarizes, drops, or selects context to fit the window.</p></div>
</div>

<div class="callout">The needle-in-a-haystack problem remains: important facts can be buried inside large prompts even when they technically fit.</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">User asks about one refund clause. App sends the whole policy manual, history, and unrelated ticket exports.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Better context: current refund clause, approval matrix, relevant order fields, and a short summary of prior turns.</div>
  </div>
</div>

---

<div class="kicker">Product readiness</div>

# AI product design sets context, actions, and checks

<div class="grid-3">
  <div class="panel">
    <h4>Context strategy</h4>
    <p>What to include, exclude, label, summarize, retrieve, cache, and verify.</p>
  </div>
  <div class="panel">
    <h4>Action strategy</h4>
    <p>Which actions become tools, when approval is needed, and how results are audited.</p>
  </div>
  <div class="panel">
    <h4>Truth strategy</h4>
    <p>When to ground, cite, ask a question, run a test, use a judge, or require human review.</p>
  </div>
</div>

<div class="artifact">
  <div class="item">
    <div class="label">Example input</div>
    <div class="body">Feature: AI helps a support manager approve refund exceptions.</div>
  </div>
  <div class="item">
    <div class="label">Example output</div>
    <div class="body">Context: policy and order history. Action: draft only. Check: manager approval plus citation before refund execution.</div>
  </div>
</div>

---

<div class="kicker">Product readiness</div>

# Five core ideas for LLM applications

<div class="stack">
  <div class="row"><div class="num">1</div><p><span class="mini-title">The model is stateless</span>Continuity comes from application-managed history and state.</p></div>
  <div class="row"><div class="num">2</div><p><span class="mini-title">Context is pasted in</span>Files, retrieval, tool results, rules, and history become request tokens.</p></div>
  <div class="row"><div class="num">3</div><p><span class="mini-title">Tools are software interfaces</span>The model asks. The application validates and executes.</p></div>
  <div class="row"><div class="num">4</div><p><span class="mini-title">Agents are harnessed workflows</span>Prompts, tools, state, subagents, and verification coordinated by software.</p></div>
  <div class="row"><div class="num">5</div><p><span class="mini-title">Truth requires grounding</span>Confidence is not evidence. Verification is part of the product.</p></div>
</div>
