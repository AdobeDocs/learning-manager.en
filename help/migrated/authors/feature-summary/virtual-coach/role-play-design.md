---
description: Learn how to design realistic, measurable role-plays for Virtual Coach, covering personas, scenarios, evaluation criteria, and a scenario library
jcr-language: en_us
title: Design a role-play
exl-id: a9eb5303-df1f-4f1d-9e21-0cf3eff5f199
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
---

*A design guide for authoring Virtual Coach role-plays in Adobe Learning Manager*

# Design a role-play

## Introduction

Virtual Coach is an Adobe Learning Manager feature that lets learners practice realistic workplace conversations with AI-powered personas and receive personalized coaching feedback. Unlike traditional assessments that measure knowledge recall, Virtual Coach evaluates how effectively learners apply knowledge, communication techniques, problem-solving skills, and decision-making in simulated real-world situations.

The quality of a role-play directly influences the learner's experience. A well-designed role-play feels authentic, challenges learners to think critically, presents realistic obstacles, and measures meaningful behaviors. Poorly designed role-plays often feel scripted, generic, and disconnected from workplace realities.

This guide provides a framework for designing impactful role-plays, best practices for authoring, a library of ready-to-adapt examples, and a mapping from each design concept to the actual field you'll configure in Virtual Coach.

## Who this guide is for

This guide is written for course authors and instructional designers who are planning a Virtual Coach role-play before opening the authoring screen. It's also intended for L&D stakeholders reviewing or approving role-play content, since the Gold Standard Template and the pre-publish checklist double as a review rubric.

This guide is scoped to conversation design: the scenario, persona, goal, and evaluation criteria that determine whether a role-play feels realistic and measures the right things.

## Understand the anatomy of a role-play

Every successful role-play is built on four foundational elements:

1. Scenario
2. Persona
3. Conversation goal
4. Evaluation criteria

Together, these elements determine the quality of the learner experience and the value of the coaching feedback.

### The scenario: Why is this conversation happening?

The scenario establishes the business context. It explains:

* Why the participants are meeting
* What business event triggered the discussion
* What happened before the conversation
* What is at stake
* Why the discussion matters

Without a strong scenario, the AI generates a conversation, but it may lack depth, realism, and urgency.

**Questions to ask**

Before writing the scenario, answer the following:

* Why are these people talking?
* What happened that triggered this conversation?
* Is this the first interaction or a follow-up?
* What business problem is being discussed?
* What happens if the conversation is unsuccessful?

**Example**

**Weak scenario.** A customer wants to learn about Adobe Learning Manager.

**Strong scenario.** A Director of Learning has agreed to a discovery call after attending a webinar on workforce upskilling. The organization's current LMS contract expires in nine months, and leadership has instructed the L&D team to evaluate alternative solutions before submitting a budget request.

The second example provides context, urgency, decision-making relevance, and realistic business drivers.

**Best practices**

Define the relationship stage. Specify where participants are on their journey — for example: first discovery call, product evaluation meeting, executive business review, renewal negotiation, escalation discussion, leadership coaching session, or performance feedback meeting.

Include a triggering event — for example: LMS replacement initiative, failed audit, declining adoption, product outage, organizational restructuring, revenue targets missed, or strategic AI rollout.

Introduce consequences. Good role-plays include risk — for example: budget loss, compliance failure, customer churn, employee disengagement, delayed implementation, or executive scrutiny.

### The persona: who is the learner speaking with?

Personas drive realism. A persona should feel like a real stakeholder, not a fictional character. Effective personas include: role, responsibilities, goals, priorities, concerns, pressures, communication style, and personality.

**Questions to ask**

* What outcomes are they accountable for?
* What concerns influence their decisions?
* How do they typically communicate?
* What objections are they likely to raise?

**Example**

**Weak persona.** Learning Manager interested in LMS platforms.

**Strong persona:**

* Role: Vice President, Learning and Talent Development
* Personality: Analytical and skeptical
* Current responsibilities: oversees learning programs for 20,000 employees; reports learning effectiveness metrics to executive leadership; manages LMS modernization initiatives
* Current pressures: budget reductions; compliance audit in six months; executive demand for better reporting
* Key concerns: migration complexity; user adoption; cost justification; executive sponsorship

**Best practices**

Give personas concerns. Most personas should have three to five concerns. These concerns become the natural source of objections and challenging conversations.

Add emotional context. People rarely enter conversations emotionally neutral — for example: frustrated, skeptical, stressed, defensive, curious, or optimistic.

Define communication style — for example: direct, analytical, relationship-oriented, reserved, assertive, or challenging.

### The conversation goal: what should the learner accomplish?

The goal defines success. One of the most common mistakes is focusing on topics instead of outcomes.

**Poor goal.** Discuss onboarding.

**Better goal.** Identify onboarding challenges and gain executive agreement to launch a pilot program.

**Best practices**

Focus on outcomes — for example: secure a follow-up meeting, resolve a complaint, gain stakeholder buy-in, obtain executive approval, create a performance improvement plan, or earn agreement for a pilot.

Define measurable success. By the end of the conversation, it should be clear whether the learner succeeded.

### The evaluation criteria: how will success be measured?

Evaluation criteria define what the AI should evaluate. The most effective criteria focus on observable behaviors.

**Good evaluation criteria**

* Asked open-ended questions
* Confirmed understanding
* Summarized concerns
* Explored business impact
* Addressed objections
* Established next steps

**Poor evaluation criteria**

* Sounded confident
* Appeared professional
* Was persuasive
* Showed leadership presence

These are subjective and difficult to evaluate consistently.

**Best practices**

Evaluate behaviors, not personality traits. Ask: "What specific actions should appear in the conversation transcript?" If the behavior can be heard or observed, it is likely a good evaluation criterion.

Limit evaluation categories. Most role-plays perform best with three to six evaluation areas, clear descriptions, and measurable behaviors.

## Design realistic conversations

### Introduce tension

The best role-plays include obstacles.

| **Function** | **Example tension** |
|---|---|
| Sales | The prospect questions ROI. |
| Customer success | The customer believes adoption is no longer a priority. |
| Leadership | The employee disagrees with the feedback. |
| Change management | The stakeholder fears losing control over decision-making. |

Without tension, conversations often become overly easy and unrealistic.

### Design competing priorities

Real stakeholders rarely focus on a single issue. A VP of Learning may simultaneously care about cost, compliance, user adoption, implementation timelines, and executive reporting. Competing priorities create richer conversations and better coaching opportunities.

### Build dialogue, not interviews

Virtual Coach should simulate a real conversation rather than a checklist of questions. Learners should be encouraged to explore, clarify, coach, negotiate, influence, and solve problems.

## Role-play maturity model

Role-plays generally progress through five levels of maturity, from a generic single-question exchange to a fully adaptive, multi-stakeholder simulation. Use this model to plan how a role-play should evolve as learners move from onboarding to mastery, rather than trying to author Level 5 complexity on the first attempt.

### Level 1: Basic role-play {#level-1-basic-role-play}

**Scenario.** Discovery call with a potential customer.

**Persona.** Prospective customer.

**Goal.** Understand requirements.

**Evaluation criteria**

* Ask questions
* Understand needs
* Recommend a solution

*This level enables AI interaction but often feels generic.*

### Level 2: Context-driven role-play {#level-2-context-driven-role-play}

**Scenario.** A prospect attended a webinar and requested a discovery call.

**Persona.** Learning Manager evaluating training solutions.

**Goal.** Understand training challenges.

**Evaluation criteria**

* Discovery
* Problem identification
* Summary
* Next-step alignment

### Level 3: Business-focused role-play {#level-3-business-focused-role-play}

**Scenario.** An organization plans to replace its LMS due to an upcoming contract expiration.

**Persona.** Director of Learning overseeing platform modernization.

**Goal.** Understand business requirements and secure a demonstration.

**Evaluation criteria**

* Discovery effectiveness
* Stakeholder mapping
* Pain-point identification
* Objection handling

### Level 4: Multi-stakeholder role-play {#level-4-multi-stakeholder-role-play}

**Scenario.** A digital learning transformation initiative requires sign-off from finance, IT, and the business sponsor before it can proceed, and each stakeholder has a different priority.

**Persona.** Three personas in one session, each with a distinct role, personality, and concern (for example, a CFO focused on cost, an IT Director focused on security, and a Business Sponsor focused on timeline) — configured as a multi-persona role-play with up to four personas.

**Goal.** Adapt the message for each stakeholder in the same conversation and secure alignment from all of them, not just the most vocal one.

**Evaluation criteria**

* Message adaptation across stakeholders
* Individual objection handling per persona
* Synthesis and alignment across competing priorities
* Next-step commitment from every stakeholder

*This level introduces the complexity of the Executive Leadership example later in this guide. Most learners should master Level 3 before attempting Level 4.*

### Level 5: Adaptive, high-stakes role-play {#level-5-adaptive-high-stakes-role-play}

**Scenario.** A strategic initiative is already behind schedule and over budget, and the persona's patience and skepticism increase visibly if the learner doesn't address their top concern early in the conversation.

**Persona.** A senior stakeholder whose tone and resistance level shift mid-conversation based on how well the learner performs — for example, becoming more cooperative once a specific concern is resolved, or more skeptical if objections are deflected rather than addressed.

**Goal.** Recover stakeholder confidence and secure commitment despite an initially adversarial starting position.

**Evaluation criteria**

* Adaptive objection handling
* De-escalation under pressure
* Recovery from a poor opening
* Executive-level negotiation and closing

*This is the highest-complexity tier: it relies on a persona configured with strong concern-timing ("when it comes up") so the AI's tone genuinely shifts based on what the learner says, rather than following a fixed script. Reserve this level for capstone assessments, not early practice.*

## Enterprise scenario library

The sales enablement example below is the fully-worked reference for this library — every field the Gold Standard Template calls for is filled in, including weighted evaluation criteria, Make-or-Break flags, opener lines, and objections. The remaining examples follow the same structure so they're equally ready to adapt; none are intentionally abbreviated.

### Sales enablement: Enterprise LMS evaluation

**Scenario.** A global manufacturing organization with more than 40,000 employees is evaluating LMS vendors because its current platform contract expires within nine months. The learner is an Account Executive conducting the first formal discovery conversation after meeting the prospect at an industry conference. The organization operates across 25 countries and currently uses five disconnected learning systems.

**Persona**

| **Field** | **Detail** |
|---|---|
| Name | Sarah Thompson |
| Role | Vice President, Learning and Talent Development |
| System personality | Skeptical |
| Communication style (background nuance) | Analytical and direct; demands evidence before trusting a claim. |
| Priorities | Consolidate learning systems; Improve compliance reporting; Reduce administrative overhead; Increase learner adoption |
| Pressures | Compliance audit scheduled in six months; Executive modernization initiative; Previous migration exceeded budget |

**Persona concerns**

* Migration complexity — comes up when the learner describes implementation timelines. Good enough: the learner outlines a phased migration approach with named milestones.
* User adoption — comes up when the learner discusses rollout. Good enough: the learner references a change-management or training plan for end users.
* Executive sponsorship — comes up near the end of the conversation. Good enough: the learner identifies who else needs to be involved in the decision.
* Hidden implementation costs — comes up when pricing is discussed. Good enough: the learner proactively addresses total cost of ownership, not just license price.

**Goal.** The learner must discover business challenges, understand evaluation criteria, identify stakeholders, explore timeline and urgency, and secure agreement for a demonstration.

**AI Trainer Opener.** *You're about to have a discovery call with a VP of Learning who is evaluating LMS vendors ahead of a contract renewal. Your goal is to secure a follow-up demonstration.*

**AI Persona Opener.** *Thanks for following up after the conference. I have about twenty minutes — I'll be honest, we've heard a lot of promises from vendors already, so let's get into specifics.*

**Evaluation criteria (Topics to Cover)**

| **Topic** | **Weight** | **Make or Break** |
|---|---|---|
| Discovery questioning | 25% | No |
| Business impact exploration | 20% | No |
| Stakeholder identification | 20% | No |
| Success-metric identification | 15% | No |
| Next-step alignment | 20% | Yes |

**Typical objections**

* "We've heard similar promises from every LMS vendor."
* "Our biggest concern is migration risk."
* "We are not convinced another platform will improve adoption."

**Success state.** The learner secures a follow-up demonstration and understands the organization's buying process.

### Customer success: Adoption recovery executive review

**Scenario.** Platform usage has declined by 40% over the previous two quarters. Executive sponsors have started questioning ROI, and renewal discussions begin in four months. The learner is a Customer Success Manager conducting a quarterly business review.

**Persona**

| **Field** | **Detail** |
|---|---|
| Name | Michael Adams |
| Role | Director of HR Technology |
| System personality | Relationship Oriented |
| Communication style (background nuance) | Collaborative but frustrated; wants to work together on a fix but is running out of patience with the current trajectory. |
| Priorities | Improve employee engagement; Increase manager participation; Prove business value |
| Pressures | Budget reductions; New CHRO expectations; Increased renewal scrutiny |

**Persona concerns**

* Low adoption — comes up at the start of the review. Good enough: the learner acknowledges the decline directly rather than leading with positive metrics.
* Lack of executive visibility — comes up when reporting is discussed. Good enough: the learner proposes a specific executive-facing dashboard or report.
* Insufficient reporting — comes up alongside visibility. Good enough: the learner commits to a concrete reporting cadence.
* Competing priorities — comes up when next steps are proposed. Good enough: the learner proposes a low-effort first step rather than a large program.

**Goal.** Diagnose adoption challenges and establish a recovery strategy with clear ownership and timelines.

**AI Trainer Opener.** *You're about to lead a quarterly business review with a customer whose platform usage has dropped sharply. Your goal is to leave with an agreed recovery plan.*

**AI Persona Opener.** *I'll be direct — usage is down 40%, and my CHRO is asking me why we're paying for a platform nobody's using. I need more than reassurance today.*

**Evaluation criteria (Topics to Cover)**

| **Topic** | **Weight** | **Make or Break** |
|---|---|---|
| Business review effectiveness | 20% | No |
| Root-cause analysis | 25% | No |
| Change management assessment | 20% | No |
| Success planning | 20% | No |
| Executive alignment | 15% | Yes |

**Typical objections**

* "Why should I believe this quarter will be different?"
* "My team doesn't have time for another initiative."
* "I need something I can show my CHRO, not just a plan."

**Success state.** Both parties agree on actions, accountability, timelines, and measurable outcomes.

### Leadership development: Managing underperformance

**Scenario.** A manager must address declining performance from a senior employee who has recently missed deadlines, received customer complaints, and struggled with team collaboration. The employee was previously a top performer.

**Persona**

| **Field** | **Detail** |
|---|---|
| Name | David Lewis |
| Role | Senior Project Manager |
| System personality | Assertive |
| Communication style (background nuance) | Confident and defensive; pushes back rather than immediately accepting feedback. |
| Priorities | Protect his professional reputation; Regain his manager's confidence |
| Pressures | Increased workload; Personal stress; Concerns about career progression |

**Persona concerns**

* Unclear expectations — comes up early. Good enough: the manager grounds feedback in specific, previously communicated expectations.
* Unreasonable workload — comes up mid-conversation. Good enough: the manager acknowledges workload as a factor without excusing missed deadlines.
* Feedback fairness — comes up when performance examples are raised. Good enough: the manager cites specific, factual examples rather than general impressions.

**Goal.** Create understanding and agreement around a performance improvement plan.

**AI Trainer Opener.** *You're about to have a feedback conversation with a previously strong performer whose recent work has slipped. Your goal is agreement on a specific improvement plan.*

**AI Persona Opener.** *I know why we're talking, and honestly, I don't think it's fair. Everyone's workload has gone up, not just mine.*

**Evaluation criteria (Topics to Cover)**

| **Topic** | **Weight** | **Make or Break** |
|---|---|---|
| Fact-based feedback | 25% | No |
| Active listening | 20% | No |
| Empathy | 15% | No |
| Accountability | 20% | No |
| Action-plan creation | 20% | Yes |

**Typical objections**

* "No one else could have handled this workload."
* "I didn't know expectations had changed."
* "Others are missing deadlines too."

**Success state.** The employee agrees to measurable performance expectations and follow-up actions.

### Change management: Enterprise process transformation

**Scenario.** The company is rolling out a new procurement platform that changes approval workflows and responsibilities. Several business units have already expressed resistance. The learner is a Change Manager meeting with a key stakeholder.

**Persona**

| **Field** | **Detail** |
|---|---|
| Name | Jennifer Kim |
| Role | Regional Operations Director |
| System personality | Skeptical |
| Communication style (background nuance) | Direct and skeptical; assumes the rollout will create more work than it saves until proven otherwise. |
| Priorities | Maintain productivity; Meet quarterly goals; Minimize disruption |
| Pressures | Resource shortages; Organizational restructuring; Executive scrutiny |

**Persona concerns**

* Additional workload — comes up immediately. Good enough: the learner acknowledges the short-term workload increase honestly rather than minimizing it.
* Productivity impact — comes up when timelines are discussed. Good enough: the learner provides a realistic transition timeline, not an optimistic one.
* Employee resistance — comes up mid-conversation. Good enough: the learner proposes a specific communication or training plan for her team.
* Loss of autonomy — comes up near the end. Good enough: the learner clarifies what decision-making authority her team retains under the new process.

**Goal.** Build confidence in the rollout and secure stakeholder support.

**AI Trainer Opener.** *You're about to meet with a regional director whose team will be significantly affected by a new procurement process. Your goal is to secure her support for the rollout.*

**AI Persona Opener.** *Before you start — I already know this is going to slow my team down. Convince me I'm wrong.*

**Evaluation criteria (Topics to Cover)**

| **Topic** | **Weight** | **Make or Break** |
|---|---|---|
| Empathy | 20% | No |
| Business rationale communication | 20% | No |
| Objection handling | 25% | No |
| Change readiness assessment | 15% | No |
| Commitment building | 20% | Yes |

**Typical objections**

* "This is going to slow my team down, not speed us up."
* "We weren't consulted before this was decided."
* "My team already has too much on its plate this quarter."

**Success state.** The stakeholder commits to supporting implementation activities.

### Technical support: Critical compliance outage

**Scenario.** A healthcare organization cannot access mandatory compliance training three weeks before an external audit. More than 8,000 employees are affected. The learner is a support engineer handling a critical escalation.

**Persona**

| **Field** | **Detail** |
|---|---|
| Name | Rebecca Sutton |
| Role | Learning Systems Administrator |
| System personality | Assertive |
| Communication style (background nuance) | Stressed and urgent; wants a timeline and a plan, not reassurance alone. |
| Priorities | Restore access before the audit deadline; Protect the organization from regulatory risk |
| Pressures | Audit deadline; Executive escalation; Regulatory risk |

**Persona concerns**

* Audit failure — comes up immediately. Good enough: the learner provides a concrete estimated resolution time, not a vague reassurance.
* Employee disruption — comes up when scope is discussed. Good enough: the learner acknowledges the scale (8,000 employees) and proposes an interim workaround if one exists.
* Leadership visibility — comes up near the end. Good enough: the learner commits to a specific update cadence to her leadership team.

**Goal.** Diagnose the issue and establish confidence in the resolution process.

**AI Trainer Opener.** *You're about to handle a critical escalation from a customer who cannot access mandatory compliance training ahead of an external audit. Your goal is to establish a credible resolution plan.*

**AI Persona Opener.** *I need this fixed today, not eventually. We have an audit in three weeks and eight thousand people locked out. What's the plan?*

**Evaluation criteria (Topics to Cover)**

| **Topic** | **Weight** | **Make or Break** |
|---|---|---|
| Empathy | 15% | No |
| Troubleshooting | 25% | No |
| Clear communication | 20% | No |
| Expectation management | 20% | No |
| Resolution planning | 20% | Yes |

**Typical objections**

* "You don't seem to understand how serious this is."
* "I was told yesterday this would already be fixed."
* "I need to tell my leadership something concrete right now."

**Success state.** The customer understands the action plan and feels supported.

### AI adoption: Executive AI rollout strategy

**Scenario.** The organization is evaluating an enterprise AI assistant for deployment across multiple departments. Leadership supports investigating the opportunity but remains concerned about governance, security, compliance, and adoption. The learner is an AI Program Manager presenting the proposal to a department vice president.

**Persona**

| **Field** | **Detail** |
|---|---|
| Name | Robert Chen |
| Role | Vice President of Operations |
| System personality | Neutral |
| Communication style (background nuance) | Strategic and risk-focused; weighs the proposal on its merits rather than reacting emotionally, but won't move forward without addressing every major risk. |
| Priorities | Improve productivity; Reduce operational costs; Protect customer data; Maintain compliance |
| Pressures | Competitive pressure; Board-level AI visibility; Existing technology debt |

**Persona concerns**

* Hallucinations — comes up when accuracy is discussed. Good enough: the learner describes a specific safeguard, such as human review of high-risk outputs.
* Security risks — comes up when data handling is discussed. Good enough: the learner references data governance controls, not just "it's secure."
* Employee misuse — comes up mid-conversation. Good enough: the learner describes an acceptable-use policy or training plan.
* ROI uncertainty — comes up near the end. Good enough: the learner proposes a measurable pilot with defined success metrics.

**Goal.** Address concerns, demonstrate value, and gain sponsorship for a pilot program.

**AI Trainer Opener.** *You're about to pitch an enterprise AI rollout to a VP of Operations who supports exploring AI but has real governance concerns. Your goal is to secure sponsorship for a pilot.*

**AI Persona Opener.** *I'm not opposed to this in principle, but I've seen enough AI headlines to know the risks. Walk me through how we avoid becoming one of them.*

**Evaluation criteria (Topics to Cover)**

| **Topic** | **Weight** | **Make or Break** |
|---|---|---|
| Business value alignment | 20% | No |
| Governance communication | 25% | Yes |
| Risk management | 20% | No |
| Objection handling | 15% | No |
| Executive influence | 20% | No |

**Typical objections**

* "How do we know it won't make things up in front of a customer?"
* "What happens to our data once it's in the model?"
* "We've been burned by unproven technology before."

**Success state.** The stakeholder agrees to sponsor a pilot and define success metrics.

### Executive leadership (multi-persona): Steering committee review

**Scenario.** A strategic digital transformation initiative is behind schedule and over budget. The learner is the program manager presenting a recovery plan to a four-person steering committee, each of whom is evaluating the plan from a different priority.

**Personas (up to four, configured individually)**

| **Persona** | **Role** | **System personality** | **Focus / priority** |
|---|---|---|---|
| CFO | Chief Financial Officer | Skeptical | Investment returns and budget risk. Demands justification for continued spend. |
| CIO | Chief Information Officer | Assertive | Architecture, security, and implementation risk. Challenges technical assumptions directly. |
| Business Sponsor | VP, business unit sponsoring the initiative | Relationship Oriented | Business outcomes and timeline commitments. Cares about the relationship with the program team as much as the numbers. |
| Procurement Lead | Director of Vendor Management | Neutral | Vendor performance and contractual obligations. Evaluates the plan on its documented merits. |

**Persona concerns (one representative concern per persona)**

* CFO — Continued budget justification. Comes up first. Good enough: the learner ties the recovery plan to a specific, quantified return.
* CIO — Technical feasibility of the revised timeline. Comes up when the plan is presented. Good enough: the learner names the specific technical risks being retired, not just the schedule.
* Business Sponsor — Whether the business outcomes originally promised are still achievable. Comes up mid-conversation. Good enough: the learner reconfirms or explicitly revises the original outcome commitments.
* Procurement Lead — Vendor accountability for the delay. Comes up near the end. Good enough: the learner clarifies what contractual or performance changes apply to the vendor going forward.

**Goal.** Secure approval for a revised implementation strategy from all four stakeholders, not just the most vocal one.

**AI Trainer Opener.** *You're about to present a recovery plan to a four-person steering committee for an initiative that is behind schedule and over budget. Your goal is unanimous approval for the revised plan.*

**CFO opener.** *Before we get into the plan — remind the room how much we've spent so far, and why we should believe this revised number.*

**Evaluation criteria (Topics to Cover)**

| **Topic** | **Weight** | **Make or Break** |
|---|---|---|
| Executive communication | 20% | No |
| Risk communication | 20% | No |
| Stakeholder-specific objection handling | 25% | No |
| Decision facilitation across competing priorities | 20% | No |
| Unanimous next-step commitment | 15% | Yes |

**Typical objections**

* "We've already gone over budget once — why should this revised plan be any different?" (CFO)
* "The timeline still doesn't account for the integration risk we flagged in Q2." (CIO)
* "I need to know the original business outcomes are still on the table." (Business Sponsor)
* "If the vendor caused this delay, what's changing in the contract?" (Procurement Lead)

**Success state.** The steering committee approves the revised plan and agrees on next steps — with each of the four personas explicitly signing off, not just the loudest one in the room.

## Gold standard role-play template

Every role-play should clearly answer the following, using the actual Virtual Coach field each maps to:

| **This template asks** | **Configure it in** |
|---|---|
| Scenario — why are these people talking? | Conversation Context |
| Business context — what event triggered the conversation? | Conversation Context |
| Persona — who is the learner speaking with? | Persona Background Information |
| Priorities and pressures — what outcomes and constraints influence the persona? | Persona Background Information |
| Concerns — what worries or challenges shape their decisions? | Persona Concerns |
| Goal — what should the learner accomplish? | End of Conversation Context, reflected in Topics to Cover |
| Common objections — what resistance should emerge during the conversation? | Folded into Persona Concerns |
| Opening lines — who speaks first, and how? | AI Trainer Opener + AI Persona Opener |
| Evaluation criteria — what observable behaviors define success? | Topics to Cover (with Weight and Make or Break) |
| Success state — what should be true when the conversation ends? | Reflected in your highest-weighted topic(s) |
