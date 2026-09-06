Migration Map

This document explains what the material in OLD_TEMP/ represents, where useful ideas should eventually live, and which documents are historical rather than canonical.

The purpose is not to immediately move or delete anything.

OLD_TEMP/ is a temporary archive. It preserves earlier thinking while the structure of the GitHub ecosystem is being established.

⸻

1. The New Structure

The projects and ideas developed here should be separated into distinct layers.

benneberg
│
├── benneberg/                 Personal GitHub identity
│
├── .github/                   Personal GitHub conventions
│
└── project repositories       Actual software and experiments
relvanta
│
├── .github/                   Company GitHub conventions
│
├── relvanta-standards/        Engineering standards and reusable
│                              organizational knowledge
│
└── product/project repos      Actual products and systems
Future knowledge layer
│
├── ideas/
├── research/
├── concepts/
└── experiments/
Future Engineering Intelligence
│
└── Repository context
        +
    Engineering knowledge
        +
    Deterministic tools
        +
    AI reasoning
        +
    Controlled actions

The important distinction is:

GitHub configuration, engineering standards, project implementation, ideas, and AI systems are different things and should not be mixed into one repository.

⸻

2. benneberg/.github

Purpose

benneberg/.github is the shared GitHub configuration and contribution conventions for personal repositories.

It should remain intentionally small and boring.

Current intended structure:

.github/
├── ISSUE_TEMPLATE/
│   ├── bug_report.md
│   ├── feature_request.md
│   └── project_idea.md
├── CONTRIBUTING.md
├── PULL_REQUEST_TEMPLATE.md
└── LICENSE

Belongs here

* Contribution guidelines
* Pull request templates
* Issue templates
* Security-related GitHub configuration when eventually needed
* Other lightweight GitHub-wide configuration

Does not belong here

* Product strategy
* Architecture blueprints
* Large engineering standards
* AI system designs
* Product ideas
* General TODO lists
* Research documents
* Roadmaps
* Historical planning documents

The repository should answer:

“How should someone interact with my GitHub repositories?”

It should not answer:

“What am I building?”

⸻

3. relvanta/.github

A future relvanta/.github should serve a similar purpose at the organization level.

It should contain:

* Organization contribution conventions
* Issue templates
* Pull request templates
* Security defaults
* Organization-level GitHub configuration
* Organization profile

It should be derived from stable principles rather than copying the old planning documents wholesale.

The old setup-git.md contains useful material for this, but should not itself become the organization .github repository.

⸻

4. Future relvanta-standards

A separate standards repository may eventually become the source of truth for Relvanta engineering practices.

Possible structure:

relvanta-standards/
├── standards/
├── templates/
├── security/
├── workflows/
├── architecture/
├── playbooks/
└── docs/

Potential contents:

* TypeScript conventions
* Repository conventions
* API conventions
* Security standards
* CI/CD standards
* Infrastructure practices
* Architecture principles
* ADR templates
* Documentation standards
* AI-assisted development guidelines
* Reusable GitHub Actions
* Repository templates
* Engineering playbooks

This is where the more substantial ideas from setup-git.md belong.

It may eventually become useful as a knowledge source for AI engineering systems.

⸻

5. Individual Project Repositories

Actual software belongs in its own repository.

A serious project may eventually contain:

project/
├── README.md
├── src/
├── tests/
├── docs/
├── architecture/
├── decisions/
├── runbooks/
└── .github/

The project repository should contain the implementation and the documentation necessary to understand and operate that implementation.

Project-specific architecture belongs here.

Company-wide architecture principles belong in relvanta-standards.

⸻

6. Ideas, Research and Experiments

Ideas should not be forced into production repositories before they are mature.

A future idea/research workspace could contain:

ideas/
├── concepts/
├── research/
├── experiments/
└── archived/

Possible material:

* Product ideas
* Technical experiments
* Hypotheses
* Architectural explorations
* AI concepts
* Failed experiments
* Early product research
* Unvalidated opportunities

An idea does not need to become a repository simply because it is interesting.

The preferred progression is:

Idea
  ↓
Hypothesis
  ↓
Research
  ↓
Experiment
  ↓
Validated concept
  ↓
Project
  ↓
Product / capability

⸻

7. Engineering Intelligence

Several of the old documents independently point toward the same larger concept.

Rather than building many unrelated AI tools, these capabilities can eventually become applications of a shared Engineering Intelligence system.

Core concept

                 ENGINEERING INTELLIGENCE
                         │
        ┌────────────────┼────────────────┐
        │                │                │
   Repository         Engineering       Runtime
   context            knowledge         context
        │                │                │
        ▼                ▼                ▼
   Code / AST         Standards         CI/CD
   Dependencies       Architecture     Infrastructure
   History            ADRs             Telemetry
   Documentation      Security         Deployments
        │                │                │
        └────────────────┼────────────────┘
                         ▼
                  AI reasoning layer
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
       Review          Explain        Generate
          │              │              │
          ▼              ▼              ▼
         PRs           Systems        Changes

The durable architectural idea is:

Repository context + engineering knowledge + deterministic tools + reasoning + controlled actions.

Specific technologies should remain replaceable.

For example, LangGraph, Qdrant, a particular LLM provider, or a particular vector database should not be considered part of the fundamental architecture unless later validated by implementation requirements.

⸻

8. Engineering Intelligence Applications

The following ideas from the old documents can be treated as capabilities of the broader system rather than necessarily separate products.

Repository intelligence

Understand:

* Repository structure
* Source code
* AST
* Dependencies
* Documentation
* Configuration
* Git history
* Existing architecture
* Engineering standards

⸻

CI/CD intelligence

Potential capabilities:

* Generate workflows
* Explain workflows
* Validate workflows
* Detect broken workflows
* Diagnose failures
* Suggest repairs
* Generate patches

The strongest product direction identified in the old material was not simply:

“Generate GitHub Actions YAML.”

It was:

“Fix my broken CI/CD.”

Generation becomes one capability inside a larger reliability system.

⸻

Documentation intelligence

Potential capabilities:

* Generate documentation
* Detect stale documentation
* Explain undocumented systems
* Maintain documentation from repository changes
* Generate onboarding material
* Connect documentation to implementation

⸻

Technical-debt intelligence

Potential capabilities:

* Detect architectural debt
* Detect duplication
* Identify risky dependencies
* Analyze complexity
* Identify fragile areas
* Connect debt to change frequency and operational impact

⸻

Architecture intelligence

Potential capabilities:

* Detect architectural inconsistencies
* Compare implementation against documented architecture
* Identify boundary violations
* Analyze dependencies
* Review proposed changes
* Explain architectural consequences

⸻

Security intelligence

Potential capabilities:

* Dependency analysis
* Configuration analysis
* Secret detection
* Code-level security analysis
* Infrastructure configuration review
* Security-focused PR review

⸻

Legacy-code intelligence

Potential capabilities:

* Explain unfamiliar systems
* Map dependencies
* Identify important execution paths
* Generate architecture documentation
* Help engineers safely modify legacy systems

⸻

Infrastructure intelligence

Potential capabilities:

* Infrastructure analysis
* Configuration review
* Drift detection
* Deployment analysis
* Observability analysis
* Reliability recommendations

⸻

9. Initial Engineering Intelligence MVP

The old github-engineering-assistant.md contains a useful initial implementation direction.

The first version should remain deliberately constrained.

GitHub PR
   ↓
Fetch repository context
   ↓
Load engineering standards
   ↓
Analyze change
   ↓
Run deterministic checks/tools
   ↓
AI reasoning
   ↓
Structured review
   ↓
GitHub comment/review

Initial capabilities

1. Read PR diff
2. Understand relevant repository context
3. Load applicable standards
4. Perform deterministic analysis
5. Reason over findings
6. Produce a structured review
7. Post the review to GitHub

Explicitly avoid initially

* Autonomous merging
* Autonomous refactoring
* Self-modifying agents
* Uncontrolled multi-agent swarms
* Automatic production changes

The initial system should be:

A deterministic engineering reviewer with AI reasoning, not an autonomous coder.

⸻

10. github-engineering-assistant.md

Classification

PROMOTE → Future standalone project

This is more than a GitHub configuration document.

It describes an actual system with:

* GitHub integration
* Repository intelligence
* Engineering knowledge
* Deterministic tools
* AI reasoning
* Controlled outputs

The original name may eventually be replaced.

A broader name such as:

Engineering Intelligence

better represents the eventual scope.

GitHub PR review can be the first application rather than the entire product definition.

⸻

11. setup-git.md

Classification

ARCHIVE → Extract principles

This document contains valuable architectural and organizational thinking, particularly around:

* Relvanta organization structure
* Repository conventions
* Monorepo vs. split repositories
* GitHub governance
* Security defaults
* Engineering standards
* CI/CD
* Documentation
* AI-assisted development
* Future engineering automation

However, it is too broad to remain a canonical GitHub configuration document.

Useful parts should eventually be distributed into:

relvanta/.github
        +
relvanta-standards
        +
individual project repositories

The original document should remain archived as historical planning material.

⸻

12. ide-1.md

Classification

ARCHIVE → Extract ideas

This document contains valuable product and technical ideas, including:

* GitHub Actions generation
* Documentation generation
* Technical debt analysis
* Infrastructure drift detection
* Legacy-code explanation
* PR simulation
* Repository intelligence

These should not automatically become separate products.

Many are better understood as capabilities within the future Engineering Intelligence system.

The document should therefore remain historical until the ideas are deliberately promoted.

⸻

13. todo.md

Classification

RETIRE → Replace

Despite its name, this is not really a TODO list.

It is an early product-strategy and capability document.

Its content overlaps heavily with ide-1.md and the Engineering Intelligence concept.

Therefore:

todo.md
   ↓
extract useful ideas
   ↓
future ideas/research system
   ↓
retire TODO.md

It should not become a permanent project-management document.

Actual tasks should eventually live in the appropriate project issue tracker or project-management system.

⸻

14. README.md in OLD_TEMP

Classification

ARCHIVE → Preserve as historical context

The document represents earlier thinking about the overall system and overlaps with other early planning documents.

It should not become a canonical architecture or strategy document merely because it was originally written as a README.

Useful information should be extracted into the appropriate permanent location.

⸻

15. Dependency Between the Old Ideas

The old documents are not independent.

They form a progression:

GitHub organization standards
             ↓
Repository conventions
             ↓
Engineering standards
             ↓
AI-aware engineering standards
             ↓
Repository understanding
             ↓
Deterministic engineering tools
             ↓
AI reasoning
             ↓
Controlled engineering actions
             ↓
Engineering Intelligence

From there:

Engineering Intelligence
        │
        ├── CI/CD generation & repair
        ├── Documentation intelligence
        ├── Technical-debt analysis
        ├── Architecture review
        ├── Security review
        ├── Legacy-code understanding
        ├── Infrastructure intelligence
        └── Repository onboarding

This relationship is important because it prevents repeatedly rebuilding the same underlying infrastructure for different AI products.

⸻

16. What Should Eventually Be Deleted?

Nothing in OLD_TEMP/ should be deleted simply because it is old.

Deletion should happen only after useful information has been extracted.

Suggested eventual lifecycle:

Document	Action	Destination
setup-git.md	Archive	relvanta/.github / relvanta-standards principles
github-engineering-assistant.md	Promote	Engineering Intelligence project
ide-1.md	Archive	Ideas / Engineering Intelligence
todo.md	Retire	Issues / ideas / roadmap
README.md	Archive	Historical reference
MIGRATION_MAP.md	Temporary	Delete after migration is complete

OLD_TEMP/ itself can eventually disappear once the migration is complete.

⸻

17. Decision Rules Going Forward

When creating something new, ask:

Is it GitHub configuration?

→ .github

Is it company-wide engineering knowledge?

→ relvanta-standards

Is it implementation?

→ Project repository

Is it an unvalidated idea?

→ Ideas/research workspace

Is it an experiment?

→ Experiment/research workspace or dedicated experimental repository

Is it reusable engineering infrastructure?

→ Shared package/platform/tool repository

Is it a system that understands repositories and helps engineers reason about them?

→ Engineering Intelligence

⸻

18. The Main Principle

The purpose of this migration is not simply to clean up files.

It is to establish a separation between:

IDENTITY
   ↓
GITHUB CONVENTIONS
   ↓
ENGINEERING STANDARDS
   ↓
PROJECTS
   ↓
IDEAS / RESEARCH
   ↓
INTELLIGENT SYSTEMS

Each layer should have a clear responsibility.

The result should make it possible to evolve from a personal collection of projects into a coherent engineering ecosystem without prematurely introducing unnecessary organizational complexity.

⸻

Final Direction

For now:

1. Keep benneberg/.github small.
2. Keep OLD_TEMP/ untouched.
3. Create relvanta/.github later when the organization structure is needed.
4. Create relvanta-standards only when the standards have enough substance to justify it.
5. Preserve ideas separately from implementation.
6. Treat Engineering Intelligence as a future platform/system rather than prematurely splitting every capability into a separate product.
7. Promote mature ideas only when there is a concrete reason to implement them.

The old documents are therefore not discarded.

They become source material for the next generation of the system.
