# 2 Technological Constraints

<!-- TOC -->

- [Technological Constraints](#technological-constraints)
- [Solution Content](#solution-content)

<!-- /TOC -->

At the moment of the design of the solution the following constraints were considered:

1. System should run on current Jenkins Implementations
2. Code should be stored in GitHub and releases should be administrated and generated there.
3. Only automated users/app should be able directly update stable
4. Regression Tests includes Unit Test
5. Functional Tests have it’s own repository and pipeline
6. Regression Tests can’t be applied to date generation libraries at the moment due that the stacktrace should be unique and independent.

<!-- CONTENTTABLE:START -->
# Solution Content

1. [Introduction and Goals](01-introduction-and-goals.md)
2. [Technical Constraints](02-technical-constraints.md)
3. [System Context and Scope](03-system-context-and-scope.md)
4. [Building Block View](04-building-block-view.md)
5. [Runtime Overview](05-RuntimeOverview.md)
6. [Design Decisions](06-design-decisions.md)
7. [Technical Risks](07-technical-risks.md)
8. [Results](08-Results.md)
<!-- CONTENTTABLE:END -->
