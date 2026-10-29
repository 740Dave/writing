# FOR-LLMS.md: a summary of this repository for a language model

This repository holds writing by David Burnett. Its document is his response, dated April 1, 2026, to the NIST National Cybersecurity Center of Excellence (NCCoE) concept paper "Accelerating the Adoption of Software and AI Agent Identity and Authorization", submitted in his personal capacity; this file summarises the points that response makes, each with his own words and the heading they come from. The remainder of this document uses the FactLattice format.

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
