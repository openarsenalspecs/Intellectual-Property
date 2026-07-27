# LicenseTrace

LicenseTrace is a semantic software provenance and build constraint system that enforces origin-first software construction. It determines whether software already exists before any code is written, resolves attribution across ecosystems, detects duplication at both repository and module level, and compiles a minimal executable specification only when no sufficient existing implementation can be reused.

At its core, LicenseTrace treats software not as something to be freely duplicated, but as something that must be traced, attributed, and validated before execution.

**No origin. No build.**

---

## Core Principles

- Every system must have a verifiable origin before it can be built.
- Reuse is preferred over creation.
- Duplication is eliminated at both ecosystem and internal spec levels.
- Attribution is mandatory and preserved across all transformations.
- Specifications are compiled before code is generated.
- Nothing is executed without provenance validation.

---

## Feature List

### 1. Specification Module (Core Gate)
- Converts human intent into a semantic build specification
- Determines whether a system already exists
- Outputs:
  - EXISTS_AS_IS
  - EXTEND_EXISTING
  - PARTIALLY_EXISTS
  - DOES_NOT_EXIST

---

### 2. Semantic Equivalence Detection
- Detects functional similarity beyond keywords
- Matches behavior, architecture, and intent
- Identifies duplicate systems across ecosystems

---

### 3. Ecosystem Scan Engine
Searches across:
- GitHub
- GitLab
- Package registries (npm, PyPI, crates.io, Go modules, Maven, etc.)
- Internal repositories
- :contentReference[oaicite:0]{index=0}

Codeberg is prioritized for:
- AGPL-licensed projects
- Minimal implementations
- Self-hosted software
- Privacy-first tooling

---

### 4. Structural Similarity Engine
- Compares dependency graphs
- Compares system architecture
- Detects partial overlaps and reusable components

---

### 5. License + Reuse Viability Engine
- Evaluates legal compatibility (AGPL, GPL, MIT, Apache, proprietary)
- Detects copyleft propagation risks
- Validates redistribution constraints

---

### 6. Intra-Spec Duplication Detection
- Detects duplicate modules within the same specification
- Prevents redundant abstraction layers
- Enforces single-source-of-truth module design

---

### 7. Origin Resolution System
- Assigns origin based on earliest verifiable timestamp
- Supports:
  - commit timestamps
  - release dates
  - package publication dates
- Handles conflicting origin claims with confidence scoring

---

### 8. Attribution Graph Engine
- Builds full provenance lineage graph
- Tracks:
  - derived_from relationships
  - extended_from relationships
  - reused_as_is components
- Preserves full credit chain across transformations

---

### 9. Legal Risk Layer
- Evaluates licensing and redistribution risk
- Detects AGPL/GPL copyleft exposure
- Blocks builds with unacceptable legal risk

---

### 10. Execution Simulation Mode
- Simulates compiled specification before execution
- Detects:
  - dead modules
  - unreachable logic paths
  - redundant dependencies
  - structural inefficiencies

---

### 11. Spec Compiler Mode
- Compiles full specification into a minimal executable graph
- Eliminates redundant modules
- Collapses semantic duplicates
- Produces canonical system representation

---

### 12. Zero-Waste Build Engine
- Prevents new code generation when reuse is possible
- Prioritizes configuration and composition over implementation
- Enforces minimal line and dependency generation

---

### 13. Human-in-the-Loop Validation
- Requires explicit confirmation before build execution
- Displays reuse candidates when available
- Blocks execution until provenance is confirmed

---

### 14. Dual Citation Requirement
All external references must include:
- Structured citation (system reference)
- Raw URL (verifiable source link)

---

### 15. File System Canonical Rules
All system-generated metadata files must be lowercase:
- notice.md
- license
- readme.md
- contributing.md

---

## System Philosophy

LicenseTrace operates on a strict rule:

> Software must be traced before it is built, and attributed before it is executed.

It enforces a world where duplication is not assumed, creation is conditional, and provenance is always preserved.

---

## Specification Branding License (SBL)
### Standard
- Fully AGPL-3.0+ compliant system
- Copyleft enforced for network deployments
- Required attribution:
  - Roxanne Ardary
  - https://www.roxanneardary.com/

### Optional

- **Specification Branding License (SBL)**
  - Attribution-free commercial deployment
  - Pricing based on scale, usage, and deployment scope
  - [https://roxanneardary.com/licensetrace/](https://roxanneardary.com/licensetrace/)

---

## License & Notice Requirements

LicenseTrace is released under the **GNU Affero General Public License v3.0 or later (AGPL-3.0+)**.   
By contributing to this project, you agree that your contributions will also be released under this license.

Please note the following:

- All contributions must comply with the **AGPL-3.0+** terms.  
- Under **Section 7** of the license, all redistributions, forks, and derivative works must preserve attribution to:  
  **Roxanne Ardary** and **[roxanneardary.com](https://www.roxanneardary.com/)**.  
- LicenseTrace specificiations are free to use with attribution. A Specification Branding License can be negotiated upon request.
- The project's **notice.md** file tracks attribution requirements, provenance, and contributor acknowledgments across all derived and reused components. Any update that adds new contributors, external sources, or derived code must also update `notice.md`.
- All systems integrating or extending LicenseTrace must preserve origin tracking metadata and maintain full attribution continuity across modules, dependencies, and forks.
- When submitting a pull request, ensure that any new files maintain the required attribution and do not introduce untracked or unattributed external code.
- Network-deployed versions of this software must remain fully AGPL-3.0+ compliant, including exposure of source code modifications where required under the license and preservation of provenance traceability.
- No module may be added to the system without a resolvable origin record or explicit attribution path.

For full legal details, please refer to the AGPL-3.0+ license and the project's `notice.md` file.
