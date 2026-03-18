---
title: "Behavioral Consistency and Transparency Analysis on Large Language Model API Gateways"
permalink: /papers/api-gateway-imc2026/
excerpt: "A web-native version of our IMC 2026 paper on auditing behavioral consistency and transparency in third-party LLM API gateways."
author_profile: true
toc: true
toc_sticky: true
---

<style>
.paper-page {
  --paper-bg: #ffffff;
  --paper-muted-bg: #f6f8fa;
  --paper-border: #d0d7de;
  --paper-text: #24292f;
  --paper-muted-text: #57606a;
  --paper-heading: #0f172a;
  --paper-link: #0969da;
  --paper-accent-bg: #eef6ff;
  --paper-table-stripe: #fafbfc;
  --paper-shadow: 0 1px 2px rgba(15, 23, 42, 0.06);
}

[data-theme="dark"] .paper-page {
  --paper-bg: #111827;
  --paper-muted-bg: #1f2937;
  --paper-border: #374151;
  --paper-text: #e5e7eb;
  --paper-muted-text: #cbd5e1;
  --paper-heading: #f9fafb;
  --paper-link: #7dd3fc;
  --paper-accent-bg: #172554;
  --paper-table-stripe: #18212f;
  --paper-shadow: 0 1px 2px rgba(0, 0, 0, 0.35);
}

@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) .paper-page {
    --paper-bg: #111827;
    --paper-muted-bg: #1f2937;
    --paper-border: #374151;
    --paper-text: #e5e7eb;
    --paper-muted-text: #cbd5e1;
    --paper-heading: #f9fafb;
    --paper-link: #7dd3fc;
    --paper-accent-bg: #172554;
    --paper-table-stripe: #18212f;
    --paper-shadow: 0 1px 2px rgba(0, 0, 0, 0.35);
  }
}

.paper-page {
  color: var(--paper-text);
}

.paper-page h1,
.paper-page h2,
.paper-page h3,
.paper-page h4 {
  color: var(--paper-heading);
}

.paper-hero,
.paper-card,
.paper-table-wrap,
.paper-figure {
  background: var(--paper-bg);
  border: 1px solid var(--paper-border);
  border-radius: 10px;
  box-shadow: var(--paper-shadow);
}

.paper-hero,
.paper-card {
  padding: 1rem 1.1rem;
  margin: 1rem 0 1.25rem;
}

.paper-hero p,
.paper-card p,
.paper-card li,
.paper-page li,
.paper-page td,
.paper-page th {
  color: var(--paper-text);
}

.paper-meta {
  color: var(--paper-muted-text);
  font-size: 0.96rem;
  line-height: 1.7;
}

.paper-badges {
  margin-top: 0.9rem;
}

.paper-badges .pub-btn {
  margin-right: 0.45rem;
  margin-bottom: 0.45rem;
  display: inline-block;
}

.paper-lead {
  font-size: 1.03rem;
  color: var(--paper-muted-text);
}

.paper-keypoints {
  margin: 1rem 0 0;
  padding: 0.9rem 1rem 0.9rem 1.2rem;
  border-radius: 8px;
  background: var(--paper-accent-bg);
  border: 1px solid var(--paper-border);
}

.paper-figure {
  margin: 1.2rem 0;
  padding: 0.9rem;
}

.paper-figure img {
  display: block;
  width: 100%;
  height: auto;
  border-radius: 6px;
}

.paper-figure figcaption {
  margin-top: 0.75rem;
  color: var(--paper-muted-text);
  font-size: 0.95rem;
}

.paper-table-wrap {
  overflow-x: auto;
  margin: 1rem 0 1.3rem;
}

.paper-table {
  width: 100%;
  border-collapse: collapse;
  min-width: 720px;
}

.paper-table caption {
  caption-side: top;
  text-align: left;
  padding: 0.95rem 0.95rem 0.4rem;
  color: var(--paper-muted-text);
  font-size: 0.95rem;
}

.paper-table th,
.paper-table td {
  border-top: 1px solid var(--paper-border);
  padding: 0.72rem 0.8rem;
  text-align: left;
  vertical-align: top;
}

.paper-table thead th {
  background: var(--paper-muted-bg);
  font-weight: 700;
}

.paper-table tbody tr:nth-child(even) {
  background: var(--paper-table-stripe);
}

.paper-note {
  color: var(--paper-muted-text);
  font-size: 0.95rem;
}

.paper-ref-list li {
  margin-bottom: 0.75rem;
}

.paper-inline-code {
  background: var(--paper-muted-bg);
  border: 1px solid var(--paper-border);
  border-radius: 6px;
  padding: 0.08rem 0.35rem;
}
</style>

<div class="paper-page">

# Behavioral Consistency and Transparency Analysis on Large Language Model API Gateways

<div class="paper-hero">
  <div class="paper-meta">
    <strong>Guanjie Lin</strong>, Yinxin Wan, Shichao Pei, Ting Xu, Kuai Xu, Guoliang Xue<br>
    Accepted by <em>ACM Internet Measurement Conference (IMC)</em>, 2026<br>
    Acceptance Rate: 10.38% (Cycle 1)
  </div>

  <div class="paper-badges">
    <a href="{{ '/files/paper_pdf/lin2026llmapi.pdf' | relative_url }}" class="pub-btn"><i class="fas fa-file-pdf"></i> PDF</a>
    <a href="{{ '/#publications' | relative_url }}" class="pub-btn"><i class="fas fa-arrow-left"></i> Back to Publications</a>
  </div>

  <p class="paper-lead">
    This page presents a web-native, single-column version of the paper. It preserves the core content of the IMC submission while adapting figures, equations, tables, and references to the reading style of the current Jekyll site.
  </p>
</div>

## Abstract

Third-party Large Language Model (LLM) API gateways are rapidly emerging as unified access points to models offered by multiple vendors. However, the internal routing, caching, and billing policies of these gateways are largely undisclosed, leaving users with limited visibility into whether requests are served by the advertised models, whether responses remain faithful to upstream APIs, or whether invoices accurately reflect public pricing policies. To address this gap, we introduce **VeriFlow**, a lightweight black-box measurement framework for evaluating behavioral consistency and operational transparency in commercial LLM gateways. VeriFlow is designed to detect key misbehaviors, including model downgrading or switching, truncation, billing inaccuracies, and instability in latency by auditing gateways along four critical dimensions: response content analysis, multi-turn conversation performance, billing accuracy, and latency characteristics. Our measurements across $10$ real-world commercial LLM API gateways reveal frequent gaps between expected and actual behaviors, including silent model substitutions, degraded memory retention, deviations from announced pricing, and substantial variation in latency stability across platforms.

<div class="paper-keypoints">
<strong>Key takeaways.</strong>
<ol>
  <li>We treat third-party LLM gateways themselves as the measurement target rather than assuming they faithfully proxy upstream vendor APIs.</li>
  <li>VeriFlow audits four dimensions at once: response behavior, long-context memory, billing accuracy, and latency stability.</li>
  <li>Across ten real-world gateways, we observe evidence of model substitution, degraded memory retention, pricing deviations, and unstable latency.</li>
</ol>
</div>

## 1. Introduction

Large Language Models (LLMs) such as OpenAI's GPT, Anthropic's Claude, and Google's Gemini are increasingly integrated into a broad range of applications. Although these models are widely accessible through cloud inference APIs, each vendor maintains its own independent platform, API schema, authentication model, and billing pipeline. For developers and organizations that rely on multiple model families, this fragmented ecosystem introduces overhead in backend integration, key management, accounting, and failover planning.

LLM API gateways have emerged as a practical answer to this fragmentation. A single gateway API can expose models from multiple upstream vendors, centralize billing, and advertise convenience features such as load balancing, model routing, cost optimization, and unified SDK compatibility. In operational terms, gateways promise to simplify model consumption in the same way that classical API gateways simplified access to microservices.

However, this convenience also introduces opacity. From the client's perspective, the gateway is a black-box intermediary. Users typically cannot observe how requests are routed, which upstream model actually serves a response, whether a gateway truncates long prompts or outputs, or whether billing conforms to the public pricing of the claimed model. These questions matter because premium models can be much more expensive than lightweight alternatives, and a gateway has direct financial incentives to optimize its backend choices in ways that are not always visible to clients.

Auditing these systems is difficult because the user sees only inputs, outputs, and limited metadata. Existing fingerprinting and benchmarking work provides useful primitives, but it does not directly address whether a third-party gateway preserves the behavior of the specific upstream model it claims to serve. This gap motivates a client-side auditing framework that uses only public APIs and observable response artifacts.

We therefore present **VeriFlow**, a lightweight framework for auditing LLM gateways across four complementary dimensions:

1. **Response content analysis**, which tests whether the observed response behavior is consistent with the claimed upstream model.
2. **Multi-turn conversation performance**, which checks long-context retention and signs of silent model switching or truncation.
3. **Billing accuracy**, which compares expected and actual charges under published pricing rules.
4. **Latency characteristics**, which use latency variation as a signal of unstable or heterogeneous backend execution paths.

We validate VeriFlow on official vendor APIs, where the ground-truth model identity is known, and then apply it to ten commercial LLM gateways. The results reveal substantial gaps between expected and observed behavior, including possible model substitutions, degraded memory retention, inaccurate billing, and large differences in latency stability.

The main contributions of this work are:

1. We identify the transparency and consistency risks introduced by third-party LLM gateways.
2. We design a practical black-box auditing framework that works entirely through public APIs.
3. We demonstrate, through measurements on real services, that gateway behavior can diverge substantially from advertised upstream behavior.

## 2. Background and Motivation

LLM API gateways are increasingly adopted to abstract vendor differences and provide unified interfaces, load balancing, and centralized billing. In a typical deployment, a client sends a request to the gateway using a standardized API schema, and the gateway then decides how to route that request to an upstream model provider. The gateway may also add caching, policy enforcement, model fallback, or pricing transformations on top of the underlying vendor APIs.

This architecture is attractive, but it also makes several important behaviors hard to verify externally:

1. **Model downgrading or switching.** A gateway may route a request to a cheaper or less capable model than the one the user selected, while still advertising premium-model access.
2. **Prompt or response truncation.** A gateway may impose its own context or output limits, causing quality degradation before the upstream model's documented limit is reached.
3. **Billing inaccuracy.** The number of billed tokens or the total charge may diverge from public pricing expectations, especially when cache discounts are involved.
4. **Latency fluctuation.** Internal routing, overloaded backends, or dynamic model switching may produce large latency variation that is visible to clients.

These issues are not merely theoretical. They arise naturally because gateways aggregate heterogeneous vendors and must make cost-performance trade-offs under operational pressure. They also arise because clients often lack a direct ground-truth baseline for comparison.

<!-- Web-native redraw based on local Figure 1 semantics -->
<figure class="paper-figure">
  <img src="{{ '/assets/papers/api-gateway-imc2026/fig1.svg' | relative_url }}" alt="Overview of LLM API gateway architecture and the main transparency and consistency challenges.">
  <figcaption><strong>Figure 1.</strong> Overview of LLM API gateway architecture and the main transparency and consistency challenges.</figcaption>
</figure>

Prior work has examined model fingerprinting, prompt caching, hidden token usage, and API-level risks, but mostly on vendor APIs or downstream applications rather than third-party intermediary gateways. VeriFlow is designed for the latter setting: it evaluates whether gateways faithfully preserve the behavior, memory, billing, and latency characteristics expected from the models they claim to proxy.

## 3. Design of VeriFlow

### 3.1 Overview

VeriFlow is a lightweight auditing framework that operates entirely through public APIs. To maximize applicability across platforms, all measurements are performed using the OpenAI-compatible <span class="paper-inline-code">/v1/chat/completions</span> endpoint, which is widely exposed by commercial gateways and returns structured metadata useful for auditing.

The framework has three logical stages:

1. **Baseline generation.** Query official vendor endpoints to build trusted behavioral signatures for known models.
2. **Third-party auditing.** Query the same probe suite against third-party gateways under aligned settings.
3. **Consistency analysis.** Compare gateway behavior against the baseline along four dimensions: response content, multi-turn performance, billing, and latency.

<!-- Export source: ~\research-paper\api-gateway-imc2026\figures\fig21.pdf -> assets/papers/api-gateway-imc2026/architecture.png -->
<figure class="paper-figure">
  <img src="{{ '/assets/papers/api-gateway-imc2026/architecture.png' | relative_url }}" alt="Overall architecture of the VeriFlow framework.">
  <figcaption><strong>Figure 2.</strong> Overall architecture of the VeriFlow framework.</figcaption>
</figure>

### 3.2 Response Content Analysis

The first dimension aims to answer a simple but difficult question: does the gateway actually serve the requested model, or does it silently substitute another one?

We model a versioned LLM endpoint as a stochastic mapping

$$
u \sim E_v(p, \theta),
$$

where a probe $p \in \mathcal{P}$ and generation parameters $\theta$ produce a structured response $u$ and metadata $m$. Naive text matching is unreliable because the same model can produce different surface-level outputs across repeated calls. Instead, VeriFlow uses prompts that encourage structured, comparable reasoning behavior.

#### Prompt design

Our prompt suite follows three principles:

1. Responses to the same probe should remain relatively stable across repeated queries to the same model.
2. Responses from different models should differ in ways that can be captured through stable features.
3. The overall suite should remain lightweight enough for practical auditing.

Based on these principles, the probe suite spans four domains:

1. **AIME** style mathematical reasoning tasks.
2. **GPQA** multiple-choice questions that test deep reasoning.
3. **Factual recall** questions about major events between 2021 and 2025.
4. **Geographic inference** tasks that require multi-hop reasoning.

Each prompt instructs the model to output a structured response containing a reasoning path and a final answer. This reduces variation caused by purely stylistic differences and makes model-specific behavior easier to compare.

#### Model signature extraction

For each structured response, VeriFlow extracts a feature vector $\Phi(u, m)$ rather than relying on textual embeddings. The signature vector includes:

1. **Answer quality**, such as correctness and answer placement.
2. **Reasoning structure**, such as reasoning depth and step-length statistics.
3. **Scale**, including response length and density.
4. **Style**, such as the presence of numeric expressions or LaTeX formatting.
5. **Parsing quality**, including whether parsing succeeds cleanly.

Collecting these signatures over repeated runs yields a behavioral profile for each model. VeriFlow then trains lightweight one-vs-rest XGBoost classifiers to determine whether responses are consistent with the claimed upstream model.

### 3.3 Multi-turn Conversation Performance

LLM applications are rarely single-shot. They often involve long-context, multi-turn interactions where users expect the system to remember prior facts, retain preferences, and update state correctly over time. A gateway can violate these expectations by switching models mid-conversation, truncating context, or handling caches in opaque ways.

To test this dimension, VeriFlow uses a standardized $25$-turn conversation template. The template assigns a stable identity and a user-specific preference early in the conversation, inserts unrelated distractor turns, later updates the preference, and then checks whether the system correctly recalls the current state near the end of the session.

In addition to textual correctness, VeriFlow also records metadata such as:

1. The number of distinct <span class="paper-inline-code">system_fingerprint</span> values across turns.
2. The rate of cached-token reuse reported in the API metadata.

These signals do not constitute proof on their own, but they provide practical indicators of possible model switching or inconsistent context handling.

### 3.4 Billing Accuracy

Billing is one of the most concrete properties a client can verify. For each audited request, VeriFlow records the number of input tokens $n_{\text{in}}$, cached tokens $n_{\text{cached}}$, and output tokens $n_{\text{out}}$, along with the public per-token prices $p_{\text{in}}$, $p_{\text{cached}}$, and $p_{\text{out}}$ when such rates are available.

The expected cost of one request is computed as

$$
C_{\text{expected}} =
(n_{\text{in}} - n_{\text{cached}})\,p_{\text{in}}
+ n_{\text{cached}}\,p_{\text{cached}}
+ n_{\text{out}}\,p_{\text{out}}.
$$

For gateways that do not expose or apply separate cache pricing, VeriFlow evaluates them using $n_{\text{cached}} = 0$. The measured charge is then compared to the expected cost to identify overcharging, missing cache discounts, or unexpected pricing transformations.

### 3.5 Latency Characteristics

Latency is both a user-facing quality metric and a potential signal of hidden backend behavior. Absolute latency alone is difficult to compare across platforms because it depends on network conditions, deployment regions, and transient load. VeriFlow therefore focuses on latency **variation** rather than raw latency.

For repeated requests under matched settings, VeriFlow measures the coefficient of variation:

$$
\mathrm{CV} = \sigma_T / \mu_T,
$$

where $\sigma_T$ and $\mu_T$ are the standard deviation and mean of the observed response times. If a gateway serves a fixed backend path consistently, the latency distribution should remain relatively stable. If it silently switches between heterogeneous execution paths or overloaded backends, the distribution often becomes broader or even multi-modal, producing a higher CV.

## 4. Evaluation

### 4.1 Data Collection

For official vendor platforms, we collect behavioral signatures from $24$ LLMs exposed through their native APIs. Using the standardized probe suite under fixed parameters, each model is queried with $K = 12$ repetitions per probe, producing $15{,}840$ records in total, or $660$ records per model.

For third-party platforms, we audit $10$ commercial gateways using the same probe suite and aligned request parameters. The gateways are anonymized using first-last-letter encodings:

<div class="paper-card">
<code>oer</code>, <code>aix</code>, <code>oub</code>, <code>zng</code>, <code>oey</code>, <code>uipi</code>, <code>bie</code>, <code>unpi</code>, <code>ayi</code>, and <code>lub</code>.
</div>

For single-turn evaluation, each model on each gateway is queried with five repetitions. For multi-turn evaluation, the $25$-turn conversation template is also repeated five times per model per gateway. Overall, the measurement campaign consumes roughly one million tokens per model, which is practical for research-scale auditing and can be further reduced with smaller repetition counts if needed.

### 4.2 Controlled Validation

Before auditing third-party gateways, we validate whether the response-content signatures are sufficiently discriminative under controlled conditions where the upstream model is known. Across the $24$ models in our baseline set, VeriFlow achieves an average $F1$ score of $0.968 \pm 0.085$, with most models exceeding $0.95$.

We also test the detector ensemble on five unseen models not included in the original training set: Claude Sonnet 4.5, Claude Haiku 4.5, Qwen-Plus, Qwen-Turbo, and DeepSeek-V3.2-Exp. None of these unseen models is mistakenly identified as one of the known baseline models. This result suggests that the method behaves conservatively and can be extended cheaply when new models appear.

### 4.3 Third-party API Gateway Evaluation

#### 4.3.1 Response Content Evaluation

The first third-party analysis measures the proportion of responses that are classified as the **claimed** upstream model. Each percentage below is computed over $275$ responses per model.

<div class="paper-table-wrap">
  <table class="paper-table">
    <caption><strong>Table 1.</strong> Response content evaluation using per-model probe subsets. Each cell shows the percentage of responses classified as the claimed model.</caption>
    <thead>
      <tr>
        <th>Gateway</th>
        <th>gpt-4o (%)</th>
        <th>gpt-5 (%)</th>
        <th>Gemini-2.5-pro (%)</th>
        <th>Claude Sonnet 4.0 (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>Baseline</td><td>98.18</td><td>97.09</td><td>96.00</td><td>97.09</td></tr>
      <tr><td>a*yi</td><td>62.18</td><td>48.00</td><td>54.91</td><td>70.91</td></tr>
      <tr><td>a*ix</td><td>88.00</td><td>70.91</td><td>N/A</td><td>83.27</td></tr>
      <tr><td>b*ie</td><td>46.91</td><td>13.09</td><td>N/A</td><td>62.91</td></tr>
      <tr><td>l*ub</td><td>90.91</td><td>94.18</td><td>84.00</td><td>58.18</td></tr>
      <tr><td>o*ub</td><td>86.18</td><td>34.91</td><td>90.18</td><td>N/A</td></tr>
      <tr><td>o*er</td><td>93.09</td><td>97.09</td><td>89.09</td><td>86.91</td></tr>
      <tr><td>o*ey</td><td>90.18</td><td>92.00</td><td>96.00</td><td>N/A</td></tr>
      <tr><td>un*pi</td><td>82.18</td><td>89.09</td><td>73.09</td><td>N/A</td></tr>
      <tr><td>ui*pi</td><td>76.00</td><td>N/A</td><td>N/A</td><td>N/A</td></tr>
      <tr><td>z*ng</td><td>95.27</td><td>94.91</td><td>N/A</td><td>97.09</td></tr>
    </tbody>
  </table>
</div>

For `gpt-4o`, most gateways remain relatively close to the baseline, though some platforms show much lower claimed-model consistency. For `gpt-5`, the differences are more striking, with several gateways frequently producing responses that are not classified as belonging to the `gpt-5` family at all. Support for `gemini-2.5-pro` and `claude-sonnet-4.0` is less uniform and more unstable.

<div class="paper-card">
<strong>Takeaway.</strong> Several gateways appear not to preserve the behavior of the claimed model consistently, especially for higher-end or less uniformly supported models.
</div>

#### 4.3.2 Multi-turn Conversation Evaluation

The second analysis evaluates memory retention and infrastructure stability over a standardized $25$-turn conversation. The table below reports checkpoint pass counts at turns 10, 24, and 25, the number of distinct system fingerprints (FC), and cache rate (CR).

<div class="paper-table-wrap">
  <table class="paper-table">
    <caption><strong>Table 2.</strong> Multi-turn conversation performance comparison for gpt-4o and gpt-4o-mini.</caption>
    <thead>
      <tr>
        <th rowspan="2">Gateway</th>
        <th colspan="5">gpt-4o</th>
        <th colspan="5">gpt-4o-mini</th>
      </tr>
      <tr>
        <th>T10</th><th>T24</th><th>T25</th><th>FC</th><th>CR (%)</th>
        <th>T10</th><th>T24</th><th>T25</th><th>FC</th><th>CR (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>Baseline</td><td>5</td><td>5</td><td>5</td><td>1</td><td>48.7</td><td>5</td><td>1</td><td>2</td><td>1</td><td>40.3</td></tr>
      <tr><td>a*yi</td><td>3</td><td>1</td><td>2</td><td>4</td><td>4.2</td><td>3</td><td>1</td><td>1</td><td>2</td><td>5.3</td></tr>
      <tr><td>a*ix</td><td>5</td><td>4</td><td>5</td><td>1</td><td>34.7</td><td>5</td><td>0</td><td>0</td><td>2</td><td>21.5</td></tr>
      <tr><td>b*ie</td><td>5</td><td>4</td><td>4</td><td>2</td><td>15.7</td><td>4</td><td>0</td><td>0</td><td>3</td><td>14.2</td></tr>
      <tr><td>l*ub</td><td>5</td><td>5</td><td>5</td><td>2</td><td>18.2</td><td>3</td><td>0</td><td>1</td><td>2</td><td>16.3</td></tr>
      <tr><td>o*ub</td><td>5</td><td>5</td><td>3</td><td>2</td><td>32.5</td><td>4</td><td>0</td><td>1</td><td>1</td><td>29.7</td></tr>
      <tr><td>o*er</td><td>5</td><td>5</td><td>5</td><td>1</td><td>32.8</td><td>5</td><td>1</td><td>0</td><td>1</td><td>52.3</td></tr>
      <tr><td>o*ey</td><td>4</td><td>3</td><td>4</td><td>2</td><td>0.0</td><td>5</td><td>4</td><td>4</td><td>3</td><td>0.0</td></tr>
      <tr><td>un*pi</td><td>5</td><td>5</td><td>4</td><td>2</td><td>19.3</td><td>4</td><td>0</td><td>0</td><td>2</td><td>18.7</td></tr>
      <tr><td>ui*pi</td><td>5</td><td>5</td><td>4</td><td>2</td><td>12.8</td><td>5</td><td>1</td><td>2</td><td>2</td><td>11.5</td></tr>
      <tr><td>z*ng</td><td>5</td><td>5</td><td>4</td><td>2</td><td>23.5</td><td>5</td><td>0</td><td>0</td><td>2</td><td>32.6</td></tr>
    </tbody>
  </table>
</div>

The official API retains state well for `gpt-4o`, while several gateways lose consistency near the end of the conversation or expose multiple system fingerprints across runs. For `gpt-4o-mini`, the gap is often larger: many gateways fail the late-turn checkpoints entirely.

Two anomalies stand out. Platform `a*yi` shows very similar degraded behavior for both `gpt-4o` and `gpt-4o-mini`, which suggests possible backend homogenization. Platform `o*ey` achieves unusually strong checkpoint performance for `gpt-4o-mini` while reporting zero cache usage, which indicates a non-canonical implementation path or an opaque cache policy.

<div class="paper-card">
<strong>Takeaway.</strong> Long-context behavior varies widely across gateways. Some are close to upstream behavior, while others appear to lose state, alter caching, or change backend configurations during the conversation.
</div>

#### 4.3.3 Billing Accuracy Evaluation

The next analysis compares expected and actual charges for `gpt-4o`. Each gateway may publish different nominal prices, so the audit compares the actual billed amount against what the gateway's own public pricing rules imply for the observed token usage.

<div class="paper-table-wrap">
  <table class="paper-table">
    <caption><strong>Table 3.</strong> Billing accuracy for <code>gpt-4o</code>: baseline token counts and expected vs. actual costs.</caption>
    <thead>
      <tr>
        <th>Gateway</th>
        <th>Input</th>
        <th>Cached</th>
        <th>Output</th>
        <th>C<sub>exp</sub></th>
        <th>C<sub>act</sub></th>
        <th>Gap (%)</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>Baseline</td><td>139,025</td><td>67,705</td><td>201,060</td><td>2.27</td><td>2.27</td><td>0.0</td></tr>
      <tr><td>a*yi</td><td>137,475</td><td>0</td><td>203,346</td><td>2.30</td><td>2.30</td><td>0.0</td></tr>
      <tr><td>a*ix</td><td>140,436</td><td>0</td><td>196,651</td><td>6.07</td><td>6.53</td><td>+7.6</td></tr>
      <tr><td>b*ie</td><td>139,085</td><td>0</td><td>208,578</td><td>2.35</td><td>2.35</td><td>0.0</td></tr>
      <tr><td>l*ub</td><td>141,712</td><td>3,685</td><td>201,749</td><td>2.32</td><td>2.32</td><td>0.0</td></tr>
      <tr><td>o*ub</td><td>138,762</td><td>0</td><td>365,097</td><td>8.50</td><td>8.50</td><td>0.0</td></tr>
      <tr><td>o*er</td><td>139,649</td><td>31,256</td><td>199,124</td><td>2.30</td><td>2.30</td><td>0.0</td></tr>
      <tr><td>o*ey</td><td>140,987</td><td>0</td><td>213,446</td><td>6.81</td><td>11.09</td><td>+62.8</td></tr>
      <tr><td>un*pi</td><td>142,318</td><td>28,501</td><td>204,763</td><td>2.27</td><td>2.27</td><td>0.0</td></tr>
      <tr><td>ui*pi</td><td>139,421</td><td>0</td><td>217,790</td><td>2.36</td><td>2.36</td><td>0.0</td></tr>
      <tr><td>z*ng</td><td>137,884</td><td>0</td><td>226,935</td><td>10.14</td><td>10.14</td><td>0.0</td></tr>
    </tbody>
  </table>
</div>

Most gateways align with their public prices and reported usage. However, `a*ix` shows a non-trivial billing gap of `+7.6%`, and `o*ey` shows a much larger `+62.8%` discrepancy despite token usage that looks comparable to other platforms. These results indicate that cost transparency is not uniformly preserved across the ecosystem.

<div class="paper-card">
<strong>Takeaway.</strong> Billing consistency is good for many platforms, but a small number of gateways materially diverge from their own published pricing expectations.
</div>

#### 4.3.4 Latency Evaluation

Finally, we compare latency variation for `gpt-4o` across task categories. Rather than comparing absolute latency across deployments, we focus on the range and coefficient of variation, which better capture backend stability.

<div class="paper-table-wrap">
  <table class="paper-table">
    <caption><strong>Table 4.</strong> Latency ranges (min, max, in seconds) and coefficients of variation (CV) for <code>gpt-4o</code> across gateways.</caption>
    <thead>
      <tr>
        <th rowspan="2">Gateway</th>
        <th colspan="3">Math</th>
        <th colspan="3">GPQA</th>
        <th colspan="3">Factual</th>
        <th colspan="3">Geo</th>
      </tr>
      <tr>
        <th>Min</th><th>Max</th><th>CV</th>
        <th>Min</th><th>Max</th><th>CV</th>
        <th>Min</th><th>Max</th><th>CV</th>
        <th>Min</th><th>Max</th><th>CV</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>Baseline</td><td>2.67</td><td>121.84</td><td>0.63</td><td>1.72</td><td>15.56</td><td>0.67</td><td>1.38</td><td>8.29</td><td>0.35</td><td>0.77</td><td>6.33</td><td>0.42</td></tr>
      <tr><td>a*yi</td><td>2.98</td><td>136.11</td><td>0.68</td><td>1.91</td><td>17.27</td><td>0.72</td><td>1.55</td><td>9.34</td><td>0.38</td><td>0.77</td><td>6.33</td><td>0.42</td></tr>
      <tr><td>a*ix</td><td>1.33</td><td>60.92</td><td>0.25</td><td>0.87</td><td>7.87</td><td>0.27</td><td>0.84</td><td>5.03</td><td>0.18</td><td>0.44</td><td>3.63</td><td>0.20</td></tr>
      <tr><td>b*ie</td><td>5.99</td><td>273.38</td><td>1.10</td><td>3.30</td><td>29.85</td><td>1.05</td><td>4.74</td><td>28.49</td><td>0.82</td><td>2.25</td><td>18.50</td><td>0.88</td></tr>
      <tr><td>l*ub</td><td>2.51</td><td>114.51</td><td>0.58</td><td>1.62</td><td>14.68</td><td>0.62</td><td>1.29</td><td>7.75</td><td>0.32</td><td>0.77</td><td>6.33</td><td>0.42</td></tr>
      <tr><td>o*ub</td><td>2.48</td><td>113.03</td><td>0.57</td><td>1.60</td><td>14.50</td><td>0.61</td><td>1.26</td><td>7.57</td><td>0.31</td><td>0.76</td><td>6.22</td><td>0.41</td></tr>
      <tr><td>o*er</td><td>4.62</td><td>210.98</td><td>0.92</td><td>3.07</td><td>27.81</td><td>1.00</td><td>3.02</td><td>18.11</td><td>0.60</td><td>1.45</td><td>11.92</td><td>0.65</td></tr>
      <tr><td>o*ey</td><td>2.25</td><td>102.45</td><td>0.50</td><td>1.44</td><td>13.05</td><td>0.53</td><td>1.23</td><td>7.38</td><td>0.30</td><td>0.71</td><td>5.87</td><td>0.38</td></tr>
      <tr><td>un*pi</td><td>2.57</td><td>117.46</td><td>0.60</td><td>1.66</td><td>15.03</td><td>0.64</td><td>1.35</td><td>8.11</td><td>0.34</td><td>0.77</td><td>6.33</td><td>0.42</td></tr>
      <tr><td>ui*pi</td><td>2.86</td><td>130.34</td><td>0.66</td><td>1.83</td><td>16.58</td><td>0.70</td><td>1.50</td><td>8.99</td><td>0.37</td><td>0.82</td><td>6.77</td><td>0.44</td></tr>
      <tr><td>z*ng</td><td>1.97</td><td>89.89</td><td>0.42</td><td>1.28</td><td>11.54</td><td>0.45</td><td>1.14</td><td>6.82</td><td>0.27</td><td>0.64</td><td>5.28</td><td>0.33</td></tr>
    </tbody>
  </table>
</div>

Most gateways remain in the same rough range as the baseline, but some show much more extreme variation. In particular, `b*ie` exhibits very high CV values and very wide latency spans, including a Math-task range from roughly six seconds to over 273 seconds. Such variation is difficult to reconcile with a single stable backend path and may indicate switching between heterogeneous execution configurations.

<div class="paper-card">
<strong>Takeaway.</strong> Latency stability is not uniform across gateways. Large CV values and unusually wide latency ranges can serve as practical indicators of suspicious backend behavior.
</div>

## 5. Related Work

Research relevant to VeriFlow spans three overlapping areas: model identification, benchmarking, and service auditing.

In the first area, works such as LLMmap, instructional fingerprinting, UTF, AuditLLM, and FDLLM design probes or fingerprints that distinguish models based on observable behavior. These studies provide important tools for differentiating models, but their primary question is usually <em>what model is this?</em> rather than <em>is a third-party gateway faithfully invoking the model it claims to serve?</em>

In the second area, benchmark suites such as MMLU and HELM evaluate broad model capabilities across reasoning, robustness, calibration, and efficiency dimensions. Follow-up work extends these ideas to multimodal retrieval, prompt-template testing, networking questions, and cost-aware serving systems. These studies are valuable for measuring model quality, but they do not directly audit intermediary platforms that can alter routing, pricing, or context handling.

In the third area, service-auditing work examines prompt caching, hidden token usage, synthetic artifacts, privacy risks, and traffic patterns in LLM-related systems. Much of this literature focuses on first-party APIs, downstream applications, or single-dimension measurements. VeriFlow differs by treating third-party gateways as the primary measurement target and jointly auditing response behavior, long-context memory, billing, and latency.

## 6. Conclusion

We introduced VeriFlow, a practical framework for auditing third-party LLM gateways along four dimensions: response-content consistency, multi-turn behavior, billing accuracy, and latency stability. By validating the approach on official APIs and then applying it to ten commercial gateways, we show that third-party gateway behavior can diverge materially from the behavior that users may expect from the claimed upstream model.

Our measurements reveal several forms of opacity, including likely model downgrading or substitution, degraded memory retention in long conversations, deviations from public pricing expectations, and large differences in latency stability across services. These findings suggest that gateway transparency is not yet mature and that black-box client-side auditing will remain important as the ecosystem grows.

We hope VeriFlow can serve as a foundation for future long-term studies across regions, time windows, and newly released model families, and for stronger accountability mechanisms in the LLM gateway ecosystem.

## References

<ol class="paper-ref-list">
  <li id="ref-aiindex">Stanford Institute for Human-Centered Artificial Intelligence. <em>Artificial Intelligence Index Report 2025</em>. Stanford HAI, 2025.</li>
  <li id="ref-openrouter">OpenRouter. "An overview of OpenRouter's API." <a href="https://openrouter.ai/docs/api-reference/overview">https://openrouter.ai/docs/api-reference/overview</a>.</li>
  <li id="ref-jimmy">Jimmy Song. "In-Depth Analysis of AI Gateway: The New Generation of Intelligent Traffic Control Hub." <a href="https://jimmysong.io/en/blog/ai-gateway-in-depth/">https://jimmysong.io/en/blog/ai-gateway-in-depth/</a>.</li>
  <li id="ref-reddit">Reddit discussion. "Apparently all third party providers downgrade, none of them provide a max quality model." <a href="https://www.reddit.com/r/LocalLLaMA/comments/1nqkx7o/apparently_all_third_party_providers_downgrade/">https://www.reddit.com/r/LocalLLaMA/comments/1nqkx7o/apparently_all_third_party_providers_downgrade/</a>.</li>
  <li id="ref-auditllm">Maryam Amirizaniani, Elias Martin, Tanya Roosta, Aman Chadha, and Chirag Shah. "AuditLLM: A Tool for Auditing Large Language Models Using Multiprobe Approach." <em>arXiv preprint arXiv:2402.09334</em>, 2024.</li>
  <li id="ref-llmmap">Dario Pasquini, Evgenios M. Kornaropoulos, and Giuseppe Ateniese. "LLMmap: Fingerprinting for Large Language Models." In <em>Proceedings of USENIX Security</em>, 2025.</li>
  <li id="ref-fingerprint">Jiashu Xu, Fei Wang, Mingyu Derek Ma, Pang Wei Koh, Chaowei Xiao, and Muhao Chen. "Instructional Fingerprinting of Large Language Models." In <em>Proceedings of NAACL</em>, 2024.</li>
  <li id="ref-fingerprint2">Zhiguang Yang and Hanzhou Wu. "A Fingerprint for Large Language Models." <em>arXiv preprint arXiv:2407.01235</em>, 2024.</li>
  <li id="ref-utf">Jiacheng Cai, Jiahao Yu, Yangguang Shao, Yuhang Wu, and Xinyu Xing. "UTF: Under-trained Tokens as Fingerprints." In <em>Proceedings of ACL</em>, 2025.</li>
  <li id="ref-fdllm">Junbang Fu, Wenlong Dong, Chong Wang, Xutong Zhao, Jingwei Gao, Zhirui Hu, Shangbo Wu, Dong Wang, Yinzhen Wang, Xiaojuan Qi, Shuai He, Yujun Chen, and Tianyu Du. "FDLLM: A Dedicated Detector for Black-Box LLMs Fingerprinting." <em>arXiv preprint arXiv:2501.16029</em>, 2025.</li>
  <li id="ref-manifpt">Hae Jin Song, Mahyar Khayatkhoei, and Wael AbdAlmageed. "ManiFPT: Defining and Analyzing Fingerprints of Generative Models." In <em>Proceedings of CVPR</em>, 2024.</li>
  <li id="ref-mmlu">Dan Hendrycks, Collin Burns, Andy Zou, Steven Basart, Andy Lee, Dawn Kohlmeier, Wenliang Ju, Dawn Xiaodong Song, and Jacob Steinhardt. "Measuring Massive Multitask Language Understanding." <em>arXiv preprint arXiv:2006.04019</em>, 2020.</li>
  <li id="ref-math">Dan Hendrycks, Collin Burns, Saurav Kadavath, Akul Arora, Steven Basart, Eric Tang, Dawn Song, and Jacob Steinhardt. "Measuring Mathematical Problem Solving With the MATH Dataset." In <em>Proceedings of NeurIPS</em>, 2021.</li>
  <li id="ref-helm">Percy Liang, Rishi Bommasani, Tony Lee, Dimitris Tsipras, Dilara Soylu, Michihiro Yasunaga, Yian Zhang, Deepak Narayanan, Yuhuai Wu, Ananya Kumar, et al. "Holistic Evaluation of Language Models." <em>Transactions on Machine Learning Research</em>, 2023.</li>
  <li id="ref-gpqa">Hugging Face dataset entry. "GPQA-Diamond." <a href="https://huggingface.co/datasets/fingertap/GPQA-Diamond">https://huggingface.co/datasets/fingertap/GPQA-Diamond</a>.</li>
  <li id="ref-latent">Guan Zhe Hong, Bhavya Vasudeva, Vatsal Sharan, Cyrus Rashtchian, Prabhakar Raghavan, and Rina Panigrahy. "Latent Concept Disentanglement in Transformer-based Language Models." <em>arXiv preprint arXiv:2506.16975</em>, 2025.</li>
  <li id="ref-cache-openai">OpenAI. "Prompt caching." <a href="https://platform.openai.com/docs/guides/prompt-caching">https://platform.openai.com/docs/guides/prompt-caching</a>.</li>
  <li id="ref-cache-gemini">Gemini API. "Context caching." <a href="https://ai.google.dev/gemini-api/docs/caching">https://ai.google.dev/gemini-api/docs/caching</a>.</li>
  <li id="ref-hidden-bill">Guoheng Sun, Ziyao Wang, Xuandong Zhao, Bowei Tian, Zheyu Shen, Yexiao He, Jinming Xing, and Ang Li. "Invisible Tokens, Visible Bills: The Urgent Need to Audit Hidden Operations in Opaque LLM Services." <em>arXiv preprint arXiv:2505.18471</em>, 2025.</li>
  <li id="ref-hidden-tokens">Ziyao Wang, Guoheng Sun, Yexiao He, Zheyu Shen, Bowei Tian, and Ang Li. "Predictive Auditing of Hidden Tokens in LLM APIs via Reasoning Length Estimation." <em>arXiv preprint arXiv:2508.00912</em>, 2025.</li>
  <li id="ref-imc25">Ruizhi Cheng, Surendra Pathak, Guowu Xie, Matteo Varvello, Songqing Chen, and Bo Han. "Hello, GenAI? Dissecting Human to Generative-AI Calling." In <em>Proceedings of IMC</em>, 2025.</li>
  <li id="ref-metal">Sangwon Hyun, Mingyu Guo, and M. Ali Babar. "METAL: Metamorphic Testing Framework for Analyzing Large-Language Model Qualities." In <em>Proceedings of IEEE ICST</em>, 2024.</li>
  <li id="ref-serverlessllm">Yao Fu, Leyang Xue, Yeqi Huang, Andrei-Octavian Brabete, Dmitrii Ustiugov, Yuvraj Patel, and Luo Mai. "ServerlessLLM: Low-Latency Serverless Inference for Large Language Models." In <em>Proceedings of USENIX OSDI</em>, 2024.</li>
  <li id="ref-privacy">Yashothara Shanmugarasa, Ming Ding, M. A. P. Chamikara, and Thierry Rakotoarivelo. "SoK: The Privacy Paradox of Large Language Models: Advancements, Privacy Risks, and Mitigation." In <em>Proceedings of ASIA CCS</em>, 2025.</li>
  <li id="ref-synthetic">Yixin Wu, Ziqing Yang, Yun Shen, Michael Backes, and Yang Zhang. "Synthetic Artifact Auditing: Tracing LLM-Generated Synthetic Data Usage in Downstream Applications." In <em>Proceedings of USENIX Security</em>, 2025.</li>
  <li id="ref-net-questions">Mubashir Anwar and Matthew Caesar. "Understanding Misunderstandings: Evaluating LLMs on Networking Questions." <em>SIGCOMM Computer Communication Review</em>, 2025.</li>
</ol>

</div>
