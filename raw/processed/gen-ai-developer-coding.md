---
marp: true
theme: default
paginate: true
footer: AI-Assisted Coding
style: |
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&family=JetBrains+Mono:wght@400;600;700&display=swap');

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
  }

  section {
    background:
      radial-gradient(circle at 84% 12%, rgba(83, 215, 255, 0.11), transparent 30%),
      linear-gradient(135deg, #101114 0%, #151820 56%, #0d0f12 100%);
    color: var(--ink);
    font-family: Inter, sans-serif;
    font-weight: 300;
    line-height: 1.34;
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
    font-size: 2.34em;
    font-weight: 800;
    letter-spacing: 0;
    line-height: 1.02;
    margin: 0 0 12px;
  }

  h2 {
    color: var(--muted);
    font-size: 0.98em;
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
    font-size: 0.68em;
  }

  strong {
    color: var(--ink);
    font-weight: 700;
  }

  .lead {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
  }

  .lead h1 {
    font-size: 3.42em;
    max-width: 1040px;
  }

  .lead h2 {
    font-size: 1.03em;
    margin: 0 auto;
  }

  .break {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
  }

  section.break {
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
  }

  .break h1 {
    font-size: 3.05em;
    max-width: 940px;
  }

  section.break h1 {
    font-size: 3.05em;
    margin-left: auto;
    margin-right: auto;
    max-width: 940px;
    text-align: center;
  }

  .break h2 {
    font-size: 1.0em;
    margin: 0 auto;
    max-width: 760px;
  }

  section.break h2 {
    font-size: 1.0em;
    margin: 0 auto;
    max-width: 760px;
    text-align: center;
  }

  .presenter-lockup {
    align-items: center;
    display: flex;
    gap: 14px;
    justify-content: center;
    margin: 8px auto 18px;
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
    margin: 24px auto;
    width: 170px;
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

  .split {
    align-items: center;
    display: grid;
    gap: 32px;
    grid-template-columns: 0.95fr 1.05fr;
  }

  .split-wide {
    align-items: start;
    display: grid;
    gap: 24px;
    grid-template-columns: 1.1fr 0.9fr;
  }

  .panel {
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.045), rgba(255, 255, 255, 0.018));
    border: 1px solid var(--line);
    border-radius: 8px;
    padding: 18px;
  }

  .panel h4 {
    color: var(--ink);
    font-size: 0.74em;
    font-weight: 800;
    margin: 0 0 7px;
  }

  .panel p {
    color: var(--muted);
    font-size: 0.59em;
    margin: 0;
  }

  .tight p {
    font-size: 0.54em;
  }

  .callout {
    background: rgba(255, 203, 107, 0.08);
    border: 1px solid rgba(255, 203, 107, 0.28);
    border-radius: 8px;
    color: var(--ink);
    font-size: 0.66em;
    margin-top: 18px;
    padding: 14px 16px;
  }

  .callout.cyan {
    background: rgba(83, 215, 255, 0.08);
    border-color: rgba(83, 215, 255, 0.28);
  }

  .callout.green {
    background: rgba(126, 231, 135, 0.08);
    border-color: rgba(126, 231, 135, 0.28);
  }

  .artifact {
    background: rgba(83, 215, 255, 0.055);
    border: 1px solid rgba(83, 215, 255, 0.24);
    border-radius: 8px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-top: 18px;
    overflow: hidden;
  }

  .artifact > div {
    padding: 12px 14px;
  }

  .artifact > div + div {
    border-left: 1px solid rgba(83, 215, 255, 0.18);
  }

  .artifact-label {
    color: var(--cyan);
    font-size: 0.47em;
    font-weight: 800;
    letter-spacing: 0.12em;
    margin-bottom: 6px;
    text-transform: uppercase;
  }

  .artifact-body {
    color: var(--muted);
    font-family: JetBrains Mono, monospace;
    font-size: 0.49em;
    line-height: 1.5;
  }

  .ref-list {
    display: grid;
    gap: 12px;
    grid-template-columns: 1fr 1fr;
    margin-top: 12px;
  }

  .ref {
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.045), rgba(255, 255, 255, 0.018));
    border: 1px solid var(--line);
    border-radius: 8px;
    padding: 13px 15px;
  }

  .ref h4 {
    color: var(--ink);
    font-size: 0.64em;
    font-weight: 800;
    margin: 0 0 4px;
  }

  .ref a {
    color: var(--cyan);
    display: block;
    font-size: 0.48em;
    line-height: 1.35;
    overflow-wrap: anywhere;
    text-decoration: none;
  }

  .ref p {
    color: var(--muted);
    font-size: 0.50em;
    margin: 5px 0 0;
  }

  .tag {
    border: 1px solid var(--line);
    border-radius: 6px;
    color: var(--muted);
    display: inline-block;
    font-size: 0.51em;
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

  .big-word {
    color: var(--cyan);
    font-size: 2.35em;
    font-weight: 800;
    line-height: 0.96;
  }

  .small {
    color: var(--dim);
    font-size: 0.54em;
  }

  .mono {
    font-family: JetBrains Mono, monospace;
  }

  .terminal {
    background: #0c0e12;
    border: 1px solid var(--line);
    border-radius: 10px;
    box-shadow: 0 18px 38px rgba(0, 0, 0, 0.22);
    overflow: hidden;
  }

  .terminal-bar {
    align-items: center;
    background: #171a20;
    border-bottom: 1px solid var(--line);
    display: flex;
    gap: 7px;
    padding: 9px 12px;
  }

  .dot {
    border-radius: 99px;
    height: 9px;
    width: 9px;
  }

  .dot.red { background: var(--coral); }
  .dot.yellow { background: var(--amber); }
  .dot.green { background: var(--green); }

  .terminal-title {
    color: var(--dim);
    flex: 1;
    font-family: JetBrains Mono, monospace;
    font-size: 0.48em;
    text-align: center;
  }

  .terminal-body {
    color: var(--muted);
    font-family: JetBrains Mono, monospace;
    font-size: 0.54em;
    line-height: 1.55;
    padding: 16px 18px;
  }

  .prompt { color: var(--green); }
  .path { color: var(--blue); }
  .ok { color: var(--green); }
  .warn { color: var(--amber); }
  .err { color: var(--coral); }
  .note { color: var(--cyan); }

  .flow {
    align-items: stretch;
    display: flex;
    gap: 12px;
    justify-content: space-between;
    margin-top: 24px;
  }

  .node {
    align-items: center;
    background: var(--panel);
    border: 1px solid var(--line);
    border-radius: 8px;
    color: var(--ink);
    display: flex;
    flex: 1;
    flex-direction: column;
    font-size: 0.62em;
    font-weight: 800;
    justify-content: center;
    min-height: 82px;
    padding: 13px 12px;
    text-align: center;
  }

  .node span {
    color: var(--dim);
    display: block;
    font-size: 0.78em;
    font-weight: 400;
    margin-top: 5px;
  }

  .arrow {
    align-items: center;
    color: var(--cyan);
    display: flex;
    font-size: 1.06em;
    font-weight: 800;
  }

  .stack {
    display: grid;
    gap: 12px;
  }

  .row {
    align-items: center;
    background: rgba(255, 255, 255, 0.028);
    border: 1px solid var(--line);
    border-radius: 8px;
    display: grid;
    gap: 14px;
    grid-template-columns: 44px 1fr;
    padding: 12px 14px;
  }

  .num {
    align-items: center;
    background: rgba(83, 215, 255, 0.10);
    border: 1px solid rgba(83, 215, 255, 0.28);
    border-radius: 8px;
    color: var(--cyan);
    display: flex;
    font-size: 0.68em;
    font-weight: 800;
    height: 38px;
    justify-content: center;
  }

  .row p {
    font-size: 0.58em;
    margin: 0;
  }

  .mini-title {
    color: var(--ink);
    display: block;
    font-size: 1.03em;
    font-weight: 800;
    margin-bottom: 2px;
  }

  .metric {
    background: rgba(255, 255, 255, 0.032);
    border: 1px solid var(--line);
    border-radius: 8px;
    overflow: hidden;
    padding: 16px;
    position: relative;
  }

  .metric::before {
    background: linear-gradient(90deg, var(--cyan), transparent);
    content: "";
    height: 2px;
    left: 0;
    position: absolute;
    top: 0;
    width: 100%;
  }

  .metric .label {
    color: var(--dim);
    font-size: 0.48em;
    font-weight: 800;
    letter-spacing: 0.14em;
    text-transform: uppercase;
  }

  .metric .value {
    color: var(--ink);
    font-size: 1.45em;
    font-weight: 800;
    line-height: 1.1;
    margin: 9px 0 5px;
  }

  .metric p {
    color: var(--muted);
    font-size: 0.52em;
    margin: 0;
  }

  .diagram {
    margin-top: 14px;
    width: 100%;
  }

  .ledger {
    background: var(--panel);
    border: 1px solid var(--line);
    border-radius: 8px;
    display: grid;
    gap: 10px;
    padding: 18px;
  }

  .bar {
    background: #0f1116;
    border: 1px solid var(--line);
    border-radius: 999px;
    height: 18px;
    overflow: hidden;
  }

  .bar span {
    display: block;
    height: 100%;
  }

  .legend {
    display: grid;
    gap: 8px;
    grid-template-columns: repeat(2, 1fr);
  }

  .legend-item {
    align-items: center;
    color: var(--muted);
    display: flex;
    font-size: 0.51em;
    gap: 7px;
  }

  .swatch {
    border-radius: 3px;
    height: 9px;
    width: 18px;
  }

  .swimlane {
    border: 1px solid var(--line);
    border-radius: 8px;
    display: grid;
    grid-template-columns: 130px 1fr;
    overflow: hidden;
  }

  .lane-label {
    align-items: center;
    background: rgba(255, 255, 255, 0.04);
    border-right: 1px solid var(--line);
    color: var(--ink);
    display: flex;
    font-size: 0.58em;
    font-weight: 800;
    padding: 12px;
  }

  .lane-content {
    align-items: center;
    display: flex;
    gap: 8px;
    padding: 12px;
  }

  .step-chip {
    background: rgba(83, 215, 255, 0.08);
    border: 1px solid rgba(83, 215, 255, 0.22);
    border-radius: 6px;
    color: var(--muted);
    font-size: 0.49em;
    font-weight: 700;
    padding: 8px 10px;
  }

  .checklist {
    display: grid;
    gap: 12px;
  }

  .check {
    align-items: start;
    display: grid;
    gap: 10px;
    grid-template-columns: 22px 1fr;
  }

  .check svg {
    margin-top: 2px;
  }

  .checkmark {
    align-items: center;
    background: rgba(126, 231, 135, 0.10);
    border: 1px solid rgba(126, 231, 135, 0.28);
    border-radius: 99px;
    color: var(--green);
    display: flex;
    font-size: 0.56em;
    font-weight: 800;
    height: 20px;
    justify-content: center;
    line-height: 1;
    margin-top: 1px;
    width: 20px;
  }

  .check p {
    font-size: 0.58em;
    margin: 0;
  }

  .caption {
    color: var(--dim);
    font-size: 0.52em;
    margin-top: 10px;
  }
---

<!-- _class: lead -->
<!-- _footer: '' -->

<div class="kicker">Gen AI for Developers</div>

# AI-assisted coding for developers

<div class="accent-line"></div>

<div class="presenter-lockup">
  <img class="presenter-logo" src="./logo_dark.png" alt="Martin Bechard logo" />
  <div class="presenter-copy">
    <div class="presenter">Martin Béchard</div>
    <div class="presenter-org">Martin.Bechard@DevConsult.ca</div>
  </div>
</div>

## June 18, 2026

---

<!-- _class: break -->
<!-- _footer: '' -->

<div class="kicker">Foundation</div>

# Models, harnesses, and workflows

<div class="accent-line"></div>

## AI-assisted coding starts with the difference between model capability and the software surface that turns it into work.

---

### Foundation

# Coding assistants combine models with harness software

## AI-assisted coding is ordinary software wrapped around a model that can read text, propose changes, and ask the harness to act.

<div class="grid-3">
  <div class="panel">
    <div class="tag cyan">01</div>
    <h4>Model</h4>
    <p>Transforms request text, code snippets, file content, tool results, and instructions into likely next text.</p>
  </div>
  <div class="panel">
    <div class="tag amber">02</div>
    <h4>Harness</h4>
    <p>Reads files, runs commands, applies patches, manages state, enforces permissions, and verifies work.</p>
  </div>
  <div class="panel">
    <div class="tag green">03</div>
    <h4>Workflow</h4>
    <p>Orients, plans, edits, tests, reviews, and decides what context should be shown next.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">Developer asks: fix invoice totals after archived discounts.</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Model proposes the next edit; harness reads files, applies the patch, runs tests, and reports the result.</div>
  </div>
</div>

---

### Foundation

# Models are engines. Harnesses are workbenches.

## A model supplies capability. A harness decides how that capability reaches files, tools, workflows, users, and verification.

<div class="grid-2">
  <div class="panel">
    <div class="tag cyan">Models</div>
    <h4>The reasoning engine selected for a request</h4>
    <p>Examples: Claude Opus 4.8, Claude Sonnet 4.6, GPT-5.5.</p>
    <p>Changing the model changes raw capability, price, latency, context handling, coding strength, and reliability.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Harnesses</div>
    <h4>The product or runtime around the model</h4>
    <p>Examples: Claude Code, Claude Cowork, OpenAI Codex, Microsoft GitHub Copilot, Cursor, Pi, Amazon Kiro, OpenClaw.</p>
    <p>Changing the harness changes repo context, tool access, permissions, memory, UI, workflows, and verification loops.</p>
  </div>
</div>

<div class="grid-2" style="margin-top: 20px;">
  <div class="panel tight"><h4>Same model, different harness</h4><p>GPT-5.5 in a chat app, IDE agent, or cloud coding workspace will behave differently because the surrounding tools and context differ.</p></div>
  <div class="panel tight"><h4>Same harness, different model</h4><p>A coding tool may route simple edits to a faster model and complex refactors to a stronger reasoning model.</p></div>
</div>

---

### Foundation

# Model choice is a harness design decision

## Some harnesses are tightly integrated with one provider's model family. Others expose a model picker or provider configuration.

<div class="grid-2">
  <div class="panel">
    <div class="tag coral">First-party model family</div>
    <h4>Deeper integration, less model flexibility</h4>
    <p>Examples: Claude Code with Claude models, OpenAI Codex with GPT models.</p>
    <p>The harness builder can tune prompts, compaction, tool schemas, retry logic, and progress signals around a smaller set of model behaviors.</p>
  </div>
  <div class="panel">
    <div class="tag green">Model-choice harness</div>
    <h4>More flexibility, harder integration</h4>
    <p>Examples: GitHub Copilot and configurable assistant surfaces such as Pi coding assistant.</p>
    <p>The harness can route work to different models, but each model may need different instructions, tool descriptions, output constraints, and eval thresholds.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">Two tasks: rename a button label, then refactor authorization across three modules.</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Fast model handles the label; stronger reasoning model handles the refactor; both must satisfy the same harness checks.</div>
  </div>
</div>

---

### Foundation

# Coding model categories

## Treat model choice as a tradeoff between capability, latency, cost, integration, and governance.

<div class="grid-3 tight">
  <div class="panel">
    <div class="tag violet">Claude Opus 4.8</div>
    <p><strong>Use when:</strong> hard repo reasoning, multi-file fixes, review, and agent plans need judgment.</p>
    <p><strong>Watch:</strong> cost and latency make it wasteful for routine edits.</p>
  </div>
  <div class="panel">
    <div class="tag cyan">Claude Sonnet 4.6</div>
    <p><strong>Use when:</strong> daily coding, bug fixes, tests, and review need a strong default.</p>
    <p><strong>Watch:</strong> escalate ambiguous architecture and stubborn debugging.</p>
  </div>
  <div class="panel">
    <div class="tag green">GPT-5.5</div>
    <p><strong>Use when:</strong> Codex and OpenAI tool loops are the main workflow.</p>
    <p><strong>Watch:</strong> verbosity, hallucination risk, and uneven code quality still need verification.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Gemini 3.1 Pro</div>
    <p><strong>Use when:</strong> long context, multimodal inputs, frontend work, or Google tooling matter.</p>
    <p><strong>Watch:</strong> quality depends heavily on the harness and task shape.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Fast routing models</div>
    <p><strong>Use when:</strong> labels, summaries, routing, simple transforms, and cheap parallel work are enough.</p>
    <p><strong>Watch:</strong> do not rely on them for security, architecture, or multi-file reasoning.</p>
  </div>
</div>

---

### Foundation

# Open weight coding LLMs

## Useful when cost, privacy, customization, or local control matter.

<div class="grid-4 tight">
  <div class="panel">
    <div class="tag green">Self-hosted code models</div>
    <p><strong>Use when:</strong> privacy, data residency, customization, or serving cost make local control valuable.</p>
    <p><strong>Watch:</strong> tool calling, templates, and context handling need model-specific tests.</p>
  </div>
  <div class="panel">
    <div class="tag violet">Long-context variants</div>
    <p><strong>Use when:</strong> large repositories, long traces, or batch analysis need broader working context.</p>
    <p><strong>Watch:</strong> more context still needs retrieval discipline and verification.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Enterprise-local stacks</div>
    <p><strong>Use when:</strong> code completion, agentic coding, and private deployment must be evaluated together.</p>
    <p><strong>Watch:</strong> model quality and serving stack quality are separate decisions.</p>
  </div>
  <div class="panel">
    <div class="tag cyan">Cohere North Mini Code</div>
    <p><strong>Use when:</strong> a Canadian open coding model with a small active MoE footprint fits the job.</p>
    <p><strong>Watch:</strong> compare it with larger open models before hard repo work.</p>
  </div>
</div>

<div class="callout cyan">Open weight changes deployment economics, but leading commercial models are usually stronger for hard reasoning. For China-origin models, review privacy, data residency, and jurisdiction risks before sending proprietary code.</div>

---

### Foundation

# Coding workbenches differ by context and control

## The tool is the workflow surface: where context comes from, how edits happen, and how verification is driven.

<div class="grid-4 tight">
  <div class="panel">
    <div class="tag violet">Claude Code</div>
    <h4>Terminal autonomy</h4>
    <p><strong>Pros:</strong> tight Claude integration, strong repo exploration, command loops, and git-oriented work.</p>
    <p><strong>Cons:</strong> provider-coupled and best for developers comfortable with CLI workflows.</p>
  </div>
  <div class="panel">
    <div class="tag green">OpenAI Codex</div>
    <h4>Delegated coding</h4>
    <p><strong>Pros:</strong> reads, edits, runs code, works locally or in cloud tasks, and can turn results into PRs.</p>
    <p><strong>Cons:</strong> GPT-centric integration and environment setup matter a lot for real repos.</p>
  </div>
  <div class="panel">
    <div class="tag cyan">GitHub Copilot</div>
    <h4>Broad platform surface</h4>
    <p><strong>Pros:</strong> editor, GitHub, CLI, agents, model choice, and enterprise controls in one familiar channel.</p>
    <p><strong>Cons:</strong> broad surface means behavior varies by client, plan, model, and organization policy.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Cursor</div>
    <h4>IDE speed</h4>
    <p><strong>Pros:</strong> fast multi-file editing, inline context, strong search, agent mode, and model flexibility.</p>
    <p><strong>Cons:</strong> teams must accept a separate IDE surface and manage workspace trust carefully.</p>
  </div>
</div>

---

### Foundation

# Specialized coding tools target specific workflows

## Each tool emphasizes a different blend of autonomy, specification, local control, and review responsibility.

<div class="grid-4 tight">
  <div class="panel">
    <div class="tag violet">Claude Cowork</div>
    <h4>Knowledge-work agent</h4>
    <p><strong>Focus:</strong> brings agentic file and application work to non-developer tasks.</p>
    <p><strong>Watch:</strong> it needs clear permissions and human review for consequential output.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Amazon Kiro</div>
    <h4>Spec-driven agentic coding</h4>
    <p><strong>Focus:</strong> turns prompts into specs, design artifacts, code, docs, and tests.</p>
    <p><strong>Watch:</strong> spec ceremony can imitate waterfall without adding real verification or safer agent autonomy.</p>
  </div>
  <div class="panel">
    <div class="tag green">Pi</div>
    <h4>Minimal agent harness</h4>
    <p><strong>Focus:</strong> customizable, model-flexible, local, and easy to bend around a personal workflow.</p>
    <p><strong>Watch:</strong> fewer built-in rails means teams must supply more conventions and verification.</p>
  </div>
  <div class="panel">
    <div class="tag coral">OpenClaw</div>
    <h4>Personal automation agent</h4>
    <p><strong>Focus:</strong> connects chat, apps, tools, and local actions.</p>
    <p><strong>Watch:</strong> broad autonomy increases security, approval, and operational risk.</p>
  </div>
</div>

---

### Foundation

# Common AI coding workflow styles

## The right style depends on how clear the target is and how easy the result is to verify.

<div class="grid-2">
  <div class="panel">
    <div class="tag coral">Exploratory coding</div>
    <h4>Prototype quickly with low structure</h4>
    <p>Start from implementation and use the result to learn requirements, edge cases, and design constraints.</p>
    <p><strong>Failure mode:</strong> weak tests, hidden assumptions, tangled code, and expensive review.</p>
  </div>
  <div class="panel">
    <div class="tag cyan">Spec-driven development</div>
    <h4>Emulate human SDLC with specs</h4>
    <p>Generate requirements, design docs, and implementation tasks before coding so the agent has clearer inputs.</p>
    <p><strong>Failure mode:</strong> slow loops, over-control, big upfront documents, and precise execution of the wrong idea.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">Goal: add a discount rule with unknown edge cases.</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Exploratory path prototypes first; spec-driven path writes acceptance rules before implementation.</div>
  </div>
</div>

---

<!-- _class: break -->
<!-- _footer: '' -->

<div class="kicker">Context And Evidence</div>

# What the model actually sees

<div class="accent-line"></div>

## Repository understanding comes from request packaging, context assembly, retrieval, and verification evidence.

---

### Context And Evidence

# The model does not remember your repo

## Every step only knows what the harness sends in that request.

<div class="grid-2">
  <div class="panel">
    <h4>What the developer sees</h4>
    <p>The assistant seems to understand the project, follow prior decisions, and continue a task across many edits.</p>
  </div>
  <div class="panel">
    <h4>What the model receives</h4>
    <p>A fresh request containing instructions, selected history, file excerpts, command output, tool results, and the latest task.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">Prior turn read a billing file, saw a failing test, and edited one condition.</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Next request includes selected history, file excerpts, test output, and the latest diff. The model has no hidden repo memory.</div>
  </div>
</div>

---

### Context And Evidence

# Prompt means the full coding request package

## The model sees a bundled request, not just the sentence typed by the developer.

<div class="grid-4">
  <div class="metric">
    <div class="label">Instructions</div>
    <div class="value">Rules</div>
    <p>Style, safety, coding standards, test expectations, output format.</p>
  </div>
  <div class="metric">
    <div class="label">Task</div>
    <div class="value">Goal</div>
    <p>The developer request, constraints, acceptance criteria, and priority.</p>
  </div>
  <div class="metric">
    <div class="label">Context</div>
    <div class="value">Repo</div>
    <p>Files, search hits, diffs, symbols, docs, tests, errors, logs.</p>
  </div>
  <div class="metric">
    <div class="label">Tools</div>
    <div class="value">Actions</div>
    <p>Read, patch, shell, browser, package manager, git, issue tracker.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">Fix the billing bug.</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Fix invoice discount totals; preserve repository patterns; use failing test output; run build and billing tests.</div>
  </div>
</div>

---

### Context And Evidence

# The hard part is deciding what to provide to the LLM

<div class="split-wide">
  <div class="stack">
    <div class="row"><div class="num">1</div><p><span class="mini-title">Orient from structure</span>Find the relevant modules, test files, package boundaries, and existing conventions.</p></div>
    <div class="row"><div class="num">2</div><p><span class="mini-title">Read targeted code</span>Prefer exact files and nearby call sites over a giant copy of the repository.</p></div>
    <div class="row"><div class="num">3</div><p><span class="mini-title">Keep evidence attached</span>Bring in compiler errors, failing tests, stack traces, screenshots, and runtime logs.</p></div>
  </div>
  <div class="terminal">
    <div class="terminal-bar"><span class="dot red"></span><span class="dot yellow"></span><span class="dot green"></span><span class="terminal-title">context selection</span></div>
    <div class="terminal-body">
      <span class="prompt">$</span> rg "createInvoice" src tests<br>
      <span class="path">src/billing/createInvoice.ts</span><br>
      <span class="path">src/billing/createInvoice.test.ts</span><br>
      <span class="prompt">$</span> pnpm test createInvoice<br>
      <span class="err">FAIL</span> totals include archived discounts<br>
      <span class="note">read only the failing path next</span>
    </div>
  </div>
</div>

---

### Context And Evidence

# Tokens are the size, cost, and speed unit

## Coding assistants spend tokens on repository context, tool output, hidden reasoning, and the final answer.

<div class="ledger">
  <div class="bar"><span style="width: 100%; background: linear-gradient(90deg, var(--cyan) 0 42%, var(--blue) 42% 57%, var(--amber) 57% 78%, var(--violet) 78% 91%, var(--green) 91% 100%);"></span></div>
  <div class="legend">
    <div class="legend-item"><span class="swatch" style="background: var(--cyan);"></span>Instructions and history</div>
    <div class="legend-item"><span class="swatch" style="background: var(--blue);"></span>File content and diffs</div>
    <div class="legend-item"><span class="swatch" style="background: var(--amber);"></span>Tool output and logs</div>
    <div class="legend-item"><span class="swatch" style="background: var(--violet);"></span>Hidden reasoning</div>
    <div class="legend-item"><span class="swatch" style="background: var(--green);"></span>Visible response</div>
  </div>
</div>

<div class="grid-3" style="margin-top: 20px;">
  <div class="panel"><h4>More context</h4><p>Can reduce guessing, but raises cost and can distract the model.</p></div>
  <div class="panel"><h4>More tool calls</h4><p>Can improve accuracy, but each result becomes more context for later steps.</p></div>
  <div class="panel"><h4>More reasoning</h4><p>Can improve multi-step work, but hidden tokens add latency and cost.</p></div>
</div>

---

### Context And Evidence

# Good coding workflows manage the token budget

## Token discipline keeps the useful evidence in view without paying for unrelated history.

<div class="grid-2">
  <div class="panel">
    <h4>Wasteful</h4>
    <p>Paste full files, huge logs, old chat history, broad docs, duplicate tool output, and unrelated examples into every step.</p>
  </div>
  <div class="panel">
    <h4>Efficient</h4>
    <p>Keep stable instructions cached, read narrow files, summarize old turns, trim logs, and retrieve only the code involved.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Wasteful request</div>
    <div class="artifact-body">Full repo paste, old chat history, unrelated docs, and entire failing logs.</div>
  </div>
  <div>
    <div class="artifact-label">Efficient request</div>
    <div class="artifact-body">Stable rules, exact file excerpts, failing assertion, recent diff, and the command to rerun.</div>
  </div>
</div>

---

<!-- _class: break -->
<!-- _footer: '' -->

<div class="kicker">Agent Workflow</div>

# Turn context into controlled change

<div class="accent-line"></div>

## The practical loop is orient, inspect, patch, verify, and carry evidence into the next step.

---

### Agent Workflow

# AI-assisted coding is a loop, not a single answer

## Each pass should produce new evidence that changes the next action.

<div class="flow">
  <div class="node">Orient<span>repo map, rules, task</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Inspect<span>files, tests, logs</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Plan<span>scope and risk</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Patch<span>edits through harness</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Verify<span>build, test, review</span></div>
</div>

<div class="callout cyan">Verification output becomes context for the next orientation step.</div>

<div class="grid-2" style="margin-top: 12px;">
  <div class="panel">
    <h4>Pairing mode</h4>
    <p>The human keeps close control and asks for explanations, diffs, tests, or alternatives at each step.</p>
  </div>
  <div class="panel">
    <h4>Agent mode</h4>
    <p>The harness lets the assistant continue through several steps, then reports what changed and how it was verified.</p>
  </div>
</div>

---

### Agent Workflow

# State-change loops are not new insight

## The agent sees its own edits and tool results, then tries to continue from there.

<div class="grid-2">
  <div class="panel">
    <div class="tag coral">Anti-pattern</div>
    <h4>Changed files, same theory</h4>
    <p>The agent notices the repository changed, assumes the previous direction was right, and continues from its own partial work without re-checking the diagnosis.</p>
  </div>
  <div class="panel">
    <div class="tag green">Useful loop</div>
    <h4>Each pass tests the theory</h4>
    <p>Compare the diff and verification output to the goal, update or reject the diagnosis, then choose the next read, edit, rollback, or test.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">After a failed patch, the transcript is longer and the repository is partially changed.</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Re-check the failing test and diff before choosing whether to continue, revise the diagnosis, or revert the local edit.</div>
  </div>
</div>

---

### Agent Workflow

# Tool calls are how coding agents touch the world

## Tool results are the bridge between model text and repository reality.

<div class="grid-3">
  <div class="panel">
    <h4>Read</h4>
    <p>Open files, inspect directories, read logs, load docs, view diffs, and capture screenshots.</p>
  </div>
  <div class="panel">
    <h4>Search</h4>
    <p>Search repository text, symbols, dependency edges, issue history, docs, and the web when fresh context is needed.</p>
  </div>
  <div class="panel">
    <h4>Write</h4>
    <p>Create files, update tests, apply patches, format code, and change configuration through the harness.</p>
  </div>
  <div class="panel">
    <h4>Targeted edit</h4>
    <p>Use regex, structural search, AST tools, or patch hunks to edit the intended region without rewriting everything nearby.</p>
  </div>
  <div class="panel">
    <h4>Run QA tools</h4>
    <p>Run build, typecheck, lint, unit tests, integration tests, security checks, and project-specific validation scripts.</p>
  </div>
  <div class="panel">
    <h4>Access the browser</h4>
    <p>Open local apps, click through workflows, inspect runtime UI, capture screenshots, and verify visual behavior.</p>
  </div>
</div>

---

### Agent Workflow

# TDD gives the agent a concrete design target

## Tests turn design into executable acceptance criteria.

<div class="grid-3">
  <div class="panel">
    <div class="tag coral">Red</div>
    <h4>Encode the next requirement</h4>
    <p>Start from the design and add a failing test for one behavior, contract, edge case, or regression.</p>
  </div>
  <div class="panel">
    <div class="tag green">Green</div>
    <h4>Make the smallest working change</h4>
    <p>The agent implements enough code to pass the new test while keeping the existing tests and working code intact.</p>
  </div>
  <div class="panel">
    <div class="tag cyan">Refactor</div>
    <h4>Clean up with proof</h4>
    <p>Once tests pass, restructure names, types, modules, or duplication, then rerun the suite to preserve behavior.</p>
  </div>
</div>

<div class="callout green">TDD is an ideal agent workflow because it adds to working code incrementally: each failing test narrows the task, each passing test proves progress against the design, and the suite tells the agent when to stop.</div>

---

### Agent Workflow

# Passing file content to the model

## File boundaries protect the model from mixing code, logs, instructions, and generated text.

<div class="split-wide">
  <div>
    <p>A repository is a filesystem, but the model sees text. File names, excerpts, diffs, search hits, and test output must be serialized into the request.</p>
    <p>Good harnesses preserve boundaries: file path, line numbers, command names, exit status, and whether content is current.</p>
    <div class="artifact" style="grid-template-columns: 1fr;">
      <div>
        <div class="artifact-label">Example boundary</div>
        <div class="artifact-body">Untrusted file content may say: forget prior instructions. The harness labels it as file text, not developer intent.</div>
      </div>
    </div>
  </div>
  <div class="stack">
    <div class="row"><div class="num">F</div><p><span class="mini-title">File markers</span>Where a file starts, ends, and which path it came from.</p></div>
    <div class="row"><div class="num">L</div><p><span class="mini-title">Line anchors</span>Enough location detail to discuss and patch the correct region.</p></div>
    <div class="row"><div class="num">D</div><p><span class="mini-title">Diff context</span>What changed, what is unchanged nearby, and what may be user work.</p></div>
  </div>
</div>

---

### Agent Workflow

# Retrieval for code is more than semantic search

## Code retrieval must combine meaning with exact symbols, paths, and runtime truth.

<div class="grid-3">
  <div class="panel">
    <h4>Text search</h4>
    <p>Fast literal search finds exact symbols, error messages, routes, and feature flags.</p>
  </div>
  <div class="panel">
    <h4>Structure search</h4>
    <p>AST, language server, or graph lookup finds definitions, references, call sites, and dependency edges.</p>
  </div>
  <div class="panel">
    <h4>Semantic search</h4>
    <p>Embeddings help find related concepts when the developer does not know the exact terms.</p>
  </div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">Question: why does createInvoice include archived discounts?</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Search exact symbol, read call sites, inspect failing test, then use semantic search only for related policy docs.</div>
  </div>
</div>

---

### Agent Workflow

# Codebase chatbots

## A chatbot over a repo is usually a RAG system: retrieve source context, then ask the model to explain or answer.

<div class="flow">
  <div class="node">Question<span>what does this do?</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Retrieve<span>vector DB, grep, graph</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Rerank<span>prefer exact sources</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Answer<span>explain with citations</span></div>
</div>

<div class="grid-3" style="margin-top: 26px;">
  <div class="panel"><h4>Multiple answers</h4><p>A symbol may exist in old code, tests, generated files, docs, forks, or dead modules. The chatbot has to choose.</p></div>
  <div class="panel"><h4>Reranking matters</h4><p>Embedding similarity may find related text, but the best answer often needs path, recency, imports, call sites, and exact terms.</p></div>
  <div class="panel"><h4>Citations matter</h4><p>Developers need source paths and confidence signals, not just a fluent summary that sounds right.</p></div>
</div>

<div class="artifact">
  <div>
    <div class="artifact-label">Example input</div>
    <div class="artifact-body">What validates an invoice before it is sent?</div>
  </div>
  <div>
    <div class="artifact-label">Example output</div>
    <div class="artifact-body">Answer cites validator, service call site, unit tests, and stale generated files excluded by reranking.</div>
  </div>
</div>

---

### Agent Workflow

# Agent definition files

## A coding agent performs better when the repo contains durable instructions it can load before editing.

<div class="grid-3">
  <div class="panel"><h4>Role and scope</h4><p>Explain what the agent is allowed to do, which areas it owns, and when it should ask before acting.</p></div>
  <div class="panel"><h4>Project rules</h4><p>Capture architecture conventions, naming, testing expectations, branch rules, and review standards.</p></div>
  <div class="panel"><h4>Important references</h4><p>Point to design docs, API contracts, schema files, generated clients, fixtures, and known fragile modules.</p></div>
  <div class="panel"><h4>Tool expectations</h4><p>Tell the agent how to search, edit, build, test, inspect browser behavior, and report verification.</p></div>
  <div class="panel"><h4>Safety config</h4><p>Reference the separate harness or tool config that protects secrets, production data, destructive commands, and user-owned changes.</p></div>
  <div class="panel"><h4>Examples</h4><p>Show good diffs, good PR summaries, preferred error handling, and the kind of evidence that counts as done.</p></div>
</div>

---

### Agent Workflow

# Ask the agent to plan, then execute visibly

## A visible plan makes assumptions, scope, and verification status inspectable while the work is still in motion.

<div class="flow">
  <div class="node">Orient<span>read rules and repo shape</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Plan<span>steps, files, tests, risks</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Execute<span>one step at a time</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Tick off<span>mark progress and changes</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Verify<span>build, tests, review</span></div>
</div>

<div class="grid-3" style="margin-top: 26px;">
  <div class="panel"><h4>Why plan first</h4><p>The plan turns a vague coding request into visible assumptions, ordered steps, file targets, and acceptance checks.</p></div>
  <div class="panel"><h4>Why tick items off</h4><p>Many recent harnesses include a plan or checklist as a convenience. It keeps the human oriented and gives the agent compact working memory.</p></div>
  <div class="panel"><h4>Why revise the plan</h4><p>When tests, search, or runtime evidence contradict the plan, the agent should update it before continuing.</p></div>
</div>

---

### Agent Workflow

# Use Subagents for complex plans

## Subagents help when independent investigations can stay separate until the main agent integrates the evidence.

<div class="flow">
  <div class="node">Main agent<span>owns plan and synthesis</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Specialist A<span>own context and tools</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Specialist B<span>own context and tools</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Return results<span>summary, evidence, diff</span></div>
  <div class="arrow">&rarr;</div>
  <div class="node">Integrate<span>review and verify</span></div>
</div>

<div class="grid-2" style="margin-top: 28px;">
  <div class="panel"><h4>Why use them</h4><p>Subagents are specialized agents with their own context. Detailed investigation stays local, and only results return to the main agent.</p></div>
  <div class="panel"><h4>Why it helps</h4><p>The main agent keeps the plan and decisions instead of filling its context window with every file read, failed search, and intermediate note.</p></div>
</div>

---

### Agent Workflow

# Verification proves the loop finished

## The agent should report the commands, checks, and runtime evidence that support the result.

<div class="grid-2">
  <div class="checklist">
    <div class="check">
      <span class="checkmark">✓</span>
      <p><strong>Compiler and type checker</strong><br>Catch syntax, import, contract, and obvious type errors.</p>
    </div>
    <div class="check">
      <span class="checkmark">✓</span>
      <p><strong>Regression tests</strong><br>Prove behavior did not drift across known examples.</p>
    </div>
    <div class="check">
      <span class="checkmark">✓</span>
      <p><strong>Runtime checks</strong><br>Use browser, API, logs, or fixtures when tests do not cover the workflow.</p>
    </div>
  </div>
  <div class="terminal">
    <div class="terminal-bar"><span class="dot red"></span><span class="dot yellow"></span><span class="dot green"></span><span class="terminal-title">verification transcript</span></div>
    <div class="terminal-body">
      <span class="prompt">$</span> pnpm run build<br>
      <span class="ok">PASS</span> type check and bundle<br>
      <span class="prompt">$</span> pnpm test billing<br>
      <span class="ok">PASS</span> 18 tests<br>
      <span class="prompt">$</span> git diff --stat<br>
      <span class="note">2 files changed, 74 insertions</span>
    </div>
  </div>
</div>

---

<!-- _class: break -->
<!-- _footer: '' -->

<div class="kicker">Governance And Adoption</div>

# Scale the practice deliberately

<div class="accent-line"></div>

## Team use needs boundaries, operating models, specialized instructions, and human acceptance.

---

### Governance And Adoption

# Coding assistants need real boundaries

## Safety belongs in the harness through access control, approval points, secret handling, and audit logs.

<div class="grid-3">
  <div class="panel">
    <h4>Prompt injection</h4>
    <p>Untrusted files, webpages, issues, emails, or docs can contain hostile instructions aimed at the assistant.</p>
  </div>
  <div class="panel">
    <h4>Secrets and PII</h4>
    <p>Repo content, logs, environment variables, screenshots, and tickets can contain data that should not leave the system.</p>
  </div>
  <div class="panel">
    <h4>Tool abuse</h4>
    <p>Shell, network, database, browser, and git tools can do real damage without permissions and audit trails.</p>
  </div>
</div>

<div class="callout cyan">Prompts are guidance. Access control, secret handling, approvals, allowlists, and logs belong in the harness.</div>

---

### Governance And Adoption

# MCP provides extensibility

## MCP connects a coding harness to external tools through typed server descriptions and controlled calls.

<div class="split">
  <div>
    <p>Model Context Protocol standardizes how an application discovers and calls external tools exposed by an MCP server.</p>
    <p>For coding work, that can mean repository tools, browser automation, issue trackers, databases, internal docs, or deployment systems.</p>
  </div>
  <div class="stack">
    <div class="row"><div class="num">S</div><p><span class="mini-title">Server</span>Describes tools, resources, schemas, and how to invoke them.</p></div>
    <div class="row"><div class="num">C</div><p><span class="mini-title">Client</span>The coding harness connects, lists tools, validates calls, and returns results.</p></div>
    <div class="row"><div class="num">K</div><p><span class="mini-title">Config</span>Hides credentials from the LLM; the model sees tool descriptions and results, not secrets.</p></div>
    <div class="row"><div class="num">M</div><p><span class="mini-title">Model</span>Requests tool use through the application, not by directly controlling the service.</p></div>
  </div>
</div>

---

### Governance And Adoption

# Choose the workflow before choosing the model

## The workflow determines the right amount of autonomy, review, and verification.

<div class="grid-2">
  <div class="panel">
    <h4>Interactive pair</h4>
    <p>Best when intent is fuzzy, UX judgment matters, or the developer wants to steer architecture and tradeoffs closely.</p>
  </div>
  <div class="panel">
    <h4>Autonomous fix</h4>
    <p>Best when the task has a clear failure signal: failing test, compiler error, lint rule, screenshot mismatch, or issue checklist.</p>
  </div>
  <div class="panel">
    <h4>Multi-agent batch</h4>
    <p>Best when changes are repetitive, verifiable, and can be divided into many small independent slices.</p>
  </div>
  <div class="panel">
    <h4>Code review</h4>
    <p>Best when the assistant can compare diffs against contracts, tests, security rules, and expected runtime behavior.</p>
  </div>
</div>

---

### Governance And Adoption

# A good developer prompt gives the agent a target

## Strong prompts name the outcome, constraints, evidence, and done signal.

<div class="stack">
  <div class="row"><div class="num">G</div><p><span class="mini-title">Goal</span>State the outcome, not just the file to edit.</p></div>
  <div class="row"><div class="num">C</div><p><span class="mini-title">Constraints</span>Name architecture rules, coding conventions, safety boundaries, and what not to change.</p></div>
  <div class="row"><div class="num">E</div><p><span class="mini-title">Evidence</span>Point to errors, screenshots, issue details, relevant modules, or examples.</p></div>
  <div class="row"><div class="num">V</div><p><span class="mini-title">Verification</span>Say which build, test, runtime, or review signal should pass before the work is done.</p></div>
</div>

---

### Governance And Adoption

# The human still owns intent and acceptance

## AI can accelerate implementation, but acceptance depends on human goals, tradeoffs, and accountability.

<div class="grid-3">
  <div class="panel">
    <h4>Architecture</h4>
    <p>Choose the design direction, simplify scope, and decide when a local refactor is worth it.</p>
  </div>
  <div class="panel">
    <h4>Product judgment</h4>
    <p>Decide whether the behavior actually helps users, even if the tests pass.</p>
  </div>
  <div class="panel">
    <h4>Accountability</h4>
    <p>Review diffs, approve risky actions, protect data, and decide when evidence is enough.</p>
  </div>
</div>

<div class="callout">The assistant can accelerate implementation. It cannot take ownership of the system's purpose.</div>

---

### Governance And Adoption

# Intelligent self-code-review reduces the new review burden

## Review agents need project rules, source references, and tier-specific checks to produce useful findings.

<div class="grid-3">
  <div class="panel"><h4>Embed your rules</h4><p>Repository instructions, architecture standards, security expectations, and style rules should be part of every review loop.</p></div>
  <div class="panel"><h4>Attach source references</h4><p>Point the reviewer to important files, design docs, API contracts, database schema, and known risky modules.</p></div>
  <div class="panel"><h4>Use tier-specific skills</h4><p>Separate review patterns for UI, app server, database, infrastructure, data pipelines, and security-sensitive code.</p></div>
  <div class="panel"><h4>Check coherence</h4><p>Compare front-end assumptions with backend contracts, generated clients, database fields, and feature flags.</p></div>
  <div class="panel"><h4>Run security checks</h4><p>Look for secret exposure, authorization gaps, unsafe tool use, prompt injection surfaces, and risky dependencies.</p></div>
  <div class="panel"><h4>Keep checklists</h4><p>Use code-review checklists so the AI reduces reviewer load instead of creating more unstructured work.</p></div>
</div>

---

### Governance And Adoption

# Fix assistants should follow branch and PR conventions

## A fix is easier to trust when reproduction, scope, patch, and packaging are all explicit.

<div class="stack">
  <div class="row"><div class="num">1</div><p><span class="mini-title">Reproduce before editing</span>Capture the failing test, compile error, browser issue, log line, or user scenario that proves the bug exists.</p></div>
  <div class="row"><div class="num">2</div><p><span class="mini-title">Scope the branch</span>Use predictable feature-branch naming, one concern per branch, and no unrelated cleanup hiding in the diff.</p></div>
  <div class="row"><div class="num">3</div><p><span class="mini-title">Patch with tests</span>Update the smallest owning module, add or repair regression coverage, and avoid broad rewrites unless the design demands it.</p></div>
  <div class="row"><div class="num">4</div><p><span class="mini-title">Package the PR</span>Summarize the cause, the fix, the risk, the commands run, screenshots when relevant, and any follow-up work.</p></div>
</div>

---

### Governance And Adoption

# Agent skills files

## Skills keep reusable procedures, examples, and scripts outside the live prompt until the task needs them.

<div class="grid-3">
  <div class="panel"><h4>What they are</h4><p>A skill is a folder with a SKILL.md file: reusable instructions, checklists, examples, scripts, and reference material for a specific task.</p></div>
  <div class="panel"><h4>When they load</h4><p>Claude Code can invoke a skill by name or load it automatically when the task matches the skill description, so long procedures stay out of the prompt until needed.</p></div>
  <div class="panel"><h4>Where they live</h4><p>Skills can be personal, project-local, nested inside a monorepo package, bundled by a plugin, or managed for an organization.</p></div>
</div>

<div class="grid-3" style="margin-top: 16px;">
  <div class="panel"><h4>Code review and debugging</h4><p>Claude Code bundles code-review and debug skills for reviewing diffs, finding causes, and walking through failures.</p></div>
  <div class="panel"><h4>Batch and loop work</h4><p>The batch and loop skills help structure repeated tasks, multi-file sweeps, and iterative repair without writing a new prompt each time.</p></div>
  <div class="panel"><h4>Run and verify</h4><p>Run, verify, and run-skill-generator help launch an app, capture the project-specific recipe, and verify changes against the running system.</p></div>
</div>

---

### Governance And Adoption

# Coding assistants should specialize by tier

## Different layers need different context, tools, and checks.

<div class="grid-4 tight">
  <div class="panel">
    <div class="tag cyan">Front-end</div>
    <h4>Interface and behavior</h4>
    <p>Use design system rules, Figma or Storybook extracts, reference pages, responsive states, accessibility, and visual verification.</p>
  </div>
  <div class="panel">
    <div class="tag green">APIs</div>
    <h4>Contracts and flows</h4>
    <p>Use endpoint conventions, error shapes, auth rules, timing diagrams, idempotency, pagination, and generated clients.</p>
  </div>
  <div class="panel">
    <div class="tag amber">Database</div>
    <h4>Data and constraints</h4>
    <p>Use data modeling standards, migration rules, indexes, seed data, read-only dev inspection, and query plans.</p>
  </div>
  <div class="panel">
    <div class="tag violet">Architecture</div>
    <h4>System design memory</h4>
    <p>Name things consistently, structure projects predictably, constrain dependencies, and record design decisions where agents can retrieve them.</p>
  </div>
</div>

<div class="callout">Encode tier-specific conventions so agents can retrieve standards, verify outputs, and keep generated code coherent.</div>

---

### Governance And Adoption

# Refactor generated code into maintainable code

## Treat generated code as a draft unless it already fits the architecture and verification bar.

<div class="grid-3">
  <div class="panel"><h4>Keep the good behavior</h4><p>Capture screenshots, examples, user flows, and tests for the part that made the AI result worth keeping.</p></div>
  <div class="panel"><h4>Reimplement the core</h4><p>Replace tangled code with normal architecture, stable types, smaller modules, and project conventions.</p></div>
  <div class="panel"><h4>Restructure with evidence</h4><p>Use build, tests, lint, browser checks, and human review so the cleanup keeps the useful outcome intact.</p></div>
</div>

<div class="callout">If the appearance is good but the code is a mess, treat the AI output as a prototype or reference implementation, not as done.</div>

---

### Governance And Adoption

# Tool choice is workflow, cost, and operational fit

## Tool selection affects autonomy, context quality, cost exposure, and operational dependency.

<div class="grid-3">
  <div class="panel">
    <h4>IDE versus CLI</h4>
    <p>IDE tools are great for tight edit-review loops. CLI and cloud agents are better for delegated work, scripted verification, and long-running tasks.</p>
  </div>
  <div class="panel">
    <h4>Cost model</h4>
    <p>Compare subscription limits, token usage, credit systems, and model tiers against the work your team actually delegates.</p>
  </div>
  <div class="panel">
    <h4>Operational dependency</h4>
    <p>Check outage behavior, rate limits, policy restrictions, routing changes, and fallback paths before making one tool central.</p>
  </div>
</div>

---

### Governance And Adoption

# What to put in place before scaling AI-assisted coding

## Scaling needs durable conventions, dependable checks, and clear approval points.

<div class="grid-2">
  <div class="checklist">
    <div class="check"><span class="checkmark">✓</span><p>Clear repository instructions and coding conventions.</p></div>
    <div class="check"><span class="checkmark">✓</span><p>Reliable build, test, lint, and runtime verification commands.</p></div>
    <div class="check"><span class="checkmark">✓</span><p>Tool permissions, secret boundaries, and audit logging.</p></div>
  </div>
  <div class="checklist">
    <div class="check"><span class="checkmark">✓</span><p>Task templates for fixes, reviews, refactors, and migrations.</p></div>
    <div class="check"><span class="checkmark">✓</span><p>Evals for common work and known failure modes.</p></div>
    <div class="check"><span class="checkmark">✓</span><p>Human approval points for high-risk changes.</p></div>
  </div>
</div>

---

### References

# References

## Source pages for date-sensitive model, tool, and skill examples.

<div class="ref-list">
  <div class="ref">
    <h4>Anthropic Claude models</h4>
    <a href="https://docs.anthropic.com/en/docs/about-claude/models/overview">docs.anthropic.com / models overview</a>
    <p>Model-family and capability reference for Claude examples.</p>
  </div>
  <div class="ref">
    <h4>Claude Code and skills</h4>
    <a href="https://docs.anthropic.com/en/docs/claude-code/overview">docs.anthropic.com / claude-code overview</a>
    <a href="https://docs.anthropic.com/en/docs/claude-code/skills">docs.anthropic.com / claude-code skills</a>
    <a href="https://www.anthropic.com/product/claude-cowork">anthropic.com / claude-cowork</a>
    <p>Harness, skill-system, and Cowork references for Anthropic tool slides.</p>
  </div>
  <div class="ref">
    <h4>OpenAI Codex and GPT models</h4>
    <a href="https://developers.openai.com/codex/models">developers.openai.com / codex models</a>
    <a href="https://developers.openai.com/api/docs/guides/code-generation">developers.openai.com / code generation</a>
    <p>Codex model-routing and code-generation reference.</p>
  </div>
  <div class="ref">
    <h4>Google Gemini</h4>
    <a href="https://ai.google.dev/gemini-api/docs/models/gemini-3.1-pro-preview">ai.google.dev / gemini 3.1 pro preview</a>
    <p>Current Gemini model reference for coding and agentic workflow examples.</p>
  </div>
  <div class="ref">
    <h4>Cohere North Mini Code</h4>
    <a href="https://docs.cohere.com/docs/north-mini-code-1.0">docs.cohere.com / north mini code</a>
    <p>Open coding model details and local deployment context.</p>
  </div>
  <div class="ref">
    <h4>Kiro, Pi, and OpenClaw</h4>
    <a href="https://kiro.dev/">kiro.dev</a>
    <a href="https://pi.dev/">pi.dev</a>
    <a href="https://openclaw.ai/">openclaw.ai</a>
    <p>Product pages for specialized harness and agent-workflow examples.</p>
  </div>
</div>

---

### References

# Additional references

## Developer-tool and protocol sources.

<div class="ref-list">
  <div class="ref">
    <h4>GitHub Copilot</h4>
    <a href="https://docs.github.com/copilot">docs.github.com / copilot</a>
    <a href="https://docs.github.com/copilot/reference/ai-models/supported-models">docs.github.com / supported copilot models</a>
    <p>Copilot product surface, model support, enterprise controls, and agent features.</p>
  </div>
  <div class="ref">
    <h4>Cursor agent harness</h4>
    <a href="https://cursor.com/blog/agent-best-practices">cursor.com / agent best practices</a>
    <p>Agent harness components, model selection, file editing, search, and terminal execution.</p>
  </div>
  <div class="ref">
    <h4>Model Context Protocol</h4>
    <a href="https://modelcontextprotocol.io/specification/2025-06-18">modelcontextprotocol.io / specification</a>
    <a href="https://modelcontextprotocol.io/specification/draft/server/tools">modelcontextprotocol.io / tools</a>
    <p>Protocol, server, schema, and tool-call references for MCP slides.</p>
  </div>
</div>
