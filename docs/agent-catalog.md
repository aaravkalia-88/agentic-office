# Agent catalog inventory

Back to the [README](../README.md). Implementation: [manager expansion plan](../plans/office-manager.md).

Status: planned catalog, inventoried from installed source files on 2026-10-31. These are role definitions and workflows to integrate, not already running Office workers. Namespaced IDs avoid collisions. Missing tools or credentials must be shown as unavailable; catalog registration never enables external actions by itself.

## Source coverage

| Family | Inspected source | Inventory |
| --- | --- | --- |
| ECC | [affaan-m/ECC](https://github.com/affaan-m/ECC), installed plugin version 2.2.3, `agents/*.md` | All 71 definitions |
| YouTube | [Jakeschincariol/youtube-agent-skill](https://github.com/Jakeschincariol/youtube-agent-skill/tree/a2feb2104981a375ffd4f87ee04f4f5344ac43c6), `skills/*/SKILL.md` | All 11 workflows, adapted into roles |
| Engineering | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills/tree/aeac41d4d005999432bb7312f7ff06383a91d59d), `skills/*/SKILL.md` and `agents/*.md` | 25 workflow files and four personas |
| Production coordination | Installed `youtube-video-maker` and `stickman-storyteller`; [stickman-video-director](https://github.com/kaomei/stickman-video-director/tree/b568219aca9ca33992d902349004472d203c1d71) | Three companion roles |

The production source index describes 26 engineering skills, while the inspected directories contain 25. The implementation must reconcile that discrepancy against pinned files and report missing entries, without manufacturing a twenty-sixth role. Inventory tests compare source files with registered IDs rather than trusting a hard-coded total.

The summarized source descriptions retain their [third-party notices](../THIRD_PARTY_NOTICES.md). Retain source licenses/notices when importing prompts too. Record exact source revisions or content hashes in the future runtime manifest. Local coordinators need configurable local references or redistributable definitions; this inventory does not publish personal skill folders, memories, private channel data, or unlicensed course material. ECC workflows such as TDD, security review, and verification remain workflows attached to appropriate roles.

The descriptions below summarize assignment signals. Effort and risk are properties of the task, not permanently assigned to a persona. A reviewer can inspect a small diff on the free lane; a security-sensitive task still requires the appropriate data and tool policy.

## ECC agents (71)

| Role ID | Assignment signal |
| --- | --- |
| `ecc:a11y-architect` | Accessibility Architect specializing in WCAG 2.2 compliance for Web and Native platforms. Use PROACTIVELY when designing UI components, establishing design systems, or auditing code for inclusive… |
| `ecc:agent-evaluator` | Evaluates agent output against 5-axis quality rubric (accuracy, completeness, clarity, actionability, conciseness). Use after any non-trivial task when the user wants a quality assessment, or when… |
| `ecc:architect` | Software architecture specialist for system design, scalability, and technical decision-making. Use PROACTIVELY when planning new features, refactoring large systems, or making architectural… |
| `ecc:bengali-reviewer` | Reviews code handling Bengali (Bangla) text for Unicode correctness, proper normalization, script-aware processing, and internationalization best practices. |
| `ecc:build-error-resolver` | Build and TypeScript error resolution specialist. Use PROACTIVELY when build fails or type errors occur. Fixes build/type errors only with minimal diffs, no architectural edits. Focuses on getting… |
| `ecc:chief-of-staff` | Personal communication chief of staff that triages email, Slack, LINE, and Messenger. Classifies messages into 4 tiers (skip/info_only/meeting_info/action_required), generates draft replies, and… |
| `ecc:code-architect` | Designs feature architectures by analyzing existing codebase patterns and conventions, then providing implementation blueprints with concrete files, interfaces, data flow, and build order. |
| `ecc:code-explorer` | Deeply analyzes existing codebase features by tracing execution paths, mapping architecture layers, and documenting dependencies to inform new development. |
| `ecc:code-reviewer` | Expert code review specialist. Proactively reviews code for quality, security, and maintainability. Use immediately after writing or modifying code. MUST BE USED for all code changes. |
| `ecc:code-simplifier` | Simplifies and refines code for clarity, consistency, and maintainability while preserving behavior. Focus on recently modified code unless instructed otherwise. |
| `ecc:comment-analyzer` | Analyze code comments for accuracy, completeness, maintainability, and comment rot risk. |
| `ecc:commit-reviewer` | Reviews a staged diff and drafts a Conventional Commits-compliant message matching the repository's actual history norms. Use before committing, or when asked to write or check a commit message. |
| `ecc:conversation-analyzer` | Use this agent when analyzing conversation transcripts to find behaviors worth preventing with hooks. Triggered by /hookify without arguments. |
| `ecc:cpp-build-resolver` | C++ build, CMake, and compilation error resolution specialist. Fixes build errors, linker issues, and template errors with minimal changes. |
| `ecc:cpp-reviewer` | Expert C++ code reviewer specializing in memory safety, modern C++ idioms, concurrency, and performance. |
| `ecc:csharp-reviewer` | Expert C# code reviewer specializing in .NET conventions, async patterns, security, nullable reference types, and performance. |
| `ecc:dart-build-resolver` | Dart/Flutter build, analysis, and dependency error resolution specialist. Fixes dart analyze errors, Flutter compilation failures, pub dependency conflicts, and build_runner issues with minimal,… |
| `ecc:database-reviewer` | PostgreSQL database specialist for query optimization, schema design, security, and performance. Use PROACTIVELY when writing SQL, creating migrations, designing schemas, or troubleshooting… |
| `ecc:django-build-resolver` | Django/Python build, migration, and dependency error resolution specialist. Fixes pip/Poetry errors, migration conflicts, import errors, Django configuration issues, and collectstatic failures… |
| `ecc:django-reviewer` | Expert Django code reviewer specializing in ORM correctness, DRF patterns, migration safety, security misconfigurations, and production-grade Django practices. |
| `ecc:doc-updater` | Documentation and codemap specialist. Use PROACTIVELY for updating codemaps and documentation. Generates docs/CODEMAPS/*, updates READMEs and guides. Backs the /update-codemaps and /update-docs… |
| `ecc:docs-lookup` | When the user asks how to use a library, framework, or API or needs up-to-date code examples, use Context7 MCP to fetch current documentation and return answers with examples. Invoke for… |
| `ecc:e2e-runner` | End-to-end testing specialist using Vercel Agent Browser (preferred) with Playwright fallback. Use PROACTIVELY for generating, maintaining, and running E2E tests. Manages test journeys,… |
| `ecc:fastapi-reviewer` | Reviews FastAPI applications for async correctness, dependency injection, Pydantic schemas, security, OpenAPI quality, testing, and production readiness. |
| `ecc:flutter-reviewer` | Flutter and Dart code reviewer. Reviews Flutter code for widget best practices, state management patterns, Dart idioms, performance pitfalls, accessibility, and clean architecture violations.… |
| `ecc:fsharp-reviewer` | Expert F# code reviewer specializing in functional idioms, type safety, pattern matching, computation expressions, and performance. |
| `ecc:gan-evaluator` | GAN Harness — Evaluator agent. Tests the live running application via Playwright, scores against rubric, and provides actionable feedback to the Generator. |
| `ecc:gan-generator` | GAN Harness — Generator agent. Implements features according to the spec, reads evaluator feedback, and iterates until quality threshold is met. |
| `ecc:gan-planner` | GAN Harness — Planner agent. Expands a one-line prompt into a full product specification with features, sprints, evaluation criteria, and design direction. |
| `ecc:go-build-resolver` | Go build, vet, and compilation error resolution specialist. Fixes build errors, go vet issues, and linter warnings with minimal changes. |
| `ecc:go-reviewer` | Expert Go code reviewer specializing in idiomatic Go, concurrency patterns, error handling, and performance. |
| `ecc:harmonyos-app-resolver` | HarmonyOS application development expert specializing in ArkTS and ArkUI. Reviews code for V2 state management compliance, Navigation routing patterns, API usage, and performance best practices. |
| `ecc:harness-optimizer` | Improve local agent-harness configuration reliability and cost using eval-driven grading (pass@k/pass^k) derived from the eval-harness skill. |
| `ecc:healthcare-reviewer` | Reviews healthcare application code for clinical safety, CDSS accuracy, PHI compliance, and medical data integrity. Specialized for EMR/EHR, clinical decision support, and health information systems. |
| `ecc:homelab-architect` | Designs home and small-lab network plans from hardware inventory, goals, and operator experience level, with safe staged changes and rollback guidance. |
| `ecc:java-build-resolver` | Java/Maven/Gradle build, compilation, and dependency error resolution specialist. Automatically detects Spring Boot or Quarkus and applies framework-specific fixes. Fixes build errors, Java… |
| `ecc:java-reviewer` | Expert Java code reviewer for Spring Boot and Quarkus projects. Automatically detects the framework and applies the appropriate review rules. Covers layered architecture, JPA/Panache, MongoDB,… |
| `ecc:kotlin-build-resolver` | Kotlin/Gradle build, compilation, and dependency error resolution specialist. Fixes build errors, Kotlin compiler errors, and Gradle issues with minimal changes. |
| `ecc:kotlin-reviewer` | Kotlin and Android/KMP code reviewer. Reviews Kotlin code for idiomatic patterns, coroutine safety, Compose best practices, clean architecture violations, and common Android pitfalls. |
| `ecc:loop-operator` | Operate autonomous agent loops, monitor progress, and intervene safely when loops stall. |
| `ecc:marketing-agent` | Marketing strategist and copywriter for campaign planning, audience research, positioning, copy creation, and content review. Covers landing pages, email sequences, social posts, ad copy,… |
| `ecc:mle-reviewer` | Production machine-learning engineering reviewer for data contracts, feature pipelines, training reproducibility, offline/online evaluation, model serving, monitoring, and rollback. |
| `ecc:network-architect` | Designs enterprise or multi-site network architecture from requirements, using existing network skills for focused routing, validation, automation, and troubleshooting detail. |
| `ecc:network-config-reviewer` | Reviews router and switch configurations for security, correctness, stale references, risky change-window commands, and missing operational guardrails. |
| `ecc:network-troubleshooter` | Diagnoses network connectivity, routing, DNS, interface, and policy symptoms with a read-only OSI-layer workflow and evidence-backed root cause summary. |
| `ecc:opensource-forker` | Fork any project for open-sourcing. Copies files, strips secrets and credentials (20+ patterns), replaces internal references with placeholders, generates .env.example, and cleans git history.… |
| `ecc:opensource-packager` | Generate complete open-source packaging for a sanitized project. Produces CLAUDE.md, setup.sh, README.md, LICENSE, CONTRIBUTING.md, and GitHub issue templates. Makes any repo immediately usable… |
| `ecc:opensource-sanitizer` | Verify an open-source fork is fully sanitized before release. Scans for leaked secrets, PII, internal references, and dangerous files using 20+ regex patterns. Generates a… |
| `ecc:performance-optimizer` | Performance analysis and optimization specialist. Use PROACTIVELY for identifying bottlenecks, optimizing slow code, reducing bundle sizes, and improving runtime performance. Profiling, memory… |
| `ecc:php-reviewer` | Expert PHP code reviewer specializing in PSR-12 compliance, PHP type system, Eloquent ORM patterns, security, and performance. |
| `ecc:planner` | Expert planning specialist for complex features and refactoring. Use PROACTIVELY when users request feature implementation, architectural changes, or complex refactoring. Automatically activated… |
| `ecc:pr-test-analyzer` | Review pull request test coverage quality and completeness, with emphasis on behavioral coverage and real bug prevention. |
| `ecc:python-reviewer` | Expert Python code reviewer specializing in PEP 8 compliance, Pythonic idioms, type hints, security, and performance. |
| `ecc:pytorch-build-resolver` | PyTorch runtime, CUDA, and training error resolution specialist. Fixes tensor shape mismatches, device errors, gradient issues, DataLoader problems, and mixed precision failures with minimal changes. |
| `ecc:rag-pipeline-reviewer` | Reviews RAG (Retrieval-Augmented Generation) pipelines for retrieval quality, chunking strategy, embedding choices, and evaluation coverage. Invoke when the user builds, modifies, or debugs a RAG… |
| `ecc:react-build-resolver` | Diagnose and fix React build failures across Vite, webpack, Next.js, CRA, Parcel, esbuild, and Bun. Handles JSX/TSX compile errors, hydration mismatches, server/client component boundary failures,… |
| `ecc:react-reviewer` | Expert React/JSX code reviewer specializing in hook correctness, render performance, server/client component boundaries, accessibility, and React-specific security. |
| `ecc:refactor-cleaner` | Dead code cleanup and consolidation specialist. Use PROACTIVELY for removing unused code, duplicates, and refactoring. Runs analysis tools (knip, depcheck, ts-prune) to identify dead code and… |
| `ecc:ruby-reviewer` | Expert Ruby and Rails code reviewer specializing in idiomatic Ruby, Active Record query safety, Rails security defaults, and RSpec/Minitest quality. |
| `ecc:rust-build-resolver` | Rust build, compilation, and dependency error resolution specialist. Fixes cargo build errors, borrow checker issues, and Cargo.toml problems with minimal changes. |
| `ecc:rust-reviewer` | Expert Rust code reviewer specializing in ownership, lifetimes, error handling, unsafe usage, and idiomatic patterns. |
| `ecc:security-reviewer` | Security vulnerability detection and remediation specialist. Use PROACTIVELY after writing code that handles user input, authentication, API endpoints, or sensitive data. Flags secrets, SSRF,… |
| `ecc:seo-specialist` | SEO specialist for technical SEO audits, on-page optimization, structured data, Core Web Vitals, and content/keyword mapping. |
| `ecc:silent-failure-hunter` | Review code for silent failures, swallowed errors, bad fallbacks, and missing error propagation. |
| `ecc:spec-miner` | Extracts behavioral specs from existing codebases for OpenSpec. Produces flat Requirement and Invariant blocks with structured metadata (entities, enforced, id, test anchors). Outputs… |
| `ecc:swift-build-resolver` | Swift/Xcode build, compilation, and dependency error resolution specialist. Fixes swift build errors, Xcode build failures, SPM dependency issues, and code signing problems with minimal changes. |
| `ecc:swift-reviewer` | Expert Swift code reviewer specializing in protocol-oriented design, value semantics, ARC memory management, Swift Concurrency, and idiomatic patterns. |
| `ecc:tdd-guide` | Test-Driven Development specialist enforcing write-tests-first methodology. Use PROACTIVELY when writing new features, fixing bugs, or refactoring code. Ensures 80%+ test coverage. |
| `ecc:type-design-analyzer` | Analyze type design for encapsulation, invariant expression, usefulness, and enforcement. |
| `ecc:typescript-reviewer` | Expert TypeScript/JavaScript code reviewer specializing in type safety, async correctness, Node/web security, and idiomatic patterns. |
| `ecc:vue-reviewer` | Expert Vue.js code reviewer specializing in Composition API correctness, reactivity pitfalls, component architecture, template security, and Vue-specific performance. |

## YouTube roles (11)

| Role ID | Assignment signal |
| --- | --- |
| `yt:audit` | Audit a YouTube channel end to end - packaging, consistency, the first fifteen seconds, and what to fix first. |
| `yt:chapters` | Write YouTube chapters from a transcript, validated against YouTube's own rules so they actually render. |
| `yt:comment` | Draft replies to YouTube comments in the creator's voice, triaged by which ones are worth answering. |
| `yt:edit` | Turn a raw recording's transcript into an edit decision list - dead air, filler cues and retakes, with timecodes. |
| `yt:package` | Write and lint the title and thumbnail for a YouTube video as one pairing, checking truncation, duplication and vagueness before publish. |
| `yt:plan` | Plan a week or a month of YouTube uploads - what to post, when, and in what order, sized to the creator's actual capacity. |
| `yt:retention` | Read a YouTube Studio audience-retention export and find where viewers actually leave, then say what to change. |
| `yt:script` | Write a YouTube video script from a raw idea - hook options off 21 formulas, scored, then the full spoken script with the retention beats marked. Use whenever the user wants a video script, a… |
| `yt:seo` | Write the description, tags and search-facing text for a YouTube video, aimed at the query a real person types. |
| `yt:shorts` | Find the Shorts hiding inside a long video and write them, using the transcript to pick self-contained moments. |
| `yt:viral` | Find what is actually working in the user's niche on YouTube and rank it by how far each video beat its own channel, then name the formula. |

## Engineering workflows (25)

| Role ID | Assignment signal |
| --- | --- |
| `engineering:api-and-interface-design` | Guides stable API and interface design. |
| `engineering:browser-testing-with-devtools` | Tests in real browsers via Chrome DevTools MCP. |
| `engineering:ci-cd-and-automation` | Automates CI/CD pipeline setup. |
| `engineering:code-review-and-quality` | Conducts multi-axis code review. Use before merging any change. |
| `engineering:code-simplification` | Simplifies code for clarity. |
| `engineering:constraint-driven-development` | Establishes a project's quality bar as a written contract and stops agents quietly lowering it. Interviews the user on which dimensions matter, supplies sane default thresholds when they have no… |
| `engineering:context-engineering` | Optimizes agent context setup. |
| `engineering:debugging-and-error-recovery` | Guides systematic root-cause debugging. |
| `engineering:deprecation-and-migration` | Manages deprecation and migration. |
| `engineering:documentation-and-adrs` | Records decisions and documentation. |
| `engineering:doubt-driven-development` | Subjects every non-trivial decision to a fresh-context adversarial review before it stands. |
| `engineering:frontend-ui-engineering` | Builds production-quality, accessible, responsive user-facing UIs. |
| `engineering:git-workflow-and-versioning` | Structures git workflow practices. |
| `engineering:idea-refine` | Refines raw ideas into sharp, actionable concepts through structured divergent and convergent thinking. |
| `engineering:incremental-implementation` | Delivers changes incrementally in thin, verifiable slices. |
| `engineering:interview-me` | Extracts what the user actually wants instead of what they think they should want. Achieves this through one-question-at-a-time interview until ~95% confidence about the underlying intent. |
| `engineering:observability-and-instrumentation` | Instruments code so production behavior is visible and diagnosable. |
| `engineering:performance-optimization` | Optimizes application performance across frontend, backend, queries, and databases. |
| `engineering:planning-and-task-breakdown` | Breaks work into ordered tasks. |
| `engineering:security-and-hardening` | Hardens code against vulnerabilities. |
| `engineering:shipping-and-launch` | Prepares production launches. |
| `engineering:source-driven-development` | Grounds every implementation decision in official documentation. |
| `engineering:spec-driven-development` | Creates specs before coding. |
| `engineering:test-driven-development` | Drives development with tests using the red-green-refactor loop. |
| `engineering:using-agent-skills` | Discovers and invokes agent skills. |

## Engineering personas (4)

| Role ID | Assignment signal |
| --- | --- |
| `engineering-persona:code-reviewer` | Senior code reviewer that evaluates changes across five dimensions — correctness, readability, architecture, security, and performance. |
| `engineering-persona:security-auditor` | Security engineer focused on vulnerability detection, threat modeling, and secure coding practices. |
| `engineering-persona:test-engineer` | QA engineer specialized in test strategy, test writing, and coverage analysis. |
| `engineering-persona:web-performance-auditor` | Web performance engineer focused on Core Web Vitals, loading, rendering, and network optimization. |

## Production coordinators (3)

| Role ID | Assignment signal |
| --- | --- |
| `production:youtube-video-maker` | Coordinates a resumable research-to-edit-to-packaging workflow and tracks artifact handoffs. |
| `production:stickman-storyteller` | Owns original story, storyboard, host continuity, scene timing, and animation handoff. |
| `production:directing-stickman-videos` | Produces renderable scene direction and applies the selected visual grammar and production checks. |

## Assignment examples

| Task | Candidate specialist | Execution rule |
| --- | --- | --- |
| Summarize a public issue and label it | `ecc:code-explorer` or an appropriate project role | OpenRouter free-only for a bounded low-effort task. |
| Draft chapters from a final transcript | `yt:chapters` | OpenRouter free-only; verify timestamps against the final cut. |
| Diagnose an architectural regression | `ecc:architect` with `engineering:debugging-and-error-recovery` | A capable configured runtime, with verified reproduction and a budget. |
| Review a small TypeScript change | `ecc:typescript-reviewer` or `engineering-persona:code-reviewer` | Choose by complexity, risk, and tools; do not allocate a paid model solely from the role name. |
| Repair a low-effort code defect | `ecc:build-error-resolver` or language specialist | Free-only model with scoped worktree tools; block until those tools exist. |
| Analyze retention | `yt:retention` | Require actual analytics; missing inputs block analysis. |

ECC's `chief-of-staff` is a communications specialist. The office manager is a separate service that owns scheduling and verification. Neither catalog membership nor a manager plan authorizes sending messages, publishing videos, buying generation, or running arbitrary source hooks.
