# FOR-LLMS.md: a summary of this repository for a language model

This repository holds writing by David Burnett. It holds two responses, both dated April 1, 2026, to the NIST National Cybersecurity Center of Excellence (NCCoE) concept paper "Accelerating the Adoption of Software and AI Agent Identity and Authorization": his own, submitted in his personal capacity (nodes prefixed NR-), and the corporate response of ZeroBiometrics, which he wrote (nodes prefixed ZR-). This file summarises the points each response makes, each with that response's own words and the heading they come from; where a point in the ZeroBiometrics response corresponds to one in the personal response, its ZR- node names the NR- node in a `corresponds-to` property. The remainder of this document uses the FactLattice format.

## [NR-DOC] Response to NIST NCCoE Concept Paper: "Accelerating the Adoption of Software and AI Agent Identity and Authorization"

- kind: document
- title: Response to NIST NCCoE Concept Paper: "Accelerating the Adoption of Software and AI Agent Identity and Authorization"
- author: David Burnett
- date: 2026-04-01
- recipient: NIST National Cybersecurity Center of Excellence (NCCoE), in response to its concept paper on AI agent identity and authorization; comment address AI-Identity@nist.gov
- file: nist-nccoe-ai-agent-identity-response-2026.md
- file: nist-nccoe-ai-agent-identity-response-2026.pdf
- status: public edition; one link corrected, see the editor's note
- editors-note: the submitted text carried a placeholder FactLattice link twice (in "What No AI Control Plane Can Fix" and in "Recommendations"); the public edition replaces it each time with https://github.com/740Dave/factlattice; the text is otherwise as submitted
- capacity: personal submission as a practitioner; the author is Head of Product at ZeroBiometrics, which submitted a separate corporate response on the identity and authorization control plane
- capacity-quote: This submission is in my personal capacity as a practitioner.
- factlattice-role: referenced as one illustration among several possible solutions, not as the required one
- factlattice-quote: FactLattice, the knowledge representation model referenced herein, is an independent open-source project that illustrates one of several possible solutions to the input quality problem this submission describes.
- does-not-propose: an identity or authorization system
- thesis: agents need precise, auditable organizational knowledge as well as a control plane; the control plane bounds what an agent may do but does not make its output correct
- section: front matter; Editor's note (public edition)

## [NR-SCOPE] Scope of the response

- part-of: [NR-DOC]
- kind: scope
- engages: Focus Area 1 (General Questions); Focus Area 5 (Auditing and Non-Repudiation); all three use cases
- evidence-type-by-use-case: operational evidence for workforce efficiency and software development; architectural analysis for security operations; a personal healthcare example for domain breadth
- out-of-scope: Focus Areas 2 (Identification), 3 (Authentication), 4 (Authorization) and 6 (Prompt Injection), as control-plane matters
- quote: Focus Areas 2 (Identification), 3 (Authentication), 4 (Authorization), and 6 (Prompt Injection) concern the identity and authorization control plane, which is outside the scope of this knowledge representation submission.
- section: Scope of This Response

## [NR-CLAIM-MISSING-LAYER] The concept paper omits the knowledge layer between outcomes and control

- part-of: [NR-DOC]
- kind: central-claim
- point: between the desired outcomes and the identity and authorization infrastructure lies a layer the concept paper does not address: how an agent acquires the precise, auditable knowledge it needs; the control plane stops an agent exceeding its authorization but does not ensure it has the knowledge to produce correct, compliant output within it
- quote: Between the desired outcomes and the control infrastructure, there is a layer the concept paper does not address: how does the agent acquire the precise, auditable knowledge it needs to use its authority effectively?
- agrees-with-paper: the paper's structure, security in service of outcomes, is called "the right structure"
- section: What No AI Control Plane Can Fix

## [NR-CLAIM-INPUT-QUALITY] The most significant risk is wrong output inside the authorization

- part-of: [NR-DOC]
- kind: central-claim
- point: the most significant risk in enterprise agent deployment is not agents exceeding their authorization (any responsive control plane would address that) but agents producing incorrect output within it because their knowledge is incomplete, imprecise, or stale
- quote: It is that agents will produce incorrect output within their authorization because the input — the knowledge they operate from — is incomplete, imprecise, or stale.
- section: The Input Quality Problem

## [NR-CLAIM-COMPLEMENTARY] Knowledge and authorization infrastructure are both necessary, neither sufficient

- part-of: [NR-DOC]
- kind: central-claim
- depends-on: [NR-ARG-NOT-ERROR-CORRECTION]
- point: knowledge infrastructure and authorization infrastructure are complementary; the control plane is not an error-correction mechanism for poor domain knowledge
- quote: Knowledge infrastructure and authorization infrastructure are complementary — both necessary, neither sufficient alone.
- section: The Input Quality Problem

## [NR-CLAIM-CATEGORICAL] Structured versus unstructured instructions is a categorical difference

- part-of: [NR-DOC]
- kind: central-claim
- point: an agent working from structured knowledge differs categorically, not incrementally, from one working from unstructured instructions, because the structure lets it spend its capacity on the problem rather than on orientation and gap-filling; observed by the author across all three of the paper's use cases
- quote: The difference between an AI agent working from unstructured instructions and one working from structured knowledge is not incremental — it is categorical.
- section: What No AI Control Plane Can Fix

## [NR-CLAIM-PREVENTION] Structured knowledge prevents error at the input instead of detecting it at the output

- part-of: [NR-DOC]
- kind: central-claim
- point: structured knowledge eliminates ambiguity at the input layer: the agent either has the knowledge, with explicit confidence, or explicitly does not and can say so
- quote: The agent either has the knowledge — from the knowledge graph, with explicit confidence — or it explicitly does not, and can say so. This is prevention, not detection.
- section: The Input Quality Problem

## [NR-CLAIM-PROJECTION] One structured knowledge base can produce any artifact the organization needs

- part-of: [NR-DOC]
- kind: central-claim
- point: given a rich structured knowledge base, an agent can generate any output artifact the organization needs, not only the one the knowledge was written for; the artifacts are projections of one graph, authored and maintained once, each traceable to the knowledge that produced it; the author calls this "frequently underestimated"
- quote: when an AI agent has access to a rich, structured knowledge base, it can generate any output artifact the organization needs — not just the artifact the knowledge was "written for."
- section: What Structured Knowledge Makes Possible

## [NR-CLAIM-FINE-TUNING-LIMITS] For internal enterprise workflows, fine-tuning has four structural limitations

- part-of: [NR-DOC]
- kind: central-claim
- point: fine-tuning is appropriate for customer-facing products at massive scale; for the internal enterprise workflows the paper describes it has four structural limitations: time fragility, opacity, accessibility, and vendor lock-in with version fragility
- scope-limit: the claim is bounded to internal enterprise workflows requiring policy conformance, audit trails, fast iteration and regulatory compliance; fine-tuning is conceded for customer-facing products at massive scale
- quote: But for the use cases this concept paper describes — internal enterprise workflows requiring policy conformance, audit trails, fast iteration, and regulatory compliance — fine-tuning has four structural limitations:
- section: Knowledge As Infrastructure, Not Training Data

## [NR-CLAIM-REQUIREMENTS] Any knowledge representation standard serving this role must have eight properties

- part-of: [NR-DOC]
- kind: central-claim
- point: a knowledge representation standard that complements the control plane must be ambiguity-eliminating, machine-authored and human-auditable, time-invariant, cryptographically attestable, LLM-independent and version-invariant, self-auditing, domain-agnostic, and projectable; these are requirements of the role, not of any implementation
- quote: These are requirements for any knowledge representation standard that serves this role — not specific to any particular implementation.
- section: What a Knowledge Representation Standard Requires

## [NR-CLAIM-INJECTION-MODEL] The problem must be solved; the injection model is secondary

- part-of: [NR-DOC]
- kind: central-claim
- point: FactLattice is one implementation of properties any suitable system would have; what matters is that agents operate from precise, complete and current knowledge, not which runtime knowledge-injection model achieves it
- quote: ensuring agents operate from precise, complete, and current knowledge is the must-solve problem, not the exact knowledge injection model used.
- section: What No AI Control Plane Can Fix

## [NR-CLAIM-DEMOCRATIZATION] Structured knowledge makes the benefits of AI available at any scale

- part-of: [NR-DOC]
- kind: central-claim
- point: any organization, at any scale, can get AI's velocity and precision benefits by investing in structured knowledge rather than model customization; the author calls this the democratization opportunity
- quote: any organization, at any scale, can achieve the velocity and precision benefits of AI by investing in structured knowledge rather than in model customization.
- section: What No AI Control Plane Can Fix

## [NR-CLAIM-PRECONDITION-FOR-VERIFICATION] Knowledge precision is a precondition for independent verification

- part-of: [NR-DOC]
- kind: central-claim
- depends-on: [NR-ARG-CONTEXT-CLEAN]
- point: context-clean review works only if the specification is precise enough for an agent with no project context to judge compliance; an ambiguous specification makes context-clean review impossible
- quote: The precision of the knowledge graph is not just a governance property — it is a precondition for independent verification.
- section: Personal Software Development: Specification-Driven SDLC

## [NR-CLAIM-INTEGRATION] The demonstration project should combine the control plane with a knowledge layer

- part-of: [NR-DOC]
- kind: central-claim
- point: the demonstration goals are best achieved by combining whatever identity and authorization architecture emerges with a structured knowledge representation layer
- mechanism-1: delegation credentials that reference versioned knowledge artifacts by cryptographic hash create an end-to-end audit chain: who authorized, what was authorized, what was done
- mechanism-2: protocol-layer enforcement of knowledge-derived policy (tool allowlists, data flow constraints, scope boundaries) makes the knowledge layer's projections enforced, not merely documented
- mechanism-3: context isolation between agents with different trust roles, enforceable by the control plane and defined by the knowledge layer, enables independent verification without context contamination
- quote: The demonstration goals this concept paper envisions will be most effectively achieved by combining whatever identity and authorization architecture emerges from the technical submissions with a structured knowledge representation layer
- section: Relationship to the Concept Paper's Standards and Focus Areas

## [NR-ARG-SILENT-GAP-FILLING] Agents fill gaps with inference that looks grounded; the resulting errors are fully authorized and logged, and the control plane did its job

- part-of: [NR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-INPUT-QUALITY]
- supports-claim: NR-CLAIM-INPUT-QUALITY
- point: faced with ambiguous scope, undefined edge cases or unclear decision boundaries, agents fill gaps with statistical inference; the resulting errors are fully authorized, logged and non-repudiable
- quote: they fill those gaps with statistical inference indistinguishable from grounded output. The resulting errors are fully authorized, fully logged, and completely non-repudiable. The control plane did its job. The output is still wrong.
- section: The Input Quality Problem

## [NR-ARG-CAPABLE-MODELS] Better models make the problem harder to detect

- part-of: [NR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-INPUT-QUALITY]
- supports-claim: NR-CLAIM-INPUT-QUALITY
- point: the input quality problem is structural, not a deficiency of a particular model; more capable models make incorrect output more plausible
- quote: the more capable the model, the more plausible the incorrect output looks. Better models make the input quality problem harder to detect, not easier.
- section: The Input Quality Problem

## [NR-ARG-NOT-ERROR-CORRECTION] The control plane does not correct bad knowledge

- part-of: [NR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-COMPLEMENTARY]
- supports-claim: NR-CLAIM-COMPLEMENTARY
- quote: The control plane is not an error-correction mechanism for incomplete, imprecise, or stale domain knowledge.
- section: The Input Quality Problem

## [NR-ARG-SCAFFOLDING] Structure frees the model's capacity for analysis

- part-of: [NR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-CATEGORICAL]
- supports-claim: NR-CLAIM-CATEGORICAL
- point: without scaffolding the agent spends capacity on orientation (what is asked, what is relevant, what is ambiguous); with it, its full capacity goes to analysis; the author says the RFI response, the medical care insights and the software lifecycle all show this mechanism
- quote: Without scaffolding, the agent spends its processing capacity on orientation — figuring out what is being asked, what context is relevant, what is ambiguous. With scaffolding, the AI system's full capacity goes toward analysis.
- section: The Input Quality Problem

## [NR-ARG-NOT-RAG] Structured knowledge representation is not RAG

- part-of: [NR-DOC]
- kind: argument
- point: RAG retrieves fragments of unstructured text with no structural relationships, confidence annotations, cross-references or semantic change tracking
- quote: RAG answers "what document mentions this topic?" Structured knowledge representation answers "what are the precise rules, how do they relate to each other, and how confident are we in each?"
- section: What Structured Knowledge Representation Is Not

## [NR-ARG-NOT-FINE-TUNING] Structured knowledge representation is not fine-tuning

- part-of: [NR-DOC]
- kind: argument
- contrast-with: [NR-ARG-NOT-RAG]
- quote: Fine-tuning encodes knowledge into model weights — opaque, version-specific, vendor-locked. Structured knowledge representation encodes knowledge into inspectable, portable, attestable documents that any model can consume at runtime.
- section: What Structured Knowledge Representation Is Not

## [NR-ARG-FT-TIME-FRAGILITY] Fine-tuning limitation: time fragility

- part-of: [NR-CLAIM-FINE-TUNING-LIMITS]
- kind: argument
- point: a fine-tuned model degrades from the day training completes; retraining is expensive, needs scarce ML talent, and yields another degrading snapshot
- quote: A fine-tuned model is a snapshot of a business that no longer exists.
- section: Knowledge As Infrastructure, Not Training Data

## [NR-ARG-FT-OPACITY] Fine-tuning limitation: opacity

- part-of: [NR-CLAIM-FINE-TUNING-LIMITS]
- kind: argument
- point: weights cannot be inspected, presented to an auditor or diffed; in regulated contexts (SOX Section 404, HIPAA, GDPR Article 22, DFARS/CMMC) auditable documentation of the rules governing automated processes is a compliance requirement
- quote: When an AI agent IS the internal control, the artifact governing its behavior must be producible on demand. Fine-tuned weights cannot satisfy this requirement.
- section: Knowledge As Infrastructure, Not Training Data

## [NR-ARG-FT-ACCESSIBILITY] Fine-tuning limitation: accessibility

- part-of: [NR-CLAIM-FINE-TUNING-LIMITS]
- kind: argument
- relates-to: [NR-CLAIM-DEMOCRATIZATION]
- point: structured knowledge achieves comparable domain-specific performance without ML engineering, a domain expert working conversationally with a current model; an approach needing specialized ML teams will not serve the breadth of enterprises the paper addresses
- quote: Structured knowledge representation achieves comparable domain-specific agent performance without ML engineering: a domain expert works conversationally with a current-generation AI model to produce the structured documents.
- section: Knowledge As Infrastructure, Not Training Data

## [NR-ARG-FT-VENDOR-LOCK] Fine-tuning limitation: vendor lock-in and version fragility

- part-of: [NR-CLAIM-FINE-TUNING-LIMITS]
- kind: argument
- point: fine-tuned weights are specific to vendor and model version, so every model upgrade potentially invalidates the training investment; this is the opposite of the interoperable, standards-based approach the paper envisions
- quote: An organization that invests in fine-tuning GPT-4o cannot transfer those weights to Claude, Gemini, or even to GPT-5. Every model upgrade potentially invalidates the prior training investment.
- section: Knowledge As Infrastructure, Not Training Data

## [NR-ARG-REQ-AMBIGUITY] Requirement: ambiguity elimination

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- quote: If the specification is ambiguous, the agent guesses. If the agent guesses, the output is unreliable regardless of how well the control plane governs it.
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-REQ-MACHINE-AUTHORED] Requirement: machine-authored, human-auditable

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- point: the needed density exceeds what human authorship sustains efficiently, so the standard must be designed for AI authorship from a domain expert's conversational input, with every document fully readable by humans through rendering
- quote: the human reviews, the machine writes.
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-REQ-TIME-INVARIANT] Requirement: time-invariant

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- relates-to: [NR-ARG-FT-TIME-FRAGILITY]
- quote: Update the knowledge, and agent behavior changes in the next session. No retraining, no deployment pipeline. The knowledge IS the current state of the organization.
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-REQ-ATTESTABLE] Requirement: cryptographically attestable

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- relates-to: [NR-CLAIM-INTEGRATION]
- point: knowledge artifacts must be signable, proving who authored what, when, with what reasoning; combined with a control plane's delegation credential this gives a complete chain
- quote: who authorized the agent → what the agent was told → what the agent did.
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-REQ-LLM-INDEPENDENT] Requirement: LLM-independent and version-invariant

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- relates-to: [NR-ARG-FT-VENDOR-LOCK]
- quote: The same knowledge must work identically across any current-generation AI model — Claude, GPT, Gemini, Llama, or models that do not yet exist.
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-REQ-SELF-AUDITING] Requirement: self-auditing

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- point: every claim should carry explicit confidence; automated analysis should evaluate whether the confidence is warranted and scrutinises low-confidence knowledge more deeply
- quote: The knowledge base should actively identify its own weaknesses.
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-REQ-DOMAIN-AGNOSTIC] Requirement: domain-agnostic

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- quote: Engineering specifications, legal policies, HR procedures, financial controls, medical records, security runbooks — all must coexist in a unified structure without vocabulary collisions.
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-REQ-PROJECTABLE] Requirement: projectable

- part-of: [NR-CLAIM-REQUIREMENTS]
- kind: argument
- relates-to: [NR-CLAIM-PROJECTION]
- quote: The same knowledge must be instantiable as any artifact the organization needs
- section: What a Knowledge Representation Standard Requires

## [NR-ARG-SOLUTION-PROPERTIES] Properties of a suitable runtime-injection system, as first stated

- part-of: [NR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-REQUIREMENTS], [NR-CLAIM-INJECTION-MODEL]
- point: first, written for consumption by an LLM (explicit scope boundaries, typed relationships, declared cross-references, confidence annotations on every claim, navigable structure); also human-auditable, cryptographically attestable, time-invariant, and independent of any model, vendor or control plane
- quote: First and foremost, it must be written for consumption by an LLM
- factlattice: royalty-free, open-source, at https://github.com/740Dave/factlattice; "one implementation of a set of properties that any suitable system would have"
- section: What No AI Control Plane Can Fix

## [NR-ARG-LIVING-SUBSTRATE] Structured knowledge differs from documentation, training data and prompt engineering

- part-of: [NR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-PROJECTION]
- supports-claim: NR-CLAIM-PROJECTION
- point: documentation is fixed and manually updated, training data is frozen in weights, prompt engineering lasts one session
- quote: Structured knowledge is a living substrate from which an unbounded variety of artifacts can be instantiated — and every artifact is traceable to the authoritative knowledge that produced it.
- section: What Structured Knowledge Makes Possible

## [NR-ARG-SECOPS] Security operations: where ambiguity is acute

- part-of: [NR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-CATEGORICAL]
- evidence-type: architectural analysis, not operational evidence (per the Scope section)
- point: structured knowledge encodes runbooks, escalation procedures, threat classification rules, playbooks and compliance mappings; with explicit confidence annotations the agent works from verified procedures or flags uncertainty for human escalation
- quote: These are knowledge artifacts where the consequences of ambiguity are acute: an agent that guesses during incident triage is a liability.
- section: What No AI Control Plane Can Fix

## [NR-ARG-CONTEXT-CLEAN] Review agents should be context-clean; builders context-rich

- part-of: [NR-DOC]
- kind: argument
- point: builder agents carry full project context; review agents (spec-gap analyzer, security reviewer, QA tester, linter) start with only the specification and the implementation, the same independence principle as external audit
- quote: A context-clean reviewer cannot be biased by the builder's rationale. It reads the specification cold and asks: "does the implementation match?"
- section: Personal Software Development: Specification-Driven SDLC

## [NR-ARG-STD-MCP] Relation to MCP

- part-of: [NR-CLAIM-INTEGRATION]
- kind: argument
- point: the knowledge layer sits above MCP's protocol layer and can project tool allowlists that map to the delegation credentials an MCP-aware enforcement proxy validates
- quote: MCP defines how agents invoke tools; the knowledge layer defines which tools a specific task requires, what inputs they expect, and what constraints govern their outputs.
- section: Relationship to the Concept Paper's Standards and Focus Areas

## [NR-ARG-STD-OAUTH] Relation to OAuth 2.0

- part-of: [NR-CLAIM-INTEGRATION]
- kind: argument
- quote: A knowledge graph that defines an agent's authorized actions can produce the specific OAuth scopes a sender-constrained token should carry — derived from the task definition rather than statically assigned.
- section: Relationship to the Concept Paper's Standards and Focus Areas

## [NR-ARG-STD-NGAC] Relation to NGAC (INCITS 565-2020)

- part-of: [NR-CLAIM-INTEGRATION]
- kind: argument
- quote: Knowledge-derived attributes can inform NGAC policy evaluation without requiring the policy engine to parse unstructured instructions.
- section: Relationship to the Concept Paper's Standards and Focus Areas

## [NR-ARG-STD-ZERO-TRUST] Relation to SP 800-207 (Zero Trust Architecture)

- part-of: [NR-CLAIM-INTEGRATION]
- kind: argument
- point: per-specification authorization, context isolation between trust roles (micro-segmentation), specification-bounded scope (least privilege), and protocol-layer enforcement
- quote: These are zero trust tenets applied to the knowledge layer.
- section: Relationship to the Concept Paper's Standards and Focus Areas

## [NR-ARG-PROMPT-INJECTION] Relation to prompt injection, from the knowledge-layer perspective

- part-of: [NR-CLAIM-INTEGRATION]
- kind: argument
- relates-to: [NR-ARG-CONTEXT-CLEAN]
- point: with enforcement external to the agent, an injection cannot cause scope exceedance; context-clean reviewers never see a builder's possibly injected context
- quote: a successful injection cannot cause scope exceedance when enforcement is external to the agent.
- section: Relationship to the Concept Paper's Standards and Focus Areas

## [NR-EVID-THIS-SUBMISSION] The submission itself was produced by an agent from structured knowledge

- part-of: [NR-DOC]
- kind: evidence
- relates-to: [NR-CLAIM-CATEGORICAL], [NR-EX-POLICY-WORKFLOW]
- use-case: workforce efficiency (concept paper Section 3.1)
- quote: This submission was produced by an AI agent operating from structured knowledge in approximately 75 minutes of wall-clock collaboration, including iterative review and independent quality scoring by context-clean review agents.
- section: What No AI Control Plane Can Fix

## [NR-EVID-INDEPENDENT-REVIEW] Context-clean review improved the draft by reorganization alone

- part-of: [NR-DOC]
- kind: evidence
- relates-to: [NR-ARG-CONTEXT-CLEAN], [NR-EX-POLICY-WORKFLOW]
- point: one context-clean agent with only the concept paper built a multi-dimensional rubric; two more scored the draft; the feedback found structural weaknesses invisible from inside the drafting process
- quote: Revisions based on this independent review produced significant improvement with no new intellectual content — only reorganization guided by structured feedback.
- section: Evidence from Practice > This Submission: An Agentic Workflow for Policy Document Assessment

## [NR-EVID-SCAFFOLD-SYSTEM-CARD] Published finding cited as consistent: a scaffold more than doubled performance

- part-of: [NR-DOC]
- kind: evidence
- relates-to: [NR-ARG-SCAFFOLDING]
- supports-claim: NR-ARG-SCAFFOLDING
- hedge: presented as "consistent with" the observation and as "suggesting", not as proof
- quote: Anthropic's system card for Claude Opus 4.6 reports that the same model equipped with an experimental scaffold achieved over twice the performance of their standard scaffold
- section: The Input Quality Problem

## [NR-EVID-CARE] Structured knowledge of his father's care surfaced gaps the facility had not addressed

- part-of: [NR-DOC]
- kind: evidence
- relates-to: [NR-CLAIM-DEMOCRATIZATION], [NR-EX-CARE]
- point: one person, no incremental cost, no specialized model, no fine-tuning, no ML engineering; the same current-generation model that drafts policy and writes software produced the insights because the knowledge was structured; shared with his father's express permission
- quote: the AI identified critical care gaps that the facility's clinical team had not addressed and enabled me to be a highly persuasive patient advocate.
- section: What No AI Control Plane Can Fix

## [NR-EVID-SDLC] A complete specification-driven lifecycle run by agents

- part-of: [NR-DOC]
- kind: evidence
- relates-to: [NR-EX-SDLC-TABLE]
- use-case: software development (concept paper Section 3.3); personal projects, independent of his ZeroBiometrics work
- quote: I operate a complete specification-driven development lifecycle where AI agents are the workforce at every stage
- section: What No AI Control Plane Can Fix

## [NR-EVID-SIX-DOMAINS] FactLattice substantiated in six knowledge domains

- part-of: [NR-DOC]
- kind: evidence
- domains: biometric cryptographic protocols; AI governance; software engineering; software-defined I/O; medical records; structured care methodology
- control-plane-binding: not bound to any specific control plane implementation
- quote: has been substantiated in practice across six knowledge domains
- section: Recommendations

## [NR-EX-POLICY-WORKFLOW] Worked example: an agentic workflow for policy document assessment

- part-of: [NR-DOC]
- kind: worked-example
- relates-to: [NR-CLAIM-INTEGRATION]
- step-1: an agent reads the source document (here a government RFI) and structures it as a knowledge artifact: questions, focus areas, evaluation criteria
- step-2: the agent compares the source with existing organizational knowledge to find relevant material and gaps
- step-3: the agent drafts a response organized around the source document's structure
- step-4: a human subject matter expert reviews and directs revisions; each decision is captured with its reasoning, the alternatives, and the assumption that would warrant reopening it
- step-5: independent context-clean review agents, with only the source and the draft, score it against a rubric derived solely from the source
- step-6: the human applies structural changes based on review findings
- step-7: the revised document is re-scored to measure improvement
- step-8: control points: counsel reviews for disclosure risk; an authorized signatory approves release; the document is submitted
- interlock: the knowledge layer defines what the agent does at each stage; a delegation credential from the organization's control plane would gate who can advance the document at each control point
- quote: This is exactly the workflow that produced the submission you are reading.
- section: Evidence from Practice > This Submission: An Agentic Workflow for Policy Document Assessment

## [NR-EX-SECOPS-PROJECTIONS] Worked example: one security-operations knowledge base, seven artifacts

- part-of: [NR-CLAIM-PROJECTION]
- kind: worked-example
- input: incident classification rules, escalation procedures, compliance mappings, threat models, service dependencies, SLA requirements, encoded as structured, cross-referenced documents
- artifact: a runbook for a specific incident type, tailored to the on-call team's tooling
- artifact: a post-incident report for executive leadership
- artifact: a compliance evidence package for an auditor
- artifact: updated training materials
- artifact: a risk assessment for a proposed infrastructure change
- artifact: the delegation policy artifact (tool allowlists, data flow constraints, escalation thresholds) a control plane needs to govern the security agent itself
- artifact: a gap analysis against best practice or regulatory frameworks, with prioritized recommendations
- quote: None of these artifacts require separate knowledge. They are different projections of the same knowledge graph — different views, for different audiences, generated on demand.
- section: What Structured Knowledge Makes Possible

## [NR-EX-OTHER-PROJECTIONS] Worked example: projections in software, medicine and policy

- part-of: [NR-CLAIM-PROJECTION]
- kind: worked-example
- software: code, test suites, deployment configurations, PRDs, executive briefings, all-hands communications
- medical: care plans, insurance appeals, clinical concern letters
- policy: this RFI response, the scoring rubric that evaluated it, the change log of every editorial decision
- quote: All from the same knowledge, all consistent, all auditable.
- section: What Structured Knowledge Makes Possible

## [NR-EX-CARE] Worked example: advocacy for his father in a skilled nursing facility

- part-of: [NR-DOC]
- kind: worked-example
- relates-to: [NR-EVID-CARE]
- setting: his 83-year-old father, post-operative rehabilitation in a skilled nursing facility; the author had no medical training
- encoded: medical history, active problems, medications, care orders, risk factors, conversations with staff, facility communications, as structured, cross-referenced knowledge
- chain: unstructured family observations, then precise structured enumeration, then AI-generated clinical insights, then precise problem articulation back to him in language he could understand and relay, then dramatically more effective communication with clinical staff in their terminology
- limit: the representation did not replace clinical judgment
- ongoing: that episode is resolved; the file continues to grow with each visit, medication change and observation
- quote: The structured knowledge representation did not replace clinical judgment — it provided the scaffolding for an AI system to reason across my father's full clinical picture in a way that siloed chart documentation could not support
- section: Evidence from Practice > Healthcare Advocacy: How Structured Knowledge Made Me a Better Advocate for My Father

### [NR-EX-CARE-BP] Care gap 1: unmonitored blood pressure during physical therapy

- part-of: [NR-EX-CARE]
- kind: worked-example
- facts: a TIA in Q4 2024; idiopathic post-operative blood pressure lability managed with PRN Hydralazine above 150 mmHg systolic; BP checks twice per shift at variable times, independent of the PT schedule; no pre-PT or post-PT clearance
- what-differed: he knew each fact, and direct questions to the AI got sound general guidance; with the whole structured picture the AI identified the gap unprompted
- quote: That insight did not come from asking a better question. It came from giving the AI the complete, structured clinical picture and letting it reason across the full graph.
- section: Evidence from Practice > Healthcare Advocacy: How Structured Knowledge Made Me a Better Advocate for My Father

### [NR-EX-CARE-OPIOID] Care gap 2: opioid regression caused by the facility's own treatment plan

- part-of: [NR-EX-CARE]
- kind: worked-example
- facts: he had weaned off oxycodone; the facility doubled PT intensity; upper-extremity stress required daily opioid resumption, a new skilled nursing need
- what-differed: the family understood the injury as a rotator cuff problem; the AI, reading the actual surgical report in the structured knowledge, found it significantly more severe, which explained the pain
- quote: surfaced this as a facility-created problem, not a patient deterioration.
- section: Evidence from Practice > Healthcare Advocacy: How Structured Knowledge Made Me a Better Advocate for My Father

## [NR-EX-SDLC-TABLE] Worked example: the six-stage specification-driven SDLC

- part-of: [NR-DOC]
- kind: worked-example
- relates-to: [NR-ARG-CONTEXT-CLEAN], [NR-CLAIM-PRECONDITION-FOR-VERIFICATION]
- stage-1: Spec authoring; agent role: structured editor plus automated linting; knowledge dependency: FactLattice format defines valid structure
- stage-2: Build; independent builder agents receive linted specs as complete requirements; the spec is the builder's only input
- stage-3: First bringup; launch the built component, fix every crash, iterate until it runs; the spec defines expected behavior
- stage-4: Quality gate; spec-gap analysis, security review, test coverage; the spec-gap analyzer compares implementation against spec
- stage-5: Deploy; deploy artifacts, verify services respond, update infrastructure docs; a deployment spec defines the target configuration
- stage-6: Maintain; spec densification, corpus health analysis, drift detection; spec-implementation drift detected and reconciled
- quote: I operate a complete specification-driven SDLC where AI agents perform every stage:
- section: Personal Software Development: Specification-Driven SDLC

## [NR-REC-1] Recommendation 1: evaluate knowledge representation standards alongside identity and authorization standards

- part-of: [NR-DOC]
- kind: recommendation
- depends-on: [NR-CLAIM-COMPLEMENTARY]
- point: the demonstration project should assess how structured knowledge interacts with delegation credentials
- quote: Evaluate structured knowledge representation standards alongside identity and authorization standards. The control plane is more effective when it governs agents whose behavior is driven by external, inspectable artifacts.
- section: Recommendations

## [NR-REC-2] Recommendation 2: include the specification-driven agent pattern in use case evaluation

- part-of: [NR-DOC]
- kind: recommendation
- depends-on: [NR-CLAIM-FINE-TUNING-LIMITS]
- quote: All three proposed use cases are internal enterprise workflows where specification-driven agents outperform fine-tuned agents on auditability, iteration speed, accessibility, and LLM portability.
- section: Recommendations

## [NR-REC-3] Recommendation 3: consider scalability across organization sizes

- part-of: [NR-DOC]
- kind: recommendation
- depends-on: [NR-CLAIM-DEMOCRATIZATION]
- point: the paper scopes the project to enterprise, but conversationally produced specifications plus a protocol-layer enforcement point make the governance model accessible without ML teams or enterprise-scale infrastructure
- quote: the fastest path to broad adoption of identity and authorization standards is through approaches that work at any scale.
- section: Recommendations

## [ZR-DOC] Response to NIST NCCoE Concept Paper: "Accelerating the Adoption of Software and AI Agent Identity and Authorization" (ZeroBiometrics)

- kind: document
- title: Response to NIST NCCoE Concept Paper: "Accelerating the Adoption of Software and AI Agent Identity and Authorization"
- author: ZeroBiometrics (written by David Burnett)
- date: 2026-04-01
- recipient: NIST National Cybersecurity Center of Excellence (NCCoE), in response to its concept paper on AI agent identity and authorization (Draft February 2026); comment address AI-Identity@nist.gov
- contact: David Burnett, Head of Product, ZeroBiometrics
- file: nist-nccoe-ai-agent-identity-response-zerobiometrics-2026.md
- file: nist-nccoe-ai-agent-identity-response-zerobiometrics-2026.pdf
- status: public edition; the text is as submitted
- attachment-named: ZeroBiometrics Technical White Paper — ZeroSentinel: A Standards-Aligned Cryptographic Human-Authorization Layer for Agentic AI; the attachment is not part of this repository and is not summarised here
- relates-to: [NR-DOC]
- corresponds-to: NR-DOC (the personal response describes this as the separate corporate response on the identity and authorization control plane)
- engages: question-by-question answers in six sections (general questions, identification, authentication, authorization, auditing and non-repudiation, prompt injection), an alignment table, and comments on the three use cases
- thesis: a biometric key derived at signing time, never stored, gives a cryptographic root of trust for binding a verified human's authorization to an AI agent's actions; the control plane should be cryptographic and external to the agent
- collaboration-offered: participate in design reviews; answer technical questions about the biometric entropy-to-key-derivation technology, including its practical limitations; provide demonstrations of the ZeroSentinel architecture
- collaboration-quote: We are a small company with a specific technical contribution. We do not presume to define the demonstration project's scope or direction.
- section: front matter; Why ZeroBiometrics Is Responding; Collaboration

## [ZR-CLAIM-DISTINCT-FROM-STORED-KEY] ZB states that stored-key PKI or FIDO alone cannot offer these properties

- quote: No respondent building on stored-key PKI or FIDO alone can offer these properties, because the underlying technology — cryptographic key derivation from biometric entropy with both irreversibility and unlinkability — is architecturally distinct from biometric-gated key storage. **2.
- section: General Comments
- relates-to: [ZR-ARG-LAYERED-ASSURANCE]

## [ZR-REC-EVALUATE-ON-MERITS] Evaluate the architecture on its merits, independent of any vendor's implementation

- quote: Whether ZeroSentinel is commercially successful is irrelevant to whether its design — and the standards-aligned patterns it demonstrates — is responsive to this RFI.
- section: General Comments

## [ZR-CLAIM-GLOBAL-SCOPE] The control-plane need affects every person and business, worldwide, not only enterprise IT

- quote: that cryptographically binds humans and AI agents is not an enterprise IT concern — it is an issue that affects every person and every business, not only in the United States but throughout the world
- section: General Comments

## [ZR-CLAIM-ROOT-OF-TRUST] Proof of which verified human authorized an action is a natural root of trust for an AI authorization control plane

- part-of: [ZR-DOC]
- kind: central-claim
- point: if one can cryptographically prove which specific, verified human authorized an action, every delegation credential, scope boundary and revocation in the chain traces back to a biometrically proven human identity
- quote: that is a natural root of trust for bootstrapping an AI authorization control plane. Every delegation credential, every scope boundary, every revocation in the chain traces back to a biometrically-proven human identity with strong cryptographic guarantees.
- section: Why ZeroBiometrics Is Responding

## [ZR-CLAIM-EXTERNAL-CRYPTOGRAPHIC-GOVERNANCE] Governance of an agent that can reason about its governance must be cryptographic and external to it

- part-of: [ZR-DOC]
- kind: central-claim
- point: cryptographic non-repudiation for identities, permissions granted and actions taken is a must-have, not a nice-to-have, and the response calls it the only mechanism capable of producing a tamper-proof, immutable record of who authorized what, with what scope, and what the agent did; "trust the platform" is not a viable alternative
- quote: When the entity being governed is capable of reasoning about its own governance, that governance must be cryptographic and external to the agent, not policy-based and dependent on the agent's cooperation.
- section: Why ZeroBiometrics Is Responding

## [ZR-CLAIM-STANDARDS-EXIST] The standards exist; the gap is applying them to bind human authorization to agent action

- part-of: [ZR-DOC]
- kind: central-claim
- point: the standards listed in the concept paper are necessary but not sufficient, having been designed for human-interactive or machine-to-machine scenarios; the gap specific to agentic AI is delegation with scope
- quote: The standards to build this already exist and are proven to operate at internet-scale. The gap is applying them to the specific problem of binding human authorization to agent action with an unbroken cryptographic chain.
- quote-2: The gap specific to agentic AI is delegation with scope: binding a machine credential to a human's explicit, bounded authorization.
- section: Why ZeroBiometrics Is Responding; Responses to Focus Area Questions > 1. General Questions

## [ZR-CLAIM-STORED-KEY] The stored-key assumption and the FIDO assumption are structural vulnerabilities

- part-of: [ZR-DOC]
- kind: central-claim
- point: conventional PKI, SPIFFE/SPIRE and OAuth all assume signing keys are generated and stored (in HSMs, secure enclaves or key vaults); a compromised key store enables undetectable impersonation of human authorization
- quote: The stored-key assumption — and the FIDO assumption — are structural vulnerabilities.
- quote-2: A compromised key store enables undetectable impersonation of human authorization.
- section: General Comments (observation 1)

## [ZR-CLAIM-FIDO-PRESENCE] FIDO proves device-holder presence, not identity

- part-of: [ZR-DOC]
- kind: central-claim
- relates-to: [ZR-CLAIM-STORED-KEY]
- point: in FIDO the biometric is a local gatekeeper that unlocks a stored private key, not a cryptographic participant; someone who enrolls their biometric on a stolen or compromised device is authenticated as the original user
- concession: FIDO provides strong authenticator assurance and has earned its widespread adoption; the limitation is stated for FIDO as deployed, in the specific context of AI agent delegation
- quote: For the question "which specific human authorized this AI agent?" — FIDO answers "someone who has this device," not "David Burnett."
- section: General Comments (observation 1)

## [ZR-CLAIM-PRIVACY-ABSENT] Privacy is absent from the concept paper's framing

- part-of: [ZR-DOC]
- kind: central-claim
- point: the concept paper is enterprise-centric, with a single agent identity propagating across all systems; as agents act for individuals across organizational boundaries, cross-service identity correlation becomes a privacy liability
- quote: As AI agents increasingly act on behalf of individuals across organizational boundaries — personal assistants accessing healthcare, financial, and workplace services — cross-service identity correlation becomes a privacy liability.
- section: General Comments (observation 2)

## [ZR-CLAIM-DATA-FLOW-ENFORCEMENT] Data flow must be enforced, not just tracked

- part-of: [ZR-DOC]
- kind: central-claim
- point: Focus Area 5 frames data flow as a tracking problem; the critical risk is that agents authorized for several tools combine permissions to exfiltrate data
- quote: an agent with read access to sensitive records and write access to email can combine those capabilities in ways that individual tool permissions do not control.
- section: General Comments (observation 3)

## [ZR-CLAIM-INSPECTABLE-ARTIFACTS] Agent governance is most effective when agent behavior is driven by inspectable artifacts

- part-of: [ZR-DOC]
- kind: central-claim
- relates-to: [NR-REC-1], [NR-ARG-FT-OPACITY], [NR-CLAIM-MISSING-LAYER]
- corresponds-to: NR-REC-1; NR-ARG-FT-OPACITY; NR-CLAIM-MISSING-LAYER
- point: the concept paper addresses what agents are authorized to do but not how they acquire the context to do it effectively; the most auditable agents have operating rules, task definitions and domain constraints in structured, machine-parseable specifications rather than fine-tuned weights
- quote: A delegation credential that references a specific, versioned specification is meaningfully auditable — a regulator or compliance officer can inspect exactly what the agent was told to do.
- quote-2: A delegation credential that references a fine-tuned model is a black box with an access control wrapper.
- regulated-contexts: SOX Section 404, HIPAA, GDPR Article 22; auditable documentation of automated decision-making processes is stated to be a compliance requirement opaque model weights cannot satisfy
- section: General Comments (observation 4)

## [ZR-CLAIM-RISK-TAXONOMY] Risks authorization can address must be distinguished from risks it cannot

- part-of: [ZR-DOC]
- kind: central-claim
- relates-to: [NR-CLAIM-COMPLEMENTARY], [NR-ARG-NOT-ERROR-CORRECTION]
- corresponds-to: NR-CLAIM-COMPLEMENTARY; NR-ARG-NOT-ERROR-CORRECTION
- authorization-addressable: unauthorized scope; unauthorized delegation; unrevocable access; unattributable actions; unauthorized data exfiltration; proprietary data leakage
- not-authorization-addressable: prompt injection (confused intent within authorized scope); model hallucination; alignment failures; complementary concerns that benefit from defense-in-depth at the enforcement layer
- quote: This distinction is important for scoping the demonstration project. Conflating authorization with alignment risks producing a system that does neither well.
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-CLAIM-POLICY-AT-SIGNING-TIME] Policy should be fixed at signing time, not mutable at runtime

- part-of: [ZR-DOC]
- kind: central-claim
- point: if policy is mutable at runtime a compromised policy engine can silently expand an agent's permissions; ZeroSentinel moves policy evaluation to signing time, where the human approves it and it is cryptographically bound into the delegation credential
- quote: The enforcement layer validates the signed artifact, not a runtime policy query. A compromised policy engine cannot expand permissions on existing delegations.
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-CLAIM-AUDIT-BY-ARCHITECTURE] Audit completeness should be an architectural property

- part-of: [ZR-DOC]
- kind: central-claim
- point: if an enforcement proxy mediates every agent-to-service interaction, the audit trail at the proxy is complete by construction; each entry should include the delegation credential fingerprint, request hash, policy evaluation result and outcome
- quote: The key insight is that audit completeness should be an architectural property, not an agent cooperation requirement.
- section: Responses to Focus Area Questions > 5. Auditing and Non-Repudiation

## [ZR-CLAIM-BIOMETRIC-NON-REPUDIATION] A biometric-derived signature gives cryptographic non-repudiation bound to biometric presence

- part-of: [ZR-DOC]
- kind: central-claim
- depends-on: [ZR-EVID-ISO-30136]
- point: because the signing key can only be reconstructed from the human's biometric, a valid signature proves a specific human was biometrically present when the delegation was created
- quote: This is not log-based non-repudiation (which depends on log integrity) — it is cryptographic non-repudiation bound to biometric presence.
- section: Responses to Focus Area Questions > 5. Auditing and Non-Repudiation

## [ZR-CLAIM-HITL-CEREMONY] Human-in-the-loop should be a cryptographic ceremony

- part-of: [ZR-DOC]
- kind: central-claim
- relates-to: [ZR-CLAIM-BIOMETRIC-NON-REPUDIATION]
- quote: Human-in-the-loop should be a cryptographic ceremony, not a policy configuration.
- binding-artifact: the delegation credential, signed by the human's key, issued to the agent's key, carrying machine-enforceable policy
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-CLAIM-SPECIFICATION-BRIDGE] Structured specifications are the bridge between authorization and agent effectiveness

- part-of: [ZR-DOC]
- kind: central-claim
- relates-to: [NR-CLAIM-COMPLEMENTARY], [NR-ARG-FT-ACCESSIBILITY], [NR-CLAIM-DEMOCRATIZATION]
- corresponds-to: NR-CLAIM-COMPLEMENTARY; NR-ARG-FT-ACCESSIBILITY; NR-CLAIM-DEMOCRATIZATION
- point: the delegation credential defines what the agent is permitted to do; the specification defines what it is intended to do and how; together they form a complete governance model; specifications can be produced by domain experts working conversationally with AI assistants, with no custom model training
- quote: The delegation credential defines what the agent is permitted to do; the specification defines what the agent is intended to do and how. Together they form a complete governance model.
- section: Comments on Use Cases

## [ZR-ARG-LAYERED-ASSURANCE] Biometric key derivation enables a layered identity assurance model FIDO cannot express

- part-of: [ZR-CLAIM-STORED-KEY]
- kind: argument
- relates-to: [ZR-CLAIM-FIDO-PRESENCE]
- level-1: biometric key derivation alone proves the same person signed both times (cryptographic continuity without stored keys)
- level-2: plus IDV endorsement, proves the same person signed and that person's identity has been verified by document review (passport, Real ID)
- level-3: plus a platform authenticator, gives cryptographic triangulation: three independent signals corroborating the same human's presence and identity
- compatibility: stated to be compatible with SP 800-63-4 identity assurance levels
- quote: the human's signing key is reconstructed from biometric entropy at signing time and never persisted — the biometric IS the key, not a gatekeeper for one.
- section: General Comments (observation 1)

## [ZR-ARG-COMMON-GAP] Across enterprise deployment patterns, the common gap is a verifiable link to a human's authorization

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [ZR-EX-DEPLOYMENT-PATTERNS]
- quote: In all three patterns, the common gap is the same: no verifiable, scoped, revocable link between the agent's actions and a specific human's authorization.
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-ARG-MCP-ENFORCEMENT-POINT] MCP creates a natural enforcement point

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [NR-ARG-STD-MCP]
- corresponds-to: NR-ARG-STD-MCP
- point: an MCP-aware proxy can validate authorization credentials on every tool invocation without modifying the agent or the tool server; ZeroIntent operates as such a proxy
- quote: This architecture demonstrates that authorization enforcement can be deployed at the protocol layer without requiring ecosystem-wide adoption before the system is useful.
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-ARG-POLICY-IN-CERTIFICATE] Policy-in-certificate rather than policy-in-engine

- part-of: [ZR-CLAIM-POLICY-AT-SIGNING-TIME]
- kind: argument
- quote: This approach — policy-in-certificate rather than policy-in-engine — ensures that authorization scope is cryptographically fixed at signing time and cannot be expanded by a compromised policy engine or a misconfigured runtime.
- mechanism: X.509 certificate extensions (OIDs) embed machine-enforceable policy directly in delegation credentials
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-ARG-OIDC] OIDC complements X.509/mTLS for web-based flows

- part-of: [ZR-DOC]
- kind: argument
- quote: OIDC is a natural extension for the authentication layer, complementing X.509/mTLS for web-based flows where browser-compatible identity protocols are required.
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-ARG-CRYPTOGRAPHIC-AGENT-IDENTITY] Agent identity should be cryptographic, with SCIM lifecycle and revocation cascade

- part-of: [ZR-DOC]
- kind: argument
- point: an X.509 agent identity certificate with proof-of-possession fits existing enterprise PKI; metadata (model version, runtime environment, organizational affiliation) can be certificate extensions; lifecycle via SCIM (RFC 7643/7644), where deprovisioning an agent should invalidate all active delegation credentials, tokens and sub-delegations derived from its identity
- quote: Agent identity should be cryptographic, not nominal.
- section: Responses to Focus Area Questions > 2. Identification

## [ZR-ARG-LAYERED-LIFETIMES] Different identity layers should have different lifetimes

- part-of: [ZR-DOC]
- kind: argument
- lifetimes: human identity long-lived; agent identity medium-lived; delegation authority short-lived and task-scoped
- quote: This layered lifetime model is architecturally correct, not a compromise — it reflects the different trust semantics of each layer.
- section: Responses to Focus Area Questions > 2. Identification

## [ZR-ARG-AUTHN-PLUS-DELEGATION] Strong agent authentication combines identity with delegation validation

- part-of: [ZR-DOC]
- kind: argument
- point: mTLS with an X.509 agent certificate plus delegation credential validation proves both who the agent is and what it is authorized to do
- quote: Authentication without authorization verification is insufficient in agentic contexts — an authenticated agent may still be acting outside its authorized scope.
- section: Responses to Focus Area Questions > 3. Authentication

## [ZR-ARG-HUMAN-KEY] The harder key-management problem is the human's signing key

- part-of: [ZR-CLAIM-STORED-KEY]
- kind: argument
- point: for agent keys standard certificate lifecycle management applies; conventional approaches to the human's key (HSM, secure enclave, password-protected keystore) share the vulnerability that the key can be stolen; biometric key derivation reconstructs an ephemeral ECC keypair at signing time
- quote: There is no stored private key to steal, no key file to exfiltrate, no passphrase to phish. The human IS the key, not the holder of one.
- section: Responses to Focus Area Questions > 3. Authentication

## [ZR-ARG-REVOCATION-CASCADE] Revocation should cascade through the delegation chain as a structural property

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [NR-ARG-STD-ZERO-TRUST]
- point: consistent with SP 800-207, revoking the human's root credential should instantly invalidate all derived delegation credentials, issued tokens and sub-delegations
- quote: This requires that each credential's validity depends on its parent's validity — a structural property, not a runtime policy check.
- section: Responses to Focus Area Questions > 3. Authentication

## [ZR-ARG-ZERO-TRUST] Zero trust at the agent-service boundary checks the specific action against the current delegation

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [NR-ARG-STD-ZERO-TRUST]
- corresponds-to: NR-ARG-STD-ZERO-TRUST
- point: consistent with SP 800-207, deny by default and verify every request, with an enforcement proxy validating the delegation credential on every tool invocation
- quote: the verification must check not only "is this agent authenticated" but "does this agent's current delegation authorize this specific action, for this specific service, at this time."
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-ARG-MONOTONIC-CONTEXT] Dynamic context changes are handled by constraints in the credential, not by mutating it

- part-of: [ZR-CLAIM-POLICY-AT-SIGNING-TIME]
- kind: argument
- point: for example, classification-aware data flow rules that monotonically restrict what the agent can do as session sensitivity accumulates; session classification only increases
- quote: Session classification should be monotonically increasing: once an agent accesses data at a given sensitivity level, the session remains at that level or higher.
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-ARG-INDEPENDENT-CLASSIFIER] Aggregation sensitivity is assessed by an independent ephemeral agent the primary agent cannot influence

- part-of: [ZR-CLAIM-DATA-FLOW-ENFORCEMENT]
- kind: argument
- relates-to: [NR-ARG-CONTEXT-CLEAN], [ZR-EX-MOSAIC]
- corresponds-to: NR-ARG-CONTEXT-CLEAN
- point: static aggregation rules in the credential cover known combinations; contextual assessment uses a short-lived, purpose-scoped agent spawned by the enforcement proxy, working from the session's data flow history and machine-parseable classification specifications
- quote: This is the same structural independence principle used for independent quality assurance in software development: the entity that produced the work product should not be the entity that evaluates its compliance.
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-ARG-LEAST-PRIVILEGE] Least privilege made human-decidable, with the task defined in a referenced specification

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [NR-ARG-STD-OAUTH], [ZR-CLAIM-SPECIFICATION-BRIDGE]
- corresponds-to: NR-ARG-STD-OAUTH
- point: the credential enumerates specific tools, services and data classifications; anything else is denied; authority the agent lacks requires a new biometric signing ceremony; the task definition is best expressed as a structured specification the credential references, which domain experts can produce conversationally with AI assistants
- quote: Our approach is to make least privilege human-decidable: the delegation credential enumerates specific tools, specific services, and specific data classifications the agent may access. Anything not explicitly authorized is denied.
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-ARG-INTENT-ARTIFACTS] Intent is best conveyed by external, inspectable artifacts

- part-of: [ZR-CLAIM-INSPECTABLE-ARTIFACTS]
- kind: argument
- relates-to: [NR-REC-1]
- corresponds-to: NR-REC-1
- point: when task, constraints and operating rules are in specifications referenced by the credential, intent is transparent to the authorizing human, the enforcement layer, the auditor and screening tools
- quote: Intent is best conveyed by external, inspectable artifacts rather than by the agent's own claims.
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-ARG-SCOPE-NARROWING] In agent-to-agent delegation, scope can only narrow

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [NR-CLAIM-INTEGRATION]
- corresponds-to: NR-CLAIM-INTEGRATION
- point: an orchestrating agent can issue a sub-delegation granting a strict subset of its own authority; when orchestration is driven by specifications that decompose a task into sub-tasks, sub-delegation boundaries come from the specification rather than the orchestrator's judgment; the human controls maximum delegation depth
- quote: The critical invariant is that scope can only narrow through the delegation chain, never expand.
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-ARG-INJECTION-HOOKS] The enforcement proxy hosts open, bidirectional prompt-injection screening hooks

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [ZR-CLAIM-RISK-TAXONOMY]
- point: authorization prevents unauthorized actions; prompt injection causes unintended actions that may fall within scope; the proxy screens inbound requests for direct injection and outbound tool responses for indirect injection, using the enterprise's preferred detection engine
- quote: ZeroBiometrics provides the architectural enforcement point; enterprises connect their preferred detection engine.
- section: Responses to Focus Area Questions > 6. Prompt Injection Prevention and Mitigation

## [ZR-ARG-PERSONAL-AGENTS] Personal AI agents need pairwise-pseudonymous delegation

- part-of: [ZR-DOC]
- kind: argument
- relates-to: [ZR-CLAIM-PRIVACY-ABSENT]
- point: the fastest-growing deployment of AI agents is personal, acting across organizational boundaries with no central enterprise authority; it needs the same cryptographic properties plus unlinkability of the human's identity across services
- quote: the human's identity at one service must not be correlatable with their identity at another service.
- section: Comments on Use Cases

## [ZR-EVID-ISO-30136] ZeroFace is certified under ISO/IEC 30136:2018 by BixeLab

- part-of: [ZR-DOC]
- kind: evidence
- relates-to: [ZR-CLAIM-ROOT-OF-TRUST]
- point: certified by BixeLab (ISO/IEC 17025 accredited, Australia), validating irreversibility and unlinkability; the response cites the attached white paper, Appendix C, for detail
- quote: This capability is certified under ISO/IEC 30136:2018 by BixeLab (ISO/IEC 17025 accredited, Australia), validating both irreversibility and unlinkability.
- section: Why ZeroBiometrics Is Responding

## [ZR-EVID-MATURITY] Stated maturity of ZeroFace and ZeroSentinel

- part-of: [ZR-DOC]
- kind: evidence
- point: ZeroFace is deployed commercially; ZeroSentinel's architecture is fully specified, with production-ready components at varying stages of maturity
- quote: ZeroFace is ISO/IEC 30136-certified, and is deployed commercially. ZeroSentinel's architecture is fully specified with production-ready components at varying stages of maturity.
- section: Why ZeroBiometrics Is Responding

## [ZR-EVID-CIRCUMVENTION] Agents attempting to circumvent their controls, cited as documented

- part-of: [ZR-DOC]
- kind: evidence
- relates-to: [ZR-CLAIM-EXTERNAL-CRYPTOGRAPHIC-GOVERNANCE]
- supports-claim: ZR-CLAIM-EXTERNAL-CRYPTOGRAPHIC-GOVERNANCE
- source-named: none in the response
- quote: documented instances exist of AI agents becoming sufficiently goal-driven that they actively attempt to circumvent the controls meant to govern them.
- section: Why ZeroBiometrics Is Responding

## [ZR-REC-1] Recommendation: evaluate biometric key derivation

- part-of: [ZR-DOC]
- kind: recommendation
- depends-on: [ZR-CLAIM-STORED-KEY]
- quote: The demonstration project should evaluate biometric key derivation, where the human's signing key is reconstructed from biometric entropy at signing time and never persisted
- section: General Comments (observation 1)

## [ZR-REC-2] Recommendation: consider pairwise-pseudonymous delegation architectures

- part-of: [ZR-DOC]
- kind: recommendation
- depends-on: [ZR-CLAIM-PRIVACY-ABSENT]
- quote: The demonstration project should consider pairwise-pseudonymous delegation architectures, consistent with the privacy principles in FIDO2/WebAuthn, where a relying party can verify that a delegation is valid without learning the human's identity at other services.
- section: General Comments (observation 2)

## [ZR-REC-3] Recommendation: evaluate classification-aware enforcement of cross-tool data flow

- part-of: [ZR-DOC]
- kind: recommendation
- depends-on: [ZR-CLAIM-DATA-FLOW-ENFORCEMENT]
- quote: The demonstration project should evaluate classification-aware enforcement models where cross-tool data flow constraints are embedded in the delegation credential and enforced at the proxy layer, not merely logged after the fact.
- section: General Comments (observation 3)

## [ZR-REC-4] Recommendation: evaluate policy-in-certificate alongside the policy-engine approach

- part-of: [ZR-DOC]
- kind: recommendation
- depends-on: [ZR-ARG-POLICY-IN-CERTIFICATE]
- quote: We recommend the demonstration project evaluate this pattern alongside the traditional policy-engine approach.
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-REC-5] Recommendation: address both enterprise-owned agents and agents hosted by commercial AI services

- part-of: [ZR-DOC]
- kind: recommendation
- point: for enterprise-owned agents runtime attestation is tractable (secure boot, TPM/TEE, model hash verification); for commercial AI services it must come from the AI provider
- quote: The demonstration project should address both cases and should not assume that all agents run in environments the enterprise controls.
- section: Responses to Focus Area Questions > 2. Identification

## [ZR-REC-6] Recommendation: consider the personal use case in a future iteration

- part-of: [ZR-DOC]
- kind: recommendation
- depends-on: [ZR-ARG-PERSONAL-AGENTS]
- relates-to: [NR-REC-3]
- corresponds-to: NR-REC-3 (both look beyond the enterprise scope: the personal response by organization size, this response by personal use)
- quote: We recommend the demonstration project consider the personal use case in a future iteration, as the architectural requirements it surfaces (privacy-by-design, no central authority, cross-organizational delegation) will eventually apply to enterprise deployments as well.
- section: Comments on Use Cases

## [ZR-EX-ALIGNMENT-TABLE] Worked example: the focus area alignment summary

- part-of: [ZR-DOC]
- kind: worked-example
- row-1: 1. Identification; X.509 agent identity certificate (ZeroAgent) with proof-of-possession via mTLS, SCIM lifecycle management, layered lifetimes; standards X.509, mTLS, SCIM (RFC 7643/7644)
- row-2: 2. Authentication; mTLS agent authentication plus delegation credential validation, human authentication via ISO/IEC 30136-certified biometric key reconstruction with no stored private key; standards X.509, mTLS, ISO/IEC 30136
- row-3: 3. Authorization; human-signed delegation certificate (ZeroGrant) with machine-enforceable OID policy extensions, policy fixed at signing time, NGAC graph with human-signed mutations; standards X.509 OIDs, OAuth 2.0 (RFC 8705), NGAC (INCITS 565)
- row-4: 4. Access Delegation; biometric signing ceremony, credentials specifying scope, audience, time bounds and data flow constraints, agent-to-agent sub-delegation with a scope-narrowing invariant; standards X.509, FIDO-inspired ceremony
- row-5: 5. Logging & Transparency; enforcement proxy (ZeroIntent) mediating all agent-to-service interactions, entries with delegation fingerprint, request hash, policy evaluation and outcome; standards append-only audit log, cryptographic fingerprints
- row-6: 6. Data Flow Tracking; classification-aware enforcement at the proxy, tool-level sensitivity classifications, independent ephemeral agent for aggregation assessment, open DLP hook, cross-tool flow constraints enforced; standards X.509 OID extensions (DATA-FLOW-POLICY)
- row-7: Prompt Injection; three-layer defense-in-depth; standards open hook API, vendor-neutral
- quote: Cross-tool flow constraints enforced, not just logged.
- section: Focus Area Alignment Summary

## [ZR-EX-DEPLOYMENT-PATTERNS] Worked example: three enterprise deployment patterns

- part-of: [ZR-DOC]
- kind: worked-example
- pattern-1: developer tooling; broad permissions inherited from the developer's service accounts, with no mechanism to scope authority to a task or time window
- pattern-2: workflow automation; email, calendars, CRM and document stores, with no cryptographic binding to the authorizing human
- pattern-3: security operations; the non-repudiation requirement is highest here
- quote: The authorization gap here is acute — these agents access sensitive data across multiple services with no cryptographic binding to the human who authorized the access.
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-EX-ZEROSENTINEL-COMPONENTS] Worked example: the ZeroSentinel components named in the response

- part-of: [ZR-DOC]
- kind: worked-example
- zerocert: X.509 certificate containing the public portion of a biometrically derived IdentityKey; the private key is reconstructed from face entropy at signing time
- zerogrant: delegation certificate signed by the human in a biometric ceremony, specifying scope, audience, time bounds and data flow constraints as OID extensions
- zerointent: proxy enforcement gateway validating every agent request against the signed ZeroGrant, with open hooks for prompt injection screening and DLP, issuing sender-constrained OAuth 2.0 tokens (RFC 8705)
- zeroagent: X.509 agent identity certificate with proof-of-possession, validated via mTLS, lifecycle managed via SCIM
- quote: It operates at the protocol layer: deployment is a proxy configuration, not a platform migration.
- section: Responses to Focus Area Questions > 1. General Questions

## [ZR-EX-MOSAIC] Worked example: the mosaic effect

- part-of: [ZR-ARG-INDEPENDENT-CLASSIFIER]
- kind: worked-example
- quote: An agent authorized to read HR records and also read calendar data could infer personnel patterns that neither data source reveals alone.
- section: Responses to Focus Area Questions > 4. Authorization

## [ZR-EX-INJECTION-LAYERS] Worked example: three layers that constrain the damage after a prompt injection

- part-of: [ZR-DOC]
- kind: worked-example
- relates-to: [NR-ARG-PROMPT-INJECTION], [ZR-ARG-INJECTION-HOOKS]
- corresponds-to: NR-ARG-PROMPT-INJECTION
- layer-1: scope-bounded delegation; the proxy validates every request against the signed credential, so an injection cannot exceed the delegation scope
- layer-2: classification-aware data flow enforcement; flow constraints can block exfiltration within the authorized tool set
- layer-3: independent content inspection; open DLP hooks inspect request and response content
- quote: No single layer solves prompt injection.
- quote-2: A successful injection cannot cause the agent to exceed its delegation scope because the enforcement proxy validates every request against the signed credential.
- section: Responses to Focus Area Questions > 6. Prompt Injection Prevention and Mitigation
