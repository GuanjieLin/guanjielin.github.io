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
</div>

## Abstract

Third-party Large Language Model (LLM) API gateways are rapidly emerging as unified access points to models offered by multiple vendors.
However, the internal routing, caching, and billing policies of these gateways are largely undisclosed, leaving users with limited visibility into whether requests are served by the advertised models, whether responses remain faithful to upstream APIs, or whether invoices accurately reflect public pricing policies.
To address this gap, we introduce VeriFlow, a lightweight black-box measurement framework for evaluating behavioral consistency and operational transparency in commercial LLM gateways.
VeriFlow is designed to detect key misbehaviors, including model downgrading or switching, truncation, billing inaccuracies, and instability in latency by auditing gateways along four critical dimensions: response content analysis, multi-turn conversation performance, billing cccuracy, and latency characteristics.
Our measurements across $10$ real-world commercial LLM API gateways reveal frequent gaps between expected and actual behaviors, including silent model substitutions, degraded memory retention, deviations from announced pricing, and substantial variation in latency stability across platforms.

## 1. Introduction

Large Language Models (LLMs) such as OpenAI’s GPT, Anthropic’s Claude, and Google’s Gemini are increasingly integrated into a broad range of applications~\cite{AIIndex2025,Hao:IMC2025}.
Although these models are widely accessible through cloud-based inference APIs, each vendor maintains its own independent API platform.
For developers and enterprise users who require access to multiple models from different providers, this fragmented ecosystem introduces substantial operational overhead, including complex backend integration, API key management, and billing processes~\cite{Jimmy:web2025}.

LLM gateways are emerging as a promising solution, offering a unified API interface with centralized billing that aggregates access to models from multiple vendors.
In such gateways, a single API key can be used to invoke different models, significantly simplifying deployment workflows and reducing integration and key management complexity.
In addition, LLM API gateways often offer additional benefits such as load balancing across models, usage-based optimization, and in some cases discounted token pricing.
However, from the client’s perspective, these gateways operate as \emph{black-box} intermediaries with little visibility into their internal behaviors.
Thus, users cannot reliably verify whether requests use the intended model, whether context is truncated, or whether billing is accurate~\cite{Cheng:IMC25,Reddit:web2025,Sun:preprint25,Wang:preprint25,Shanmugarasa:SoKPrivacy25}.

Auditing these black-box gateways is challenging because their routing and model selection behaviors are not exposed to clients.
Existing efforts such as LLMmap~\cite{Pasquini:SEC25} use active probing to differentiate between LLMs for mostly open-source models, but does not target the behavioral transparency of commercial LLM gateways.
Other work on instructional fingerprints~\cite{Xu:NAACL24,Yang:FingerLLM24,Song:CVPR24}, UTF~\cite{Cai:ACL25}, AuditLLM~\cite{Amirizaniani:AuditLLM24}, and FDLLM~\cite{Fu:FDLLM25} focuses on analyzing model traits or downstream artifacts rather than evaluating whether third-party API gateways preserve upstream model behavior or comply with pricing rules.
These gaps motivate an efficient framework that measures the transparency and behavioral consistency of LLM gateways from the client’s perspective.

Building on these needs, we present VeriFlow, a systematic framework for audits gateway behavior transparency and consistency across four key dimensions.
VeriFlow performs response content analysis using a structured set of probing queries to generate behavioral profiles for different models, enabling the detection of potential model downgrading or substitution.
It evaluates multi-turn conversational consistency to identify model switching during extended conversations and to determine whether silent truncation occurs before reaching documented context or output limits.
VeriFlow further examines billing accuracy by comparing actual token consumption with reported usage and assessing differences between expected and reported costs, accounting for cached tokens.
Finally, it measures latency characteristics, quantifying variability in request and response delays.

We first demonstrate VeriFlow’s effectiveness and efficiency through controlled validation using official vendor model endpoints.
We then apply VeriFlow to $10$ commercial LLM API gateways, where we uncover significant gaps between expected and observed behaviors, including model substitutions, degraded memory retention, inaccurate billing, and substantial variability in request latency.

Our key research contributions are summarized as follows:

1. We identify the lack of transparency and consistency guarantees in LLM API gateways and motivate the need for systematic client-side auditing.
2. We design VeriFlow, a lightweight framework that measures gateway behavior across four dimensions: response content, multi-turn conversation consistency, billing accuracy, and latency characteristics.
3. We validate VeriFlow in controlled settings and apply it to $10$ commercial gateways, uncovering substantial discrepancies between expected and observed behavior.

## 2. Background and Motivation

LLM API gateways are increasingly adopted to abstract vendor differences and provide unified interfaces, load balancing, and centralized billing~\cite{Openrouter:web2025}.
As illustrated in Figure~\ref{fig:gateway-cheat}, a gateway acts as a proxy between client applications and upstream model providers.
However, the internal operation of these gateways remains largely non-transparent.
Users cannot observe how requests are routed, which upstream models are selected, what inference parameters are applied, or how billing is computed.
As a result, clients cannot determine whether a gateway follows documented policies or behaves consistently.
This lack of visibility raises concerns around several critical issues as shown in Figure~\ref{fig:gateway-cheat}:

<!-- Web-native redraw based on local Figure 1 semantics -->
<figure class="paper-figure">
  <img src="{{ '/assets/papers/api-gateway-imc2026/Fig1.png' | relative_url }}" alt="Overview of LLM API gateway architecture and the main transparency and consistency challenges.">
  <figcaption><strong>Figure 1.</strong> Overview of LLM API gateway architecture and the main transparency and consistency challenges.</figcaption>
</figure>

1. Model downgrading/switching:
   gateways may route requests to cheaper or less capable models despite advertising a premium model, often using internal routing policies driven by cost or latency considerations.
   Such routing decisions are typically undisclosed, leaving users unaware of which model actually served a request.
2. Prompt/response truncation: gateways may enforce their own context or output limits that are smaller than the model’s native capacity, silently truncating multi-turn prompts or responses without signaling the change and degrading service quality.
3. Billing inaccuracy:
   reported usage and actual token consumption may diverge, including cases where gateways charge for cached tokens~\cite{OpenAI:web,Gemini:web} or add extra tokens that were not processed.
4. Latency fluctuation: limited computational resources, especially during peak hours, along with extra processing and forwarding steps inside the gateway, as well as behaviors such as switching models, modifying user input, or changing API endpoints, can introduce significant variability in response latency at LLM gateways, negatively impacting service quality and reliability.

Prior work has examined hidden behaviors in LLM services, such as prompt caching, hidden token usage, and API-level security risks, but these studies primarily focus on first-party vendor's LLM API platforms rather than third-party LLM API gateways~\cite{Gu:PromptCache25,Hyun:ICST24,Sun:preprint25,Wang:preprint25,Wu:SEC25,Shanmugarasa:SoKPrivacy25,Yao:OSDI24}.
These challenges collectively motivate VeriFlow, a framework for systematically auditing behavioral transparency and consistency in black-box LLM API gateways.

## 3. Design of VeriFlow

### 3.1 Overview

This section describes the design of VeriFlow in detail.

VeriFlow is a lightweight, systematic auditing framework that operates entirely through the public APIs exposed by LLM gateways.
All measurements are performed using the OpenAI-compatible <span class="paper-inline-code">/v1/chat/completions</span> endpoint, ensuring a consistent request–response format across platforms.
The framework relies solely on information accessible to ordinary clients through standard interactions, without requiring privileged access or internal instrumentation.

Figure~\ref{fig:architecture} illustrates the overall structure of VeriFlow, which implements a multi-dimensional auditing pipeline to evaluate the response content, multi-turn conversation, billing accuracy, and latency characteristics.

<!-- Export source: ~\research-paper\api-gateway-imc2026\figures\fig21.pdf -> assets/papers/api-gateway-imc2026/architecture.png -->
<figure class="paper-figure">
  <img src="{{ '/assets/papers/api-gateway-imc2026/architecture.png' | relative_url }}" alt="Overall architecture of the VeriFlow framework.">
  <figcaption><strong>Figure 2.</strong> Overall architecture of the VeriFlow framework.</figcaption>
</figure>

### 3.2 Response Content Analysis

The goal of this dimension is to determine whether a gateway actually serves the requested model or silently replaces it with a different and often cheaper model.
To detect such substitution, we analyze the response behavior of different LLMs and use it to differentiate between models.
This is challenging because even the same model may generate varied responses to the same prompt, especially for open-ended questions, making naive text matching unreliable.
Prior work on LLM fingerprinting and identification primarily distinguishes models using lexical, semantic, or logit-space features extracted from free-form text~\cite{Pasquini:SEC25,Zhou:ACL24}.
However, these approaches are often sensitive to generation randomness and frequently fail to capture meaningful behavioral differences in critical fields (e.g., the final answer in a math query is far more important than the surrounding derivation text) when relying solely on text-level analysis.

Instead, our prompt design follows three requirements: (1) responses to the same probe should remain stable across repeated queries to the same model,
(2) responses should differ across models because they reflect model-specific capabilities, and these differences should be identifiable through key feature dimensions, and
(3) the prompt suite should be lightweight so that auditing remains efficient.

To formalize this analysis, we adopt a formulation following prior work~\cite{Pasquini:SEC25,Zhou:ACL24}, treating each model version $v$ as a stochastic mapping

$$
u \sim E_v(p,\theta),
$$

where a probe $p\in\mathcal{P}$ and generation parameters $\theta$ produce an output $u$ with metadata~$m$.

#### Prompt design

Following the three requirements mentioned above, we design prompts that (i) structure model responses for analysis and (ii) expose key response features that can effectively differentiate models.
Each prompt instructs the LLM to generate explicit step-by-step reasoning leading to a final answer, and the response is required to follow a shared JSON schema that enforces a consistent output format across models and runs.

When designing the prompt content, We deliberately avoid two unsuitable choices.
First, we avoid banner-grabbing questions such as “What is your model version?”, since they are easily spoofed through system-prompt manipulation and yield inconsistent identifiers across gateways~\cite{Pasquini:SEC25}.
Second, we avoid using large public benchmarks at API scale, as they are expensive to run and risk data contamination~\cite{Hendrycks:MMLU2020,Dan:NIPS2021}.

Motivated by these requirements and constraints, we design a probe suite $\mathcal{S}$ that captures distinctive behavioral signatures across models, including differences in reasoning ability, knowledge cutoff, mathematical competence, and output style (e.g., preferred symbols or \LaTeX~formatting).
To cover these dimensions, we design prompts across four domains:

1. \emph{AIME (American Invitational Mathematics Examination)}: numeric-answer problems that test precise computation and mathematical reasoning~\cite{Liu:ACL2025};
2. \emph{GPQA (Graduate-Level Google-Proof Q\&A)}: multiple-choice questions designed to expose deep reasoning and deliberation capabilities across models~\cite{Hugging:GPQA2025};
3. \emph{Factual Recall}: questions about major events between 2021–2025 that assess knowledge cutoff and factual retrieval ability;
4. \emph{Geographic Information Inference}: implicit reasoning tasks that require step-by-step linking of intermediate facts to identify a specific geographic feature.

Building on discrete concept composition (DCC)~\cite{Guan:Latent2025}, each prompt instructs LLM to compose disconnected facts across multiple reasoning hops, making intermediate choices such as ordering, granularity, and error types directly observable.
Concretely, each response is required to follow a structured format with two fields:
<span class="paper-inline-code">knowledge_path</span> (an array of intermediate reasoning steps) and
<span class="paper-inline-code">final_answer</span> (the final result).
A complete specification of the request template can be found in Appendix~\ref{app:dcc-template}.
This structure helps to remove most free-form variations in responses so that observable differences mainly reflect model capabilities rather than surface text patterns.
It also exposes reasoning strategies that remain stable across repetitions.
For example, when asked \textit{``What is the highest geographic feature associated with the origin area of the Starbucks corporation?''}, GPT-5 consistently avoids detailed step-by-step reasoning and instead produces a short summary, whereas other models produce explicit multi-hop chains of inference.

#### Model signature extraction

For each structured response obtained from a prompt, we extract a $d$-dimensional signature vector $\Phi(u,m)$ rather than relying on text-level embeddings.
This enables robust differentiation between models by capturing behavioral and structural characteristics.
The signature vector is composed of five feature families:
(i) answer quality: correctness of the final answer and whether it appears in the correct location,
(ii) reasoning structure: reasoning depth, mean step length, and variance,
(iii) scale: response length and density,
(iv) style: presence of numeric expressions or \LaTeX\ formatting, and
(v) parsing quality: whether parsing occurs and at what degree.
Full feature definitions can be found in Appendix~\ref{app:binary-config}.
Collecting signatures across probes and repetitions yields, for each model version, a behavioral signature matrix.Collecting signatures across probes and repetitions yields, for each model version, a behavioral signature matrix.
Using these signatures, we train lightweight per-model classifiers. For each model $v$, a one-vs-rest XGBoost classifier is trained to distinguish signatures produced by $v$ from those of all other models.

### 3.3 Multi-turn Conversation Performance

LLM applications typically involve multi-turn conversations, where users expect the model to retain context, chat history, and intermediate results across turns.
Since most LLMs are inherently stateless, the full conversation history is included in every request to preserve context in multi-turn interactions.
Under normal conditions, this enables consistent behavior and correct recall of information introduced earlier in the dialog.
However, a black-box gateway can silently break these expectations by switching back-end models to cheaper alternatives or truncating conversation history to reduce token consumption.

In this dimension, our goal is to evaluate gateway performance in multi-turn interactions and detect failures arising from silent model switching and hidden prompt or response truncation.
To accomplish this, we construct a multi-turn testing procedure that embeds repeated questions and explicit memory checkpoints to assess whether early information is retained and updated correctly, and whether response consistency is preserved throughout the conversation.

#### Multi-Turn Conversation Design

We design a $25$-turn conversation template specifically for testing third-party LLM API gateways.
A $25$-turn length offers a practical balance, providing enough depth to expose multi-turn consistency issues and cover diverse test cases while remaining lightweight and efficient in token usage.
A detailed template with example content is provided in Appendix~\ref{app:conv-template}.

The conversation begins by assigning the model a stable identity and a user-specific preference.
Two segments of distractor discussion on unrelated topics are then inserted to reduce the immediate salience of this information.
Midway through the dialog, the preference is first checked and then explicitly updated by the user, after which the conversation again shifts to unrelated content.
In the final two turns, the model is asked to restate both the identity and the current preference.
During the process, we also collect \emph{metadata from all responses}, including the <span class="paper-inline-code">system_fingerprint</span> and cached token counts.
<span class="paper-inline-code">system_fingerprint</span> serves as a good sign for potential model switching, as it typically changes when the underlying model is replaced.
The number of cached tokens is also informative, since switching models resets the cache-hit mechanism, causing a drop in cached token usage.
This structure allows us to test whether the gateway-served model (i) retains information introduced early in the conversation, (ii) correctly overwrites outdated preferences, (iii) avoids hallucinating attributes that were never provided, and (iv) maintains consistent behaviors during the entire interaction.

#### Indicators and Detection Goals

For each model offered through each gateway, we run multi-turn conversations using the template and evaluate performance based on three indicators that collectively quantify conversational consistency and context retention: (i) Memory Checkpoint Pass Rate: the fraction of correctly recalled identity and preference values at predefined checkpoints (e.g., at turns 10, 24, and 25), (ii) System Fingerprint Stability: the number of distinct <span class="paper-inline-code">system_fingerprint</span> values observed across turns, which can indicate silent model switching;, and (iii) Cached Token Usage Rate, the ratio of cached prompt tokens to total input tokens as reported by API metadata.

### 3.4 Billing Accuracy

Billing is a critical factor for third-party LLM gateways, as users ultimately care about whether they are charged fairly.
In black-box API gateways, cost discrepancies can arise from (i) incorrect token consumption reporting, (ii) improper handling of cached tokens, and (iii) incorrect cost calculations based on published pricing.

In the billing accuracy analysis, we first compute the actual token consumption locally and compare it against the values reported in the gateway console.
We also evaluate whether each gateway charges fees consistent with the reported token usage and the unit prices it publishes.
For each request, we record the number of input tokens $n_{\text{in}}$, cached tokens $n_{\text{cached}}$, and output tokens $n_{\text{out}}$, along with the published per-token rates $p_{\text{in}}$, $p_{\text{cached}}$, and $p_{\text{out}}$.
The expected cost for a single call is then computed as:

$$
C_{\text{expected}} =
(n_{\text{in}} - n_{\text{cached}})\,p_{\text{in}}
+ n_{\text{cached}}\,p_{\text{cached}}
+ n_{\text{out}}\,p_{\text{out}}.
$$

gateways that do not support separate cache pricing or fail to apply cache discounts are evaluated with $n_{\text{cached}} = 0$.

### 3.5 Latency Characteristics

Latency is an important performance metric in LLM gateways and can also serve as an indicator of potential misbehaviors such as model switching or downgrading, since different models often exhibit distinct processing times.
As a result, switching to a different model may introduce noticeable variation in latency.
In this evaluation, we conduct latency measurements by issuing repeated requests for a given probe across gateways within a tightly bounded time window.
This controlled setup reduces external influences such as network dynamics, allowing latency variation to more reliably reflect gateway-side behavior.

When a gateway consistently serves a fixed claimed model on probes with comparable prompt and output lengths under fixed parameters, the resulting latency distribution should remain stable. We quantify this stability using the coefficient of variation (CV),

$$
\mathrm{CV} = \sigma_T / \mu_T,
$$

where $\sigma_T$ and $\mu_T$ are the standard deviation and mean over $K$ repeated invocations of the same probe.
In contrast, model switching across heterogeneous execution paths typically increases CV and can lead to bimodal or multi-modal latency distributions.
Elevated or highly inconsistent CV therefore serves as an indicator of unstable back-end behaviors for LLM API gateways.

## 4. Evaluation

### 4.1 Data Collection

For official vendor platforms, we collect behavioral signatures from $24$ LLMs exposed through their native APIs.
Using the standardized probe suite $\mathcal{S}$ under fixed parameters, each model is queried with $K=12$ repetitions per probe, producing $15{,}840$ records in total ($660$ per model) covering response-content features and latency measurements.
The full sampling protocol can be found in Appendix~\ref{app:exp-settings}.

For third-party platforms, we audit $10$ commercial LLM gateways using the same probe suite and parameters.
Gateways are anonymized using first–last-letter encodings:
<span class="paper-inline-code">oer</span>, <span class="paper-inline-code">aix</span>, <span class="paper-inline-code">oub</span>, <span class="paper-inline-code">zng</span>, <span class="paper-inline-code">oey</span>, <span class="paper-inline-code">uipi</span>, <span class="paper-inline-code">bie</span>, <span class="paper-inline-code">unpi</span>, <span class="paper-inline-code">ayi</span>, <span class="paper-inline-code">lub</span>.
Results represent a point-in-time snapshot rather than a long-term ranking of individual services.
For single-turn evaluation, each model on each gateway is queried with the prompt suite using five repetitions.
For multi-turn evaluation, we run the standardized $25$-turn conversation template, also repeated five times per model per gateway.
Overall, approximately \textbf{1M tokens} are consumed per model during testing, which remains reasonably sustainable in practice. This cost can be further reduced by lowering the repetition count if needed.

### 4.2 Controlled Validation

Before applying VeriFlow to third-party gateways, we first validate on official vendor APIs that the response-content signatures introduced in Section~\ref{sec:content-analysis} are sufficiently discriminative under controlled settings where the ground-truth model identity is known.

For each model version $v$ available through official vendor APIs, we train a classifier that distinguishes signatures generated by $v$ from those generated by all other models, using the probe suite $\mathcal{S}$ and the feature configuration described in Section~\ref{sec:content-analysis}.
Data splits, threshold selection, and hyperparameter settings are summarized in Appendix~\ref{app:binary-config}, with detailed per-model metrics reported in Appendix~\ref{app:binary-results}.
Evaluating these classifiers on labeled test data collected by querying vendor endpoints with $\mathcal{S}$, we observe an average $F1$ score of $0.968 \pm 0.085$ across all $24$ models, with most models exceeding $0.95$.
Considering that our evaluation includes closely related variants within the same model family (e.g., \texttt{gpt-4o-mini} and \texttt{gpt-4.1-nano}), these results demonstrate that our response-content analysis exhibits strong discriminative power and can reliably distinguish LLM models.

We also evaluate the robustness of our method on \textbf{unseen models} by applying the trained ensemble to $5$ additional LLMs (Claude sonnet 4.5, Claude haiku 4.5, Qwen-plus, Qwen-turbo and DeepSeek-V3.2-Exp) not included in the original set of 24.
In the evaluation, none of these unseen models is mistakenly classified as any known model.
This indicates that our method behaves conservatively in controlled settings and avoids misclassification when encountering new model variants.
Extending the ensemble to identify new models is also lightweight as training an additional classifier requires \emph{less than $1$ second} per model.

### 4.3 Third-party API Gateway Evaluation

#### 4.3.1 Response Content Evaluation

reports the proportion of responses classified as the \emph{claimed} upstream model for four representative models across different gateways (extended results for all models can be found in Appendix~\ref{app:content_result}).
Each percentage is computed over $275$ responses per model.

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

For gpt-4o, most gateways generate responses that are consistently identified as the claimed model, while platforms such as \texttt{bie} and \texttt{ayi} exhibit noticeably lower consistency.
For gpt-5, identification rates vary significantly across gateways, with several platforms frequently classified as models outside the \texttt{gpt-5} family—indicating possible model substitution.
For \texttt{gemini-2.5-pro} and \texttt{claude-sonnet-4.0}, platform support is limited and behavior is unstable.
The official APIs and a few gateways maintain high identification rates above $95\%$, whereas several others fall below $60\%$, showing that they do not reliably preserve the identity of the claimed model.

\textbf{Takeaway:} For certain models, responses from several gateways show substantial variation. This indicates that these gateways may route user's prompt to a different model than the requested one.

#### 4.3.2 Multi-turn Conversation Evaluation

Table~\ref{tab:memory_singlecol} summarizes the multi-turn conversation performacnes for gpt-4o and gpt-4o-mini across the vendor's baseline API platforms and $10$ third-party gateways, where T10/24/25 indicates checkpoint pass count at turn $10$, $24$, and $25$, FC indicates system\_fingerprint count, and CR indicates cache rate(\%). Extended results are presented in Appendix~\ref{app:conversation_result}.

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

For gpt-4o, the official API passes all checkpoints with only $1$ unique fingerprint and moderate cache reuse.
Gateways such as l*ub, o*er, and un*pi largely match this behavior, while others do not pass checkpoints at turns 24 and 25 or introduce additional fingerprints in most cases.
For gpt-4o-mini, behavior is less stable even on the baseline, and most gateways forgets identity and preference by the final checkpoints.
Two platforms show notable anomalies.
Platform a*yi has very similar checkpoint passing and cache rate performances for gpt-4o and gpt-4o-mini, indicating both of them may be switched to the same model.
Platform o*ey achieves the highest checkpoint passing counts for gpt-4o-mini among all gateways while reporting zero cache usage, suggesting either a non-canonical gpt-4o-mini implementation or aggressive, opaque caching that alters long-context behavior relative to the upstream API.

\textbf{Takeaway.} Long-context retention and infrastructure behavior vary substantially across gateways: some preserve the upstream LLM’s behavior, while others lose state or change back-end configurations during the conversation.

#### 4.3.3 Billing Accuracy Evaluation

Table~\ref{tab:billing-aggregated} demonstartes the billing accuracy results for gpt-4o by comparing the expected cost from public prices with the actual amount charged by each gateway. Extended results are presented in Appendix~\ref{app:billing_result}.

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

Most gateways match the expected cost and do not have any billing gap. A small number of platforms charge more than expected. a*ix has a billing gap of $7.6\%$ while o*ey has the billing gap as $62.8\%$ even though the token usage is similar to other platforms.

\textbf{Takeaway.} Billing outcomes vary across gateways. Most platforms follow vendor pricing while a few charge significantly more than the expected cost.

#### 4.3.4 Latency Evaluation

Table~\ref{tab:latency-cv} summarizes the latecny measurement results for gpt-4o across the across the vendor's baseline API platforms and $10$ third-party gateways. Extended results are presented in Appendix~\ref{app:cv_result}.
Gateway b*ie exhibits marked instability, characterized by anomalously large CV vlaues and wide disparities between minimum and maximum response times. For instance, in the Math task, latencies span from $\approx 6$ seconds to over $273$ seconds, resulting in a CV ($1.10$) almost double the baseline. This indicates that b*ie may switch between different models.

\textbf{Takeaway.} Latency stability is not uniform across gateways. High variation may indicate suspicious back-end behavior such as model downgrading or switching.

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

## 5. Related Work

Research on LLMs spans model identification and fingerprinting, benchmarking, and service auditing.
LLMmap~\cite{Pasquini:SEC25} uses active probing to identify base models across vendors.
Instructional fingerprinting~\cite{Xu:NAACL24}, A Fingerprint for LLMs~\cite{Yang:FingerLLM24}, UTF~\cite{Cai:ACL25}, AuditLLM~\cite{Amirizaniani:AuditLLM24}, and FDLLM~\cite{Fu:FDLLM25} design fingerprints or multi-probe strategies to distinguish and audit models.
Outside the LLM domain, ManiFPT~\cite{Song:CVPR24} formalizes fingerprints of generative models.
These works focus on recognizing individual models rather than the behavior of intermediary gateways.

Benchmarks such as MMLU~\cite{Hendrycks:MMLU2020} and HELM~\cite{Liang:HELM} measure capability, robustness, and efficiency across tasks.
Follow-up work studies multimodal retrieval~\cite{Luo:WWW25}, testing of prompt templates~\cite{Hyun:ICST24}, and cost-aware serverless inference~\cite{Yao:OSDI24}.
These lines of work evaluate what models can do on tasks but do not audit whether a third-party gateway invokes the declared model, preserves long-context behavior, or applies pricing policies correctly.

Service auditing for web APIs has focused on throughput, availability, and latency.
Recent work audits LLM APIs for prompt caching~\cite{Gu:PromptCache25} and traces synthetic artifacts in downstream systems~\cite{Wu:SEC25}.
Security and privacy studies on public LLM interfaces highlight extraction and inference risks~\cite{Cheng:KDD25,Hao:IMC2025} and systematize privacy challenges~\cite{Shanmugarasa:SoKPrivacy25}.
Other papers analyze vulnerabilities in reasoning and evaluation suites~\cite{Gawin:WWW25,Anwar:CCR25}, and network measurements dissect human-to-GenAI calling patterns in the wild~\cite{Cheng:IMC25}.
Prior studies therefore audit vendor APIs, cloud platforms, or downstream applications, sometimes scanning a single dimension on a public gateway.
VeriFlow instead treats third-party LLM gateways as the primary measurement object and jointly compares response behavior, multi-turn memory, latency stability, and billing against the documented policies of upstream vendors.

## 6. Conclusion

We introduced VeriFlow, a framework for auditing third-party LLM gateways along content, multi-turn, billing, and latency dimensions.
Our measurements on official APIs and ten commercial gateways reveal significant transparency gaps, including downgraded models and pricing deviations.
We hope VeriFlow will serve as a starting point for long-term, multi-region monitoring and stronger accountability mechanisms in the gateway ecosystem.

## Appendix

### Ethics

In this work, we use only public APIs of vendors and we do not capture user traffic. We anonymize commercial platforms and we do not disclose real platform names. Our study does not involve any personal information.

### DCC Prompt Template

Table~\ref{tab:dcc-prompt} presents the complete Discrete Concept Composition (DCC) prompt template used for eliciting structured behavioral signatures.
The design deliberately separates the reasoning process from the final result to facilitate the feature extraction described in Section~\ref{sec:content-analysis}.

{% raw %}
```text
\begin{table*}[t]
\centering
\caption{DCC standardized prompt template specification.}
\label{tab:dcc-prompt}
\footnotesize
\begin{tabular}{|p{0.48\textwidth}|p{0.48\textwidth}|}
\hline
\multicolumn{2}{|c|}{\textbf{System Message}} \\
\hline
\multicolumn{2}{|p{0.97\textwidth}|}{You are a meticulous reasoning engine. Your task is to solve multi-step problems by thinking step-by-step and to clearly articulate your reasoning process. Your final output must be a single JSON object.} \\
\hline
\multicolumn{2}{|c|}{\textbf{User Prompt Template}} \\
\hline
\multicolumn{2}{|p{0.97\textwidth}|}{%
Based on the following question, provide your step-by-step reasoning path and the final answer.

\textbf{Question}: \{question\_prompt\_implicit\}

\textbf{Required Output Format}:
Your entire response must be a single JSON object containing the following two keys:

1. \texttt{knowledge\_path}: An array of strings. Each string in the array should represent a distinct step in your reasoning process.

2. \texttt{final\_answer}: A string containing the final answer.

\textbf{Example}:

\textbf{Question}: What is the highest geographic feature associated with the origin area of the Starbucks corporation?

\textbf{Your Output should be}:

\texttt{\small
\{ "knowledge\_path": ["Starbucks originated in Seattle, Washington.", "The highest geographic feature in the state of Washington is Mount Rainier."], "final\_answer": "Mount Rainier" \}
}

Now, please apply this reasoning process and format to the following question.

\textbf{Question}: \{question\_prompt\_implicit\}
} \\
\hline
\end{tabular}
\end{table*}
```
{% endraw %}

### Sampling Protocol and Probe Suite

This appendix summarizes the sampling protocol and lists the probe suite used in our study. We collect behavioral signatures from official APIs of vendors and from third party gateways using the same parameters.

1. Models: 24 models from three vendors for baseline collection.
2. Repetitions: $K=12$ per probe with temperature equal to 0.7.
3. Spacing: consecutive samples for the same probe are spaced by at least two hours to mitigate cache effects.

Table~\ref{tab:probe-suite} provides the composition of the behavioral probe suite $\mathcal{S}$.

<div class="paper-table-wrap">
  <table class="paper-table">
    <caption><strong>Appendix Table.</strong> Composition of the behavioral probe suite $\mathcal{S}$.</caption>
    <thead>
      <tr>
        <th>Category</th>
        <th>N</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>AIME</td><td>15</td></tr>
      <tr><td>GPQA</td><td>10</td></tr>
      <tr><td>Geographic Feature</td><td>15</td></tr>
      <tr><td>Factual Recall</td><td>15</td></tr>
      <tr><td><strong>Total</strong></td><td><strong>55</strong></td></tr>
    </tbody>
  </table>
</div>

### Conversation Protocol

Table~\ref{tab:conversation-template} presents the standardized 25-turn conversation template used to evaluate memory retention in Section~\ref{sec:conversation}.
It defines the precise sequence of turns, goals, and example content to create controlled context pressure.

Crucially, this protocol also serves as the standardized workload for our Billing Accuracy evaluation (Section~\ref{sec:billing}).
Since complex billing logic (such as prompt caching discounts) is most active during long-context interactions, this fixed 25-turn sequence provides a stable baseline for auditing costs.
The billing metrics reported in our study—including expected cost ($C_{\text{exp}}$), actual cost ($C_{\text{act}}$), and the billing gap—are computed by averaging the token usage and charges recorded across the five independent repetitions of this conversation protocol for each model in each gateway.

<div class="paper-table-wrap">
  <table class="paper-table">
    <caption><strong>Appendix Table.</strong> Standardized conversation protocol with example content.</caption>
    <thead>
      <tr>
        <th>Turn(s)</th>
        <th>Purpose</th>
        <th>Example content</th>
      </tr>
    </thead>
    <tbody>
      <tr><td>1</td><td>Assign identity and initial preference</td><td>You are a toy expert. Your current favorite toy is LEGO.</td></tr>
      <tr><td>2--9</td><td>Distractor segment on an unrelated topic</td><td>Discuss properties of plastics used in consumer goods. Summarize trade offs among durability, weight, and cost.</td></tr>
      <tr><td>10</td><td>Memory checkpoint</td><td>What is your professional identity now?</td></tr>
      <tr><td>11</td><td>Preference update</td><td>Your favorite toy is now Transformers.</td></tr>
      <tr><td>12--23</td><td>Second distractor segment and light math</td><td>Answer short questions about electric vehicles. Compute a simple battery charging time using $t = C \times \frac{0.8 - 0.2}{P \times \eta}$.</td></tr>
      <tr><td>24--25</td><td>Final memory checkpoints</td><td>What is your professional identity? What is your favorite toy now?</td></tr>
    </tbody>
  </table>
</div>

### Binary Classifier Configuration

#### Feature Engineering

For each response we extract a signature vector using the function
$\Phi$ described in Section\,3.2.2.  The vector comprises answer quality (whether answer match and its appearance position), reasoning structure (depth, mean step length and variance), scale (response length and density), style (whether has \LaTeX\ or numeric) and parsing quality (whether parsing occurs and what degree).  For each base feature we compute contrastive statistics relative to the distribution of all other models on the same
<span class="paper-inline-code">test_id</span>, including mean difference, relative difference,
Cohen’s $d$, standard deviation ratio and distribution overlap.  We
also compute a ranking feature indicating the position of the target
model among all 24 models for that feature.

#### Training and Hyper-parameters

We frame model identification as 24 independent one-vs-rest
binary classification problems.  For each model $m$, records with
<span class="paper-inline-code">model_name</span>$=m$ are treated as positive and all others as
negative.  We split responses for each $(m,\texttt{test\_id})$ pair
into 10 training and two testing samples, yielding 13{,}200 training
instances and 2{,}640 testing instances per classifier.  Because
positives are outnumbered $1:23$, we perform 20\,× random
oversampling of the minority class using RandomOverSampler.  A
difficulty-adaptive weighting scheme is then applied via
<span class="paper-inline-code">scale_pos_weight</span>: models deemed \emph{easy} use
$\sqrt{\rho}$, \emph{medium} use $\rho^{0.7}$ and \emph{hard} models use
$\rho^{0.9}$ where $\rho$ is the post-oversampling negative-to-positive
ratio ($\approx 1.15$).

We train XGBoost classifiers with objective binary:logistic,
max\_depth of 6, 500 trees, learning rate 0.1,
subsample and colsample\_bytree equal to 0.8, and
$\ell_1/\ell_2$ regularization terms $(\alpha,\lambda)=(0.1,1.0)$.  Early
stopping on a held-out validation subset with 30 rounds prevents
overfitting.  For each classifier we sweep the decision threshold
between 0.1 and 0.95 in steps of 0.05; the optimal threshold is
chosen to maximize the F1 score (medium and easy models) or recall
(hard models) subject to a minimum precision of 0.5 (easy/medium) or
0.35 (hard).  On average the classifiers achieve an F1 score of
0.932, precision 0.928, recall 0.945 and AUROC 0.988.

### Per Model Performance Metrics

Per model metrics on the test set appear in Table~\ref{tab:per_model_performance_test}, and performance on the small probe subset in Table~\ref{tab:per_model_performance_elite}.

To drive the gateway audits we distill each model’s probe suite down to
a compact small subset. Algorithm~\ref{alg:elite-probe-selection}
summaries the deterministic selection loop: we score every probe,
retain those that cleanly separate the target model, and backfill the
budget using XGBoost gain importance when necessary. We use $Q=12$ probes and a separation margin of $\delta=0.35$
consistent with the experiments in Section~\ref{sec:content-eval}.

```text
\begin{algorithm}[t]
  \caption{Selecting the small subset probe vector $\mathcal{S}_m^{'}$ for model $m$}
  \label{alg:elite-probe-selection}
  \KwIn{Trained XGBoost classifier $f_m$, probe set $\mathcal{S}$, budget $Q$, separation margin $\delta$}
  \KwOut{Small subset probe vector $\mathcal{S}_m^{'}$}
  \ForEach{$(s,i) \in \mathcal{S} \times \text{tests}$}{
    Compute $p_{s,i} \leftarrow f_m(s,i)$
  }
  \ForEach{$s \in \mathcal{S}$}{
    $\bar{p}_s \leftarrow \frac{1}{|\mathcal{I}_s|}\sum_{i \in \mathcal{I}_s} p_{s,i}$ where $\mathcal{I}_s$ indexes samples produced by probe $s$
  }
  $\mathcal{C} \leftarrow \{s \in \mathcal{S} \mid \bar{p}_s - \max_{n \neq m} \bar{p}_{s,n} \ge \delta\}$\;
  $\mathcal{S}_m^{'} \leftarrow$ Top-$Q$ probes in $\mathcal{C}$ ranked by $\bar{p}_s$\;
  \If{$|\mathcal{S}_m^{'}| < Q$}{
    Rank remaining probes by XGBoost gain importance and append greedily until $|\mathcal{S}_m^{'}| = Q$
  }
  \Return $\mathcal{S}_m^{'}$
\end{algorithm}
```

```text
\begin{table}[t]
  \centering
  \caption{Performance of the 24 binary classifiers on the test set.
    Models are sorted by F1 score.}
  \label{tab:per_model_performance_test}
  \scriptsize
  \begin{tabular}{lcccc}
    \toprule
    Model & F1 & Precision & Recall & AUROC \\
    \midrule
    gemini\text-2.5\text-flash\text-lite & 0.999 & 0.997 & 1.000 & 1.000 \\
    claude\text-3\text-haiku\text-20240307 & 0.988 & 0.984 & 0.991 & 0.999 \\
    claude\text-opus\text-4\text-1\text-20250805 & 0.980 & 0.978 & 0.982 & 0.998 \\
    claude\text-3\text-5\text-sonnet\text-20241022 & 0.967 & 0.954 & 0.982 & 0.996 \\
    gpt\text-3.5\text-turbo & 0.962 & 0.961 & 0.964 & 0.995 \\
    claude\text-3\text-7\text-sonnet\text-20250219 & 0.958 & 0.960 & 0.955 & 0.994 \\
    claude\text-sonnet\text-4\text-20250514 & 0.951 & 0.957 & 0.945 & 0.993 \\
    gpt\text-5 & 0.946 & 0.959 & 0.973 & 0.992  \\
    gemini\text-2.5\text-pro & 0.943 & 0.954 & 0.964 & 0.991 \\
    gemini\text-2.0\text-flash & 0.941 & 0.950 & 0.982 & 0.990 \\
    gemini\text-2.0\text-flash\text-lite & 0.888 & 0.884 & 0.891 & 0.967 \\
    gpt\text-4o\text-mini & 0.902 & 0.855 & 0.955 & 0.975  \\
    gpt\text-4.1 & 0.897 & 0.838 & 0.964 & 0.971  \\
    gpt\text-4.1\text-nano & 0.891 & 0.874 & 0.909 & 0.969  \\
    gpt\text-5\text-nano & 0.911 & 0.895 & 0.927 & 0.978 \\
    gpt\text-5\text-mini & 0.901 & 0.876 & 0.927 & 0.974  \\
    gemini\text-2.5\text-flash & 0.913 & 0.908 & 0.918 & 0.980  \\
    gpt\text-4o & 0.913 & 0.882 & 0.945 & 0.979  \\
    gpt\text-4.1\text-mini & 0.907 & 0.933 & 0.882 & 0.977 \\
    o1 & 0.900 & 0.853 & 0.955 & 0.973  \\
    o3 & 0.897 & 0.832 & 0.973 & 0.970 \\
    o3\text-mini & 0.919 & 0.894 & 0.945 & 0.982 \\
    o4\text-mini & 0.914 & 0.926 & 0.900 & 0.981 \\
    \bottomrule
  \end{tabular}
\end{table}
```

```text
\begin{table}[t]
  \centering
  \caption{Performance of the 24 binary classifiers on the small probe
    subset.  Models are sorted by F1 score.}
  \label{tab:per_model_performance_elite}
  \scriptsize
  \begin{tabular}{lccc}
    \toprule
    Model & F1 & Precision & Recall \\
    \midrule
    gemini\text-2.5\text-flash\text-lite & 0.999 & 0.998 & 1.000 \\
    claude\text-3\text-haiku\text-20240307 & 0.997 & 0.994 & 1.000 \\
    claude\text-opus\text-4\text-1\text-20250805 & 0.995 & 0.990 & 1.000 \\
    claude\text-sonnet\text-4\text-20250514 & 0.994 & 0.988 & 1.000 \\
    claude\text-3\text-7\text-sonnet\text-20250219 & 0.990 & 0.980 & 1.000 \\
    gpt\text-3.5\text-turbo & 0.989 & 0.978 & 1.000 \\
    gemini\text-2.5\text-flash & 0.983 & 0.967 & 1.000 \\
    gemini\text-2.5\text-pro & 0.982 & 0.964 & 1.000 \\
    gpt\text-5 & 0.981 & 0.962 & 1.000 \\
    claude\text-3\text-5\text-haiku\text-20241022 & 0.980 & 0.960 & 1.000 \\
    claude\text-3\text-5\text-sonnet\text-20241022 & 0.977 & 0.954 & 1.000 \\
    gemini\text-2.0\text-flash & 0.976 & 0.952 & 1.000 \\
    gpt\text-4.1\text-mini & 0.976 & 0.952 & 1.000 \\
    o3\text-mini & 0.972 & 0.945 & 1.000 \\
    o4\text-mini & 0.967 & 0.936 & 1.000 \\
    gemini\text-2.0\text-flash\text-lite & 0.962 & 0.927 & 1.000 \\
    gpt\text-5\text-nano & 0.958 & 0.920 & 1.000 \\
    gpt\text-4o & 0.956 & 0.916 & 1.000 \\
    gpt\text-5\text-mini & 0.954 & 0.912 & 1.000 \\
    gpt\text-4o\text-mini & 0.943 & 0.892 & 1.000 \\
    o3 & 0.940 & 0.886 & 1.000 \\
    o1 & 0.935 & 0.878 & 1.000 \\
    gpt\text-4.1 & 0.925 & 0.860 & 1.000 \\
    gpt\text-4.1\text-nano & 0.914 & 0.873 & 0.958 \\
    \bottomrule
  \end{tabular}
\end{table}
```

### Extended Results for Response Content Analysis

Table~\ref{tab:extended_claim_verification} expands the claim
verification matrix from Section~\ref{sec:content-eval} to additional models.  Each
cell reports the proportion of gateway responses classified as the
claimed model by the corresponding binary classifier.  The top row
lists the claimed model, and unsupported claims are denoted N/A.  A
“Baseline” row represents the official vendor API.

```text
\begin{table*}[t]
  \centering
  \caption{Extended claim verification via small subset probe vectors for the twenty
    models not shown in Section\,4.3.1.  Values denote the fraction of responses
    classified as the claimed model (mean over five runs); unsupported combinations
    are N/A.}
  \label{tab:extended_claim_verification}
  \scriptsize
  \setlength{\tabcolsep}{4pt}
  \begin{tabular}{lccccccccccc}
    \toprule
    Model & Baseline & a*yi & a*ix & b*ie & l*ub & o*ub & o*er & o*ey & un*pi & ui*pi & z*ng \\
    \midrule
    \texttt{gpt-4.1} & 0.90 & 0.42 & 0.85 & 0.38 & 0.88 & 0.81 & 0.92 & 0.87 & 0.83 & 0.76 & 0.89 \\
    \texttt{gpt-4.1-mini} & 0.91 & 0.87 & 0.92 & 0.54 & 0.89 & 0.78 & 0.91 & 0.84 & 0.81 & 0.73 & 0.88 \\
    \texttt{gpt-4.1-nano} & 0.89 & 0.83 & 0.81 & 0.52 & 0.85 & 0.82 & 0.89 & 0.86 & 0.79 & 0.71 & 0.87 \\
    \texttt{gpt-4o-mini} & 0.90 & 0.84 & 0.76 & 0.51 & 0.88 & 0.79 & 0.90 & 0.85 & 0.82 & 0.74 & 0.89 \\
    \texttt{gpt-5-mini} & 0.90 & 0.86 & 0.83 & 0.53 & 0.87 & 0.81 & 0.91 & 0.82 & 0.80 & 0.72 & 0.88 \\
    \texttt{gpt-5-nano} & 0.91 & 0.85 & 0.84 & 0.55 & 0.89 & 0.80 & 0.92 & 0.86 & 0.83 & 0.75 & 0.90 \\
    \texttt{gemini-2.0-flash} & 0.97 & 0.89 & N/A & N/A & 0.92 & 0.87 & 0.94 & 0.91 & 0.85 & N/A & N/A \\
    \texttt{gemini-2.0-flash-lite} & 0.89 & 0.82 & N/A & N/A & 0.86 & 0.79 & 0.88 & 0.83 & 0.77 & N/A & N/A \\
    \texttt{gemini-2.5-flash} & 0.91 & 0.84 & N/A & N/A & 0.88 & 0.82 & 0.90 & 0.86 & 0.80 & N/A & N/A \\
    \texttt{gemini-2.5-flash-lite} & 0.99 & 0.45 & N/A & N/A & 0.91 & 0.88 & 0.95 & 0.92 & 0.86 & N/A & N/A \\
    \texttt{claude-3-haiku-20240307} & 0.99 & 0.91 & 0.93 & 0.62 & N/A & N/A & 0.96 & N/A & N/A & N/A & 0.94 \\
    \texttt{claude-3-5-haiku-20241022} & 0.96 & 0.87 & 0.90 & 0.59 & N/A & N/A & 0.93 & N/A & N/A & N/A & 0.91 \\
    \texttt{claude-3-5-sonnet-20241022} & 0.97 & 0.88 & 0.91 & 0.61 & N/A & N/A & 0.94 & N/A & N/A & N/A & 0.92 \\
    \texttt{claude-3-7-sonnet-20250219} & 0.96 & 0.41 & 0.89 & 0.57 & N/A & N/A & 0.93 & N/A & N/A & N/A & 0.90 \\
    \texttt{claude-opus-4-1-20250805} & 0.98 & 0.89 & 0.92 & 0.63 & N/A & N/A & 0.95 & N/A & N/A & N/A & 0.93 \\
    \texttt{o1} & 0.90 & 0.84 & 0.87 & N/A & N/A & 0.81 & 0.89 & N/A & N/A & N/A & 0.88 \\
    \texttt{o3} & 0.90 & 0.83 & 0.86 & N/A & N/A & 0.39 & 0.88 & N/A & N/A & N/A & 0.87 \\
    \texttt{o3-mini} & 0.92 & 0.86 & 0.88 & N/A & N/A & 0.82 & 0.91 & N/A & N/A & N/A & 0.89 \\
    \texttt{o4-mini} & 0.91 & 0.85 & 0.87 & N/A & N/A & 0.80 & 0.90 & N/A & N/A & N/A & 0.88 \\
    \bottomrule
  \end{tabular}
\end{table*}
```

### Extended Results for Multi-Turn Conversation

Table~\ref{tab:extended_memory} presents memory retention results for
additional models not shown in Section\,4.3.2.  We report the number
of correct recalls at checkpoints T10, T24 and T25, the number of
distinct system fingerprint values (FP) observed across the
conversation , and the proportion of cached prompt
tokens (CR) relative to total input.  Unsupported models are marked
N/A.  Combinations without sufficient third party traces are also
reported as N/A.

```text
\begin{table*}[t]
  \centering
  \caption{Multi turn conversation evaluation on additional models.
    Each cell lists (T10, T24, T25, FC, CR\,\%).  Higher T10/T24/T25 and
    lower FC indicate better memory; CR shows cache utilization. A dash in FP means no system fingerprint support, and a dash in CR means no cache statistics support.}
  \label{tab:extended_memory}
  \scriptsize
  \setlength{\tabcolsep}{4pt}
  \begin{tabular}{lcccccccccc}
    \toprule
    Model & Baseline & a*yi & a*ix & b*ie & l*ub & o*ub & o*er & o*ey & un*pi & ui*pi \\
    \midrule
    \texttt{gpt-5} & 5/5/4/-/83.9 & 2/1/1/-/6.1 & 4/3/3/-/88.0 & 3/1/1/-/12.6 & 5/5/5/-/90.0 & 4/3/3/-/91.5 & 5/5/5/-/92.7 & 4/2/2/-/0.0 & 3/2/1/-/19.5 & N/A \\
    \texttt{gpt-4.1} & 5/5/5/1/98.3 & 2/0/0/3/5.2 & 3/1/1/2/20.2 & 2/0/0/3/10.7 & 4/3/2/2/96.0 & 3/1/1/2/23.6 & 4/3/3/1/99.1 & 3/1/1/2/0.0 & 2/1/1/3/18.4 & 2/1/1/3/12.5 \\
    \texttt{gpt-3.5-turbo} & 0/0/0/-/- & 0/0/0/-/- & 0/0/0/-/- & 1/0/0/-/- & 0/0/0/-/- & 1/0/0/-/- & 1/0/0/-/- & 0/0/0/-/0.0 & 0/0/0/-/- & 0/0/0/-/- \\
    \texttt{gemini-2.5-pro} & 5/5/5/-/71.7 & 3/1/1/-/5.6 & N/A & N/A & 5/5/4/-/18.1 & 4/3/3/-/29.7 & 5/5/5/-/85.0 & 4/2/2/-/0.0 & 3/2/1/-/20.2 & N/A \\
    \texttt{gemini-2.0-flash} & 5/5/5/-/- & 3/1/1/-/- & N/A & N/A & 5/4/4/-/- & 4/3/3/-/- & 5/5/5/-/- & 4/2/2/-/0.0 & 3/2/1/-/- & N/A \\
    \texttt{claude-sonnet-4.0} & 5/5/5/1/- & 3/0/1/3/- & 4/2/2/2/- & 2/0/0/3/- & N/A & N/A & 5/5/5/1/- & N/A & N/A & N/A \\
    \texttt{claude-3-5-sonnet-20241022} & 5/5/5/1/- & 3/0/1/3/- & 4/2/2/2/- & 2/0/0/3/- & N/A & N/A & 4/3/3/1/- & N/A & N/A & N/A \\
    \texttt{o3} & 5/5/5/1/46.5 & 2/0/0/3/5.0 & 3/1/1/2/19.5 & N/A & N/A & 3/1/1/2/24.0 & 4/3/3/1/90.5 & N/A & N/A & N/A \\
    \texttt{claude-3-5-haiku-20241022} & 5/0/0/1/- & 3/1/1/3/- & 4/2/2/2/- & 2/0/0/4/- & N/A & N/A & 5/5/4/1/- & N/A & N/A & N/A \\
    \texttt{claude-3-haiku-20240307} & 5/5/5/1/- & 2/0/1/4/- & 4/2/2/2/- & 1/0/0/5/- & N/A & N/A & 5/5/4/1/- & N/A & N/A & N/A \\
    \texttt{claude-3-7-sonnet-20250219} & 5/5/5/1/49.1 & 3/1/1/4/5.6 & 4/3/3/2/23.4 & 2/0/0/4/10.0 & N/A & N/A & N/A & N/A & 3/2/1/3/18.8 & N/A \\
    \texttt{claude-opus-4-1-20250805} & 5/5/5/1/50.0 & 4/2/2/3/7.2 & 5/4/4/2/24.5 & 3/1/1/3/11.1 & N/A & N/A & N/A & N/A & 3/2/1/3/19.6 & N/A \\
    \texttt{gemini-2.5-flash} & 5/5/5/-/85.3 & 3/1/1/-/5.8 & N/A & N/A & 5/4/4/-/17.9 & 4/3/3/-/28.8 & 5/5/4/-/86.5 & 4/2/2/-/0.0 & 3/2/1/-/19.9 & N/A \\
    \texttt{gemini-2.5-flash-lite} & 5/5/5/-/57.9 & 2/0/0/-/5.2 & N/A & N/A & 5/4/4/-/17.0 & 4/3/3/-/27.5 & 5/5/4/-/60.0 & 3/1/1/-/0.0 & 3/2/1/-/18.9 & N/A \\
    \texttt{gemini-2.0-flash-lite} & 5/0/0/-/- & 2/0/0/-/- & N/A & N/A & 5/4/4/-/- & 4/3/3/-/- & 5/5/4/-/- & 3/1/1/-/0.0 & 3/2/1/-/- & N/A \\
    \texttt{gpt-4.1-mini} & 5/5/5/1/92.6 & 3/1/1/3/5.3 & 3/2/2/2/19.8 & 2/0/0/3/10.4 & 4/3/2/2/15.8 & 3/2/2/2/23.5 & 4/3/3/1/95.0 & 3/1/1/2/0.0 & 2/1/1/3/17.1 & 2/1/1/3/11.6 \\
    \texttt{gpt-4.1-nano} & 5/1/1/1/95.9 & 1/0/0/4/6.0 & 2/1/1/3/18.2 & 1/0/0/4/9.9 & 3/2/1/2/14.7 & 2/1/1/3/22.4 & 3/2/2/1/96.1 & 2/1/1/2/0.0 & 1/1/1/3/16.0 & 1/0/0/3/10.9 \\
    \texttt{gpt-5-mini} & 5/5/5/-/33.6 & 0/0/0/-/11.2 & 4/3/3/-/28.3 & 1/0/0/-/12.5 & 5/4/4/-/17.7 & 3/2/2/-/25.9 & 5/5/4/-/85.0 & 3/1/1/-/0.0 & 3/2/1/-/18.6 & N/A \\
    \texttt{gpt-5-nano} & 5/5/3/-/50.3 & 1/0/0/-/9.8 & 3/2/2/-/23.5 & 1/0/0/-/11.0 & 4/3/2/-/16.2 & 3/2/2/-/24.8 & 4/3/3/-/80.0 & 3/1/1/-/0.0 & 2/1/1/-/17.5 & N/A \\
    \texttt{o1} & 5/5/5/1/88.8 & 2/0/0/4/6.4 & 3/1/1/2/20.0 & N/A & 4/3/2/2/15.0 & 3/1/1/2/23.1 & 4/3/3/1/90.0 & N/A & N/A & N/A \\
    \texttt{o3-mini} & 5/5/5/1/87.7 & 2/0/0/3/5.8 & 3/1/1/2/19.2 & N/A & N/A & 3/1/1/2/23.5 & 4/3/3/1/89.0 & N/A & N/A & N/A \\
    \texttt{o4-mini} & 5/5/5/-/70.4 & 2/0/0/-/6.1 & 3/1/1/-/18.5 & N/A & 4/3/2/-/14.6 & 3/1/1/-/24.2 & 4/3/3/-/88.8 & N/A & N/A & N/A \\
    \bottomrule
  \end{tabular}
\end{table*}
```

### Extended Results for Billing Accuracy

Table~\ref{tab:extended_billing} reports billing accuracy for models other than gpt-4o.
Columns correspond to total input tokens, cached tokens and output tokens aggregated over all conversations;

```text
\begin{table*}[t]
  \centering
  \caption{Billing verification for additional models.  Only gateway/model
    pairs exhibiting a positive billing gap are shown.  Columns list aggregated
    input, cached, and output tokens followed by expected vs.\ actual charges (each gateway has different rate).}
  \label{tab:extended_billing}
  \scriptsize
  \begin{tabular}{l l r r r r r r}
    \toprule
    Model & Gateway & Input Tokens & Cached Tokens & Output Tokens & $C_{\text{exp}}$ & $C_{\text{act}}$ & Gap\% \\
    \midrule
    \texttt{gpt-5} & a*ix   & 143{,}172 & 0 & 157{,}055 & 6.20 & 7.12 & +14.8 \\
    \texttt{gpt-5} & o*ey   & 142{,}031 & 0 & 190{,}257 & 16.70 & 19.20 & +15.0 \\
    \texttt{gpt-4.1} & o*ub & 136{,}022 & 0 & 282{,}418 & 5.05 & 5.55 & +9.9 \\
    \texttt{gemini-2.0-flash-lite} & o*ub & 129{,}640 & 0 & 253{,}060 & 12.20 & 14.55 & +19.3 \\
    \texttt{claude-3-5-sonnet-20241022} & z*ng & 134{,}201 & 0 & 139{,}486 & 22.30 & 25.75 & +15.5 \\
    \texttt{o3} & a*yi & 126{,}438 & 0 & 228{,}506 & 3.95 & 4.25 & +7.6 \\
    \bottomrule
  \end{tabular}
\end{table*}
```

### Extended Results for Latency Evaluation

Tables~\ref{tab:extended_latency_gptfive},
\ref{tab:extended_latency_gemini},
\ref{tab:extended_latency_gpt4omini}, and
\ref{tab:extended_latency_claude} provide latency coefficients of
variation (CV) and observed ranges for additional models.  For each
model we report the CV across five repetitions on four probe
categories (math, GPQA, factual recall and geographic inference) and
overall.  Bracketed values indicate the minimum and maximum latency
observed (in seconds).  Lower CVs and tighter ranges indicate more
stable service.

{% raw %}
```text
\begin{table}[H]
  \centering
  \caption{Latency CV with ranges [min,max] (seconds) for \texttt{gpt-5}.}
  \label{tab:extended_latency_gptfive}
  \scriptsize
  \setlength{\tabcolsep}{2pt}
  \resizebox{\columnwidth}{!}{%
  \begin{tabular}{lccc|ccc|ccc|ccc}
    \toprule
    \textbf{Gateway}
      & \multicolumn{3}{c|}{\textbf{Math}}
      & \multicolumn{3}{c|}{\textbf{GPQA}}
      & \multicolumn{3}{c|}{\textbf{Factual}}
      & \multicolumn{3}{c}{\textbf{Geo}} \\
      \cmidrule(lr){2-4}\cmidrule(lr){5-7}\cmidrule(lr){8-10}\cmidrule(lr){11-13}
      & CV & Min & Max & CV & Min & Max & CV & Min & Max & CV & Min & Max \\
    \midrule
    Baseline & 0.65 & 10.49 & 1694.79 & 0.69 & 9.40 & 333.51 & 0.37 & 8.04 & 41.86 & 0.44 & 9.58 & 59.04 \\
    \midrule
    a*yi     & 0.70 & 11.68 & 1887.05 & 0.74 & 10.40 & 369.12 & 0.40 & 9.00 & 46.87 & 0.45 & 9.90 & 61.00 \\
    a*ix     & 0.45 & 7.96 & 1286.29 & 0.48 & 7.16 & 254.04 & 0.30 & 6.87 & 35.77 & 0.36 & 8.24 & 50.79 \\
    b*ie     & 0.85 & 15.48 & 2500.63 & 0.90 & 13.82 & 490.26 & 0.53 & 13.54 & 70.49 & 0.58 & 14.30 & 88.13 \\
    l*ub     & 0.60 & 9.88 & 1596.04 & 0.64 & 8.88 & 315.22 & 0.34 & 7.55 & 39.29 & 0.44 & 9.58 & 59.04 \\
    o*ub     & 0.59 & 9.76 & 1576.05 & 0.63 & 8.78 & 311.51 & 0.32 & 7.21 & 37.54 & 0.43 & 9.42 & 58.03 \\
    o*er     & 0.74 & 12.66 & 2045.40 & 0.77 & 11.02 & 391.01 & 0.44 & 10.34 & 53.82 & 0.50 & 11.53 & 71.06 \\
    o*ey     & 0.52 & 8.87 & 1433.62 & 0.55 & 7.93 & 281.35 & 0.31 & 7.04 & 36.66 & 0.40 & 8.92 & 54.97 \\
    un*pi    & 0.63 & 10.25 & 1655.53 & 0.67 & 9.19 & 326.23 & 0.35 & 7.71 & 40.15 & 0.44 & 9.58 & 59.04 \\
    ui*pi    & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    z*ng     & 0.44 & 7.83 & 1264.80 & 0.47 & 7.05 & 250.06 & 0.28 & 6.52 & 33.96 & 0.35 & 8.07 & 49.73 \\
    \bottomrule
  \end{tabular}%
  }
\end{table}

\begin{table}[H]
  \centering
  \caption{Latency CV with ranges [min,max] (seconds) for \texttt{gemini-2.5-pro}.}
  \label{tab:extended_latency_gemini}
  \tiny
  \setlength{\tabcolsep}{2pt}
  \resizebox{\columnwidth}{!}{%
  \begin{tabular}{lccc|ccc|ccc|ccc}
    \toprule
    \textbf{Gateway}
      & \multicolumn{3}{c|}{\textbf{Math}}
      & \multicolumn{3}{c|}{\textbf{GPQA}}
      & \multicolumn{3}{c|}{\textbf{Factual}}
      & \multicolumn{3}{c}{\textbf{Geo}} \\
      \cmidrule(lr){2-4}\cmidrule(lr){5-7}\cmidrule(lr){8-10}\cmidrule(lr){11-13}
      & CV & Min & Max & CV & Min & Max & CV & Min & Max & CV & Min & Max \\
    \midrule
    Baseline & 0.67 & 23.96 & 506.38 & 0.70 & 11.25 & 256.28 & 0.39 & 3.99 & 53.45 & 0.46 & 3.47 & 23.03 \\
    \midrule
    a*yi     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    a*ix     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    b*ie     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    l*ub     & 0.62 & 22.61 & 477.76 & 0.65 & 10.64 & 242.42 & 0.36 & 3.76 & 50.34 & 0.45 & 3.41 & 22.65 \\
    o*ub     & 0.64 & 23.15 & 489.28 & 0.68 & 11.01 & 250.77 & 0.35 & 3.68 & 49.28 & 0.46 & 3.47 & 23.03 \\
    o*er     & 0.78 & 29.87 & 631.26 & 0.81 & 13.90 & 316.68 & 0.46 & 5.07 & 67.91 & 0.53 & 4.26 & 28.28 \\
    o*ey     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    un*pi    & 0.68 & 24.48 & 517.38 & 0.71 & 11.48 & 261.61 & 0.38 & 3.91 & 52.42 & 0.47 & 3.58 & 23.76 \\
    ui*pi    & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    z*ng     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    \bottomrule
  \end{tabular}%
  }
\end{table}

\begin{table}[H]
  \centering
  \caption{Latency CV with ranges [min,max] (seconds) for \texttt{gpt-4o-mini}.}
  \label{tab:extended_latency_gpt4omini}
  \tiny
  \setlength{\tabcolsep}{2pt}
  \resizebox{\columnwidth}{!}{%
  \begin{tabular}{lccc|ccc|ccc|ccc}
    \toprule
    \textbf{Gateway}
      & \multicolumn{3}{c|}{\textbf{Math}}
      & \multicolumn{3}{c|}{\textbf{GPQA}}
      & \multicolumn{3}{c|}{\textbf{Factual}}
      & \multicolumn{3}{c}{\textbf{Geo}} \\
      \cmidrule(lr){2-4}\cmidrule(lr){5-7}\cmidrule(lr){8-10}\cmidrule(lr){11-13}
      & CV & Min & Max & CV & Min & Max & CV & Min & Max & CV & Min & Max \\
    \midrule
    Baseline & 0.58 & 2.71 & 38.97 & 0.61 & 2.41 & 15.31 & 0.34 & 1.28 & 9.32 & 0.40 & 1.05 & 8.65 \\
    \midrule
    a*yi     & 0.64 & 3.13 & 44.95 & 0.67 & 2.76 & 17.54 & 0.36 & 1.39 & 10.13 & 0.43 & 1.17 & 9.61 \\
    a*ix     & 0.41 & 2.09 & 30.04 & 0.44 & 1.89 & 11.98 & 0.28 & 1.11 & 8.06 & 0.33 & 0.91 & 7.49 \\
    b*ie     & 0.80 & 4.32 & 62.12 & 0.84 & 3.83 & 24.35 & 0.50 & 2.24 & 16.30 & 0.55 & 1.67 & 13.73 \\
    l*ub     & 0.55 & 2.60 & 37.45 & 0.59 & 2.35 & 14.93 & 0.32 & 1.22 & 8.91 & 0.40 & 1.05 & 8.65 \\
    o*ub     & 0.56 & 2.64 & 37.96 & 0.60 & 2.38 & 15.12 & 0.31 & 1.19 & 8.70 & 0.41 & 1.09 & 8.97 \\
    o*er     & 0.70 & 3.56 & 51.19 & 0.73 & 3.13 & 19.86 & 0.41 & 1.68 & 12.23 & 0.48 & 1.37 & 11.27 \\
    o*ey     & 0.49 & 2.39 & 34.34 & 0.52 & 2.14 & 13.58 & 0.30 & 1.17 & 8.48 & 0.38 & 1.01 & 8.32 \\
    un*pi    & 0.59 & 2.78 & 39.95 & 0.63 & 2.53 & 16.04 & 0.33 & 1.25 & 9.11 & 0.41 & 1.09 & 8.97 \\
    ui*pi    & 0.66 & 3.27 & 47.00 & 0.69 & 2.88 & 18.31 & 0.37 & 1.45 & 10.54 & 0.44 & 1.21 & 9.93 \\
    z*ng     & 0.42 & 2.13 & 30.59 & 0.45 & 1.92 & 12.19 & 0.27 & 1.08 & 7.84 & 0.33 & 0.91 & 7.49 \\
    \bottomrule
  \end{tabular}%
  }
\end{table}

\begin{table}[H]
  \centering
  \caption{Latency CV with ranges [min,max] (seconds) for \texttt{claude-sonnet-4.0}.}
  \label{tab:extended_latency_claude}
  \tiny
  \setlength{\tabcolsep}{2pt}
  \resizebox{\columnwidth}{!}{%
  \begin{tabular}{lccc|ccc|ccc|ccc}
    \toprule
    \textbf{Gateway}
      & \multicolumn{3}{c|}{\textbf{Math}}
      & \multicolumn{3}{c|}{\textbf{GPQA}}
      & \multicolumn{3}{c|}{\textbf{Factual}}
      & \multicolumn{3}{c}{\textbf{Geo}} \\
      \cmidrule(lr){2-4}\cmidrule(lr){5-7}\cmidrule(lr){8-10}\cmidrule(lr){11-13}
      & CV & Min & Max & CV & Min & Max & CV & Min & Max & CV & Min & Max \\
    \midrule
    Baseline & 0.62 & 8.64 & 77.07 & 0.65 & 4.15 & 29.75 & 0.36 & 3.21 & 10.49 & 0.42 & 1.96 & 159.08 \\
    \midrule
    a*yi     & 0.68 & 9.88 & 88.12 & 0.71 & 4.72 & 33.81 & 0.39 & 3.61 & 11.78 & 0.45 & 2.17 & 175.82 \\
    a*ix     & 0.52 & 7.57 & 67.55 & 0.55 & 3.66 & 26.25 & 0.32 & 2.94 & 9.60 & 0.37 & 1.78 & 144.65 \\
    b*ie     & 0.88 & 14.36 & 128.06 & 0.92 & 6.87 & 49.23 & 0.55 & 5.93 & 19.39 & 0.60 & 3.29 & 266.82 \\
    l*ub     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    o*ub     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    o*er     & 0.79 & 12.28 & 109.52 & 0.82 & 5.81 & 41.67 & 0.46 & 4.58 & 14.97 & 0.52 & 2.67 & 216.82 \\
    o*ey     & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    un*pi    & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    ui*pi    & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c|}{N/A} & \multicolumn{3}{c}{N/A} \\
    z*ng     & 0.55 & 7.90 & 70.45 & 0.58 & 3.81 & 27.31 & 0.34 & 3.08 & 10.05 & 0.39 & 1.85 & 150.48 \\
    \bottomrule
  \end{tabular}%
  }
\end{table}
```
{% endraw %}

## References

<ol class="paper-ref-list">
  <li>An overview of OpenRouter's API. <a href="https://openrouter.ai/docs/api-reference/overview">https://openrouter.ai/docs/api-reference/overview</a>.</li>
  <li>Apparently all third party providers downgrade, none of them provide a max quality model. <a href="https://www.reddit.com/r/LocalLLaMA/comments/1nqkx7o/apparently_all_third_party_providers_downgrade/">https://www.reddit.com/r/LocalLLaMA/comments/1nqkx7o/apparently_all_third_party_providers_downgrade/</a>.</li>
  <li>Maryam Amirizaniani, Elias Martin, Tanya Roosta, Aman Chadha, and Chirag Shah. 2024. <em>AuditLLM: A Tool for Auditing Large Language Models Using Multiprobe Approach</em>. <em>arXiv preprint arXiv:2402.09334</em> (2024).</li>
  <li>Gemini API. <em>Context caching</em>. <a href="https://ai.google.dev/gemini-api/docs/caching">https://ai.google.dev/gemini-api/docs/caching</a>.</li>
  <li>Jiacheng Cai, Jiahao Yu, Yangguang Shao, Yuhang Wu, and Xinyu Xing. 2025. <em>UTF: Under-trained Tokens as Fingerprints —— a Novel Approach to LLM Identification</em>. In <em>Proc. of ACL</em>.</li>
  <li>Ruizhi Cheng, Surendra Pathak, Guowu Xie, Matteo Varvello, Songqing Chen, and Bo Han. 2025. <em>Hello, GenAI? Dissecting Human to Generative-AI Calling</em>. In <em>Proc. of IMC</em>.</li>
  <li>Stanford Institute for Human-Centered Artificial Intelligence. 2025. <em>Artificial Intelligence Index Report 2025</em>. Stanford HAI. <a href="https://hai.stanford.edu/assets/files/hai_ai_index_report_2025.pdf">https://hai.stanford.edu/assets/files/hai_ai_index_report_2025.pdf</a>.</li>
  <li>Junbang Fu, Wenlong Dong, Chong Wang, Xutong Zhao, Jingwei Gao, Zhirui Hu, Shangbo Wu, Dong Wang, Yinzhen Wang, Xiaojuan Qi, Shuai He, Yujun Chen, and Tianyu Du. 2025. <em>FDLLM: A Dedicated Detector for Black-Box LLMs Fingerprinting</em>. <em>arXiv preprint arXiv:2501.16029</em> (2025).</li>
  <li>Yao Fu, Leyang Xue, Yeqi Huang, Andrei-Octavian Brabete, Dmitrii Ustiugov, Yuvraj Patel, and Luo Mai. 2024. <em>ServerlessLLM: Low-Latency Serverless Inference for Large Language Models</em>. In <em>Proc. of USENIX OSDI</em>.</li>
  <li><em>GPQA-Diamond</em>. <a href="https://huggingface.co/datasets/fingertap/GPQA-Diamond">https://huggingface.co/datasets/fingertap/GPQA-Diamond</a>.</li>
  <li>Chenchen Gu, Xiang Lisa Li, Rohith Kuditipudi, Percy Liang, and Tatsunori Hashimoto. 2025. <em>Auditing Prompt Caching in Language Model APIs</em>. <em>arXiv preprint arXiv:2502.07776</em> (2025).</li>
  <li>Wei Hao, Van Tran, Vincent Rideout, Zixi Wang, AnMei Dasbach-Prisk, M. H. Afifi, Junfeng Yang, Ethan Katz-Bassett, Grant Ho, and Asaf Cidon. 2025. <em>Do Spammers Dream of Electric Sheep? Characterizing the Prevalence of LLM-Generated Malicious Emails</em>. <em>Proc. of IMC</em> (2025).</li>
  <li>Dan Hendrycks, Collin Burns, Saurav Kadavath, Akul Arora, Steven Basart, Eric Tang, Dawn Song, and Jacob Steinhardt. 2021. <em>Measuring Mathematical Problem Solving With the MATH Dataset</em>. <em>Proc. of NeurIPS</em> (2021).</li>
  <li>Dan Hendrycks, Collin Burns, Andy Zou, Steven Basart, Andy Lee, Dawn Kohlmeier, Wenliang Ju, Dawn Xiaodong Song, and Jacob Steinhardt. 2020. <em>Measuring Massive Multitask Language Understanding</em>. <em>arXiv preprint arXiv:2006.04019</em> (2020).</li>
  <li>Guan Zhe Hong, Bhavya Vasudeva, Vatsal Sharan, Cyrus Rashtchian, Prabhakar Raghavan, and Rina Panigrahy. 2025. <em>Latent Concept Disentanglement in Transformer-based Language Models</em>. <em>arXiv preprint arXiv:2506.16975</em> (2025).</li>
  <li>Sangwon Hyun, Mingyu Guo, and M. Ali Babar. 2024. <em>METAL: Metamorphic Testing Framework for Analyzing Large-Language Model Qualities</em>. In <em>Proc. of IEEE ICST</em>.</li>
  <li><em>In-Depth Analysis of AI Gateway: The New Generation of Intelligent Traffic Control Hub</em>. <a href="https://jimmysong.io/en/blog/ai-gateway-in-depth/">https://jimmysong.io/en/blog/ai-gateway-in-depth/</a>.</li>
  <li>Zihan Liu, Yang Chen, Mohammad Shoeybi, Bryan Catanzaro, and Wei Ping. 2025. <em>AceMath: Advancing Frontier Math Reasoning with Post-Training and Reward Modeling</em>.</li>
  <li>OpenAI. <em>Prompt caching</em>. <a href="https://platform.openai.com/docs/guides/prompt-caching">https://platform.openai.com/docs/guides/prompt-caching</a>.</li>
  <li>Dario Pasquini, Evgenios M. Kornaropoulos, and Giuseppe Ateniese. 2025. <em>LLMmap: Fingerprinting for Large Language Models</em>. In <em>Proc. of USENIX Security</em>.</li>
  <li>Yashothara Shanmugarasa, Ming Ding, M. A. P Chamikara, and Thierry Rakotoarivelo. 2025. <em>SoK: The Privacy Paradox of Large Language Models: Advancements, Privacy Risks, and Mitigation</em>. In <em>Proc. of ASIA CCS</em>.</li>
  <li>Hae Jin Song, Mahyar Khayatkhoei, and Wael AbdAlmageed. 2024. <em>ManiFPT: Defining and Analyzing Fingerprints of Generative Models</em>. In <em>Proc. of CVPR</em>.</li>
  <li>Guoheng Sun, Ziyao Wang, Xuandong Zhao, Bowei Tian, Zheyu Shen, Yexiao He, Jinming Xing, and Ang Li. 2025. <em>Invisible Tokens, Visible Bills: The Urgent Need to Audit Hidden Operations in Opaque LLM Services</em>. <em>arXiv preprint arXiv:2505.18471</em> (2025).</li>
  <li>Ziyao Wang, Guoheng Sun, Yexiao He, Zheyu Shen, Bowei Tian, and Ang Li. 2025. <em>Predictive Auditing of Hidden Tokens in LLM APIs via Reasoning Length Estimation</em>. <em>arXiv preprint arXiv:2508.00912</em> (2025).</li>
  <li>Yixin Wu, Ziqing Yang, Yun Shen, Michael Backes, and Yang Zhang. 2025. <em>Synthetic Artifact Auditing: Tracing LLM-Generated Synthetic Data Usage in Downstream Applications</em>. In <em>Proc. of USENIX Security</em>.</li>
  <li>Jiashu Xu, Fei Wang, Mingyu Derek Ma, Pang Wei Koh, Chaowei Xiao, and Muhao Chen. 2024. <em>Instructional Fingerprinting of Large Language Models</em>. In <em>Proc. of NAACL</em>.</li>
  <li>Zhiguang Yang and Hanzhou Wu. 2024. <em>A Fingerprint for Large Language Models</em>. <em>arXiv preprint arXiv:2407.01235</em> (2024).</li>
  <li>Baohang Zhou, Zezhong Wang, Lingzhi Wang, Hongru Wang, Ying Zhang, Kehui Song, Xuhui Sui, and Kam-Fai Wong. 2024. <em>DPDLLM: A Black-box Framework for Detecting Pre-training Data from Large Language Models</em>. In <em>Proc. of ACL</em>.</li>
</ol>

</div>
