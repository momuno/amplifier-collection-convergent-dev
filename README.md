# Convergent Development Collection

> Transform divergent exploration into focused implementation through systematic workflows

---

## What This Provides

The **Convergent Development** collection equips Amplifier with a complete development workflow from ideation to implementation:

- **9 specialized workflow agents** - Each expert in their phase
- **4 core workflows** - Convergence, Sprint Planning, TDD Implementation, Issue Tracking
- **Complete methodology documentation** - Process guides and best practices
- **Command templates** - Reference implementations for workflow steps

### The Philosophy

Convergent development acknowledges that great software emerges from:

1. **Divergent exploration** - Freely exploring all possibilities
2. **Thoughtful convergence** - Identifying the focused scope
3. **Systematic deferrals** - Preserving ideas for future iterations
4. **Value-first implementation** - Delivering working software with learning early
5. **Continuous iteration** - Feeding learnings back into the next cycle

```
Diverge broadly → Converge ruthlessly → Implement systematically → Learn continuously
```

---

## Quick Start

### Installation

```bash
# Install the collection (requires foundation collection)
amplifier collection add git+https://github.com/momuno/amplifier-collection-convergent-dev@main

# Verify installation
amplifier collection show convergent-dev
```

### Usage

```bash
# Use the convergent-dev profile
amplifier profile use convergent-dev:convergent-dev

# Start convergence on a new idea
amplifier run "I want to build a documentation evergreen system that keeps docs up-to-date"

# The convergence-architect will guide you through:
# 1. DIVERGE - Explore all possibilities
# 2. CAPTURE - Organize ideas systematically
# 3. CONVERGE - Identify 3-5 core features
# 4. DEFER - Preserve remaining ideas for future
```

---

## The Four Core Workflows

### 1. Convergence: Ideation to Feature Scope

**Purpose**: Transform divergent exploration into a focused feature scope with everything else thoughtfully deferred.

**Agent**: `convergence-architect`

**Phases**:
```
💡 Idea → 🌟 DIVERGE → 📋 CAPTURE → 🎯 CONVERGE → 💾 DEFER → 📄 Feature Scope
```

**Outputs**:
- `FEATURE_SCOPE.md` - The 3-5 features to implement
- `DEFERRED_FEATURES.md` - All other ideas preserved for future
- `CONVERGENCE_COMPLETE.md` - Summary of convergence process
- Tracks all deferred features in beads

**When to use**: Starting new projects, defining features, scope reduction

**Example**:
```bash
amplifier run "I have an idea for a doc-evergreen tool"
# Explores 23 features
# Converges to 3-5 core features
# Defers 18-20 features to v2+
```

### 2. Sprint Planning: Feature Scope to Executable Sprints

**Purpose**: Break down feature scope into value-first sprints with realistic timelines.

**Agent**: `sprint-planner`

**Key Principles**:
- Vertical slices (end-to-end functionality)
- Value-first ordering (deliver learning early)
- Realistic timelines (based on complexity)
- Clear deliverables per sprint

**Outputs**:
- `SPRINT_PLAN.md` - Overview of all sprints
- `SPRINT_0X_[NAME].md` - Detailed plan per sprint

**When to use**: After feature scope convergence, before implementation

**Example**:
```bash
amplifier run "Create sprint plan for the feature scope in ai_working/convergence/..."
# Breaks into 4 sprints
# Sprint 1: Proof of concept (3 days)
# Sprint 2: Review workflow (2 days)
# Sprint 3: CLI + templates (3 days)
# Sprint 4: Context control (2 days)
```

### 3. TDD Implementation: Sprint to Working Software

**Purpose**: Implement sprint features using Test-Driven Development with coordinated agents.

**Agent**: `tdd-specialist` (orchestrates `zen-architect`, `modular-builder`)

**The TDD Cycle**:
```
🔴 RED → 🟢 GREEN → 🔵 REFACTOR → Commit → Repeat
```

**Agent Coordination**:
- Simple tests → `modular-builder` directly
- Complex tests → `zen-architect` (design) → `modular-builder` (implement)
- Orchestrator decides based on test scope

**When to use**: Implementing each sprint from the sprint plan

**Example**:
```bash
amplifier run "Implement sprint 1 using TDD cycle"
# 🔴 Write failing test for proof of concept
# 🟢 Minimal code to pass test
# 🔵 Refactor for quality
# ✅ Commit on green
```

### 4. Issue Tracking: Systematic Issue Capture

**Purpose**: Systematically capture, investigate, and track issues from user feedback.

**Agent**: `issue-capturer` (orchestrates `bug-hunter` for complex investigations)

**The Five Modes**:
```
📥 CAPTURE → 🔍 INVESTIGATE → 📝 DOCUMENT → 🔗 INTEGRATE → 📊 SUMMARIZE
```

**Outputs**:
- Issues tracked by beads
- Issues include investigation details
- Feeds into next convergence/sprint cycle

**When to use**: After testing, gathering feedback, before next iteration

**Example**:
```bash
amplifier run "Capture and investigate issues from user feedback"
# Parses free-form feedback
# Investigates root causes (delegates to bug-hunter)
# Documents persistently
# Feeds into next sprint planning
```

---

## Available Agents

### Workflow Orchestrators (4 agents)

| Agent                      | Purpose                                  | Keywords                      |
| -------------------------- | ---------------------------------------- | ----------------------------- |
| **convergence-architect**  | Transform exploration into focused scope | converge, diverge, defer      |
| **sprint-planner**         | Break scope into executable sprints      | sprint, plan, timeline        |
| **tdd-specialist**         | Orchestrate TDD cycle                    | tdd, test, red-green-refactor |
| **issue-capturer**         | Systematically track issues              | issue, bug, feedback          |

### Implementation & Architecture (3 agents)

| Agent               | Purpose                                    | Keywords                         |
| ------------------- | ------------------------------------------ | -------------------------------- |
| **zen-architect**   | Planning and architecture with simplicity  | architecture, design, plan       |
| **modular-builder** | Module implementation with regeneration    | implement, build, module         |
| **bug-hunter**      | Hypothesis-driven debugging                | debug, investigate, fix          |

### Cleanup & Maintenance (2 agents)

| Agent                   | Purpose                         | Keywords              |
| ----------------------- | ------------------------------- | --------------------- |
| **post-task-cleanup**   | Codebase hygiene after tasks    | cleanup, hygiene      |
| **post-sprint-cleanup** | Sprint completion cleanup       | sprint-done, finalize |

---

## Real-World Example: doc-evergreen

**Starting Point**: "I want a tool to keep documentation up-to-date"

### Step 1: Convergence (3 days)
```bash
amplifier profile use convergent-dev:convergent-dev
amplifier run "I want a doc-evergreen tool"

# Results:
# - Explored 23 potential features
# - Converged to 3 core features:
#   1. Review stale docs
#   2. Generate update suggestions
#   3. Simple CLI interface
# - Deferred 20 features to v2+
# Output: FEATURE_SCOPE.md + DEFERRED_FEATURES.md
```

### Step 2: Sprint Planning (1 day)
```bash
amplifier run "Create sprint plan for doc-evergreen feature scope"

# Results:
# - Sprint 1: Proof of concept (3 days)
# - Sprint 2: Review workflow (2 days)
# - Sprint 3: CLI + templates (3 days)
# - Sprint 4: Context control (2 days)
# Output: 5 sprint plan documents
```

### Step 3: TDD Implementation (10 days)
```bash
amplifier run "Implement sprint 1 using TDD"

# Results:
# - Tests written first for each feature
# - Minimal code to pass tests
# - Refactored for quality
# - Output: Working proof of concept v0.1.0
```

### Step 4: Issue Tracking (ongoing)
```bash
amplifier run "Capture issues from testing sprint 1"

# Results:
# - Captured 5 issues from user testing
# - Investigated 2 complex bugs with bug-hunter
# - Documented all in beads
# - Fed into sprint 2 planning
```

**Total Time**: 2 weeks from idea to working v0.1.0 with all deferred ideas preserved

---

## Philosophy Alignment

The convergent-dev collection follows Amplifier's core principles:

### Ruthless Simplicity
- Start minimal, grow as needed
- Avoid future-proofing
- Question every abstraction
- Defer ruthlessly

### Value-First Delivery
- Vertical slices over horizontal layers
- Working software over comprehensive documentation
- Learning-driven over plan-driven
- Ship early, learn fast

### Test-Driven Development
- Tests define requirements
- Red-green-refactor cycle
- Tests are honest gatekeepers
- Refactor with test protection

### Trust in Emergence
- Don't design everything upfront
- Let patterns emerge through use
- Complexity justifies itself through need
- Modular design ("bricks and studs")

---

## Context Documentation

### Workflows
- `context/workflows/README.md` - Complete workflow overview
- `context/workflows/CONVERGENCE_PROCESS.md` - Convergence methodology
- `context/workflows/SPRINT_PLANNING.md` - Sprint planning guide
- `context/workflows/TDD_CYCLE.md` - TDD implementation workflow
- `context/workflows/ISSUE_CAPTURE.md` - Issue tracking process

### Command Templates
- `context/commands/1-converge.md` - Convergence command reference
- `context/commands/2-plan-sprints.md` - Sprint planning reference
- `context/commands/3-tdd-cycle.md` - TDD cycle reference
- `context/commands/4-capture-issues.md` - Issue capture reference
- `context/commands/status.md` - Status check reference

---

## Tips for Success

### During Convergence
- ✅ Explore freely without self-censoring
- ✅ Document everything (nothing is lost)
- ✅ Be ruthless about feature scope (3-5 features max)
- ✅ Trust that deferred ≠ deleted

### During Sprint Planning
- ✅ Prioritize learning over features
- ✅ Vertical slices that work end-to-end
- ✅ Realistic estimates (don't over-commit)
- ✅ Clear acceptance criteria per sprint

### During TDD Implementation
- ✅ Write the test first (always!)
- ✅ Test behavior, not implementation
- ✅ Minimal code to pass (resist over-engineering)
- ✅ Refactor with test protection
- ✅ Commit on green tests

### During Issue Tracking
- ✅ Capture systematically from all sources
- ✅ Investigate thoroughly (delegate to bug-hunter)
- ✅ Document persistently
- ✅ Feed into next convergence/sprint cycle

---

## Dependencies

- **foundation** collection (^1.0.0) - Required for base profiles and shared context

---

## Contributing

> [!NOTE]
> This project is not currently accepting external contributions, but we're actively working toward opening this up. We value community input and look forward to collaborating in the future. For now, feel free to fork and experiment!

Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit [Contributor License Agreements](https://cla.opensource.microsoft.com).

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft
trademarks or logos is subject to and must follow
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
