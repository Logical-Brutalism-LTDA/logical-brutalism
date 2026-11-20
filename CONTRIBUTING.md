# Contributing to Logical Brutalism

Logical Brutalism is a parametric, server-driven UI architecture engineered for high-density B2B software. Contributions are evaluated strictly on measurable engineering criteria: information density, runtime performance, and accessibility.

---

## 01 // Engineering Constraints

Before opening an issue or Pull Request, verify that your proposal adheres to the system's core constraints:

1. **Function Over Aesthetics:** Every change must address a concrete defect or measurable improvement—reducing cognitive load, lowering bundle footprint/mount latency, or fixing accessibility issues (Axiom I). Subjective styling changes ("looks cleaner") will be closed.
2. **Geometric Strictness:** Maintain hard 90-degree edges. Do not introduce `border-radius`, decorative drop shadows, or non-functional transitions outside explicitly documented exceptions (P-02).
3. **WCAG AAA Contrast Parity:** All UI primitives and token modifications must maintain WCAG AAA contrast compliance across both **Infinity-White** and **Void-First** themes.
4. **Zero Virtual DOM Tax:** Contributions must remain compatible with the core server-driven stack—**semantic HTML, Tailwind CSS, HTMX, and Alpine.js** (integrating cleanly with server-rendered backends such as FastAPI and Django). Heavy client-side runtimes or Virtual DOM dependencies are out of scope.
5. **Empirical Integrity (Benchmarks):** Any changes to benchmark harnesses or test applications must remain 100% reproducible, free of mocks, and free of artificial delays (`setTimeout` hacks).
6. **Objective Documentation:** Keep docs, comments, and PR descriptions dry, concise, and technically precise. Avoid marketing language or conversational filler.

---

## 02 // Local Development Setup

1. Fork the repository and clone your fork locally:

```bash
git clone https://github.com/<your-username>/logical-brutalism.git
cd logical-brutalism
```

2. Create a dedicated branch for your work:

```bash
git checkout -b feat/compact-data-table
```

3. Install dependencies according to the subsystem you are modifying:

```bash
# Python / FastAPI / CLI tooling (via uv)
uv sync

# Node.js / Tailwind CSS / Frontend assets
npm install
npm run build
```

4. Verify that builds pass cleanly without regressions before committing.

---

## 03 // Commit & Pull Request Workflow

### Commit Convention

Use concise [Conventional Commits](https://www.conventionalcommits.org/) aligned with the organization's taxonomy:

| Prefix | Scope |
| :--- | :--- |
| `feat:` | New UI primitive, CLI capability, or core feature |
| `fix:` | Bug fix, layout regression, or contrast correction |
| `spec:` | Changes to axioms, generative principles, or design tokens |
| `bench:` | Playwright harness updates, build pipelines, or raw audit logs |
| `docs:` | Living Spec updates, READMEs, or `llms.txt` parity |
| `refactor:` | Internal optimization with zero behavioral change |

Example: `fix(core-css): enforce AAA contrast ratio on Void-First table headers`

### Submitting a Pull Request

1. Reference the related issue (e.g., `Closes #42`).
2. State the functional or measurable impact of the change (bundle delta, latency delta, or contrast ratio where applicable).
3. Update relevant documentation and `llms.txt` if public primitives, CLI commands, or spec rules changed.
4. Complete the Pull Request template checklist.

---

## 04 // Licensing & Attribution

Logical Brutalism separates source code licensing from specification licensing to ensure both frictionless software adoption and proper academic/authorship attribution:

- **Source Code (`MIT License`):** All code, CSS primitives, CLI scripts, and benchmark harnesses are released under the MIT License. You may use, modify, and distribute them commercially while retaining the original copyright notice.
- **Specification & Methodology (`CC BY 4.0`):** The theoretical framework—including the **3 Axioms**, the **7 Generative Principles**, and the canonical Living Spec documentation—is licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/). Derivative systems, academic papers, or adaptations based on this specification must provide clear attribution to **Matheus Lacerda Ferreira** with a link to [logicalbrutalism.matheuslacerda.dev](https://logicalbrutalism.matheuslacerda.dev).

---

**Maintainer:** Matheus Lacerda Ferreira ([matheuslacerda.dev](https://matheuslacerda.dev))
