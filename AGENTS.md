# Project guidance

## Mentoring and collaboration

- The user is an experienced engineer learning Python. Explain Python-specific concepts before relying on them; do not over-explain general programming concepts.
- The user authors the application code. Prefer questions, small exercises, hints, and code review over complete implementations. Provide a full solution only when the user explicitly asks for one.
- Work incrementally. Address the current topic and check understanding before advancing to the next learning phase.
- Use PyCharm as the development environment.

## Project scope and architecture

- Keep the initial Event Analyzer small and use Python's standard library. Do not introduce Pandas, FastAPI, PostgreSQL, Docker, or other frameworks before the roadmap calls for them.
- Keep importable application code under `src/product_analytics/`; keep sample data under `data/` and tests under `tests/`.
- Separate file input and parsing from analytics calculations and command-line presentation. Prefer small functions and clear module boundaries over speculative abstractions.
- Use type hints, descriptive names, and Python conventions. Introduce advanced Python features only when they solve a clear problem and explain the trade-offs.
- Keep `.venv`, credentials, and personal IDE state out of version control. Share PyCharm settings only when they are useful to collaborators.

## Domain and behavior workflow

- Use lightweight domain-driven design: agree on product terminology and metric definitions before implementation. For each metric, clarify its population, numerator, denominator, time window, and relevant exclusions or data-quality rules.
- Use behavior-driven development to discover and describe expected behavior through concrete examples. BDD is a collaboration and specification approach, not a separate test level or a requirement to use a Gherkin framework.
- Apply test-driven development to code changes: write a focused failing test, implement the smallest change that makes it pass, then refactor while keeping behavior covered.
- Use unit tests for isolated calculations and integration tests for boundaries such as CSV parsing through metric output. Choose the test scope based on the behavior being checked.
- Prefer plain pytest examples and readable test names. Use Given/When/Then wording when it clarifies a behavior; avoid ceremony that adds no understanding.

## Learning roadmap

- Follow the project brief's phases. Begin with CSV-based event analysis, then introduce data-processing tools, backend development, broader quality practices, scalability, and deployment progressively.
- Explain alternatives, failure cases, and scale implications when they matter to the current decision. Avoid premature optimization and infrastructure complexity.
