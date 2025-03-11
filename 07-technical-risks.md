# 7 Technical Risks
<!-- TOC -->

- [7 Technical Risks](#7-technical-risks)

<!-- /TOC -->

| Risk/Debt | Description | Mitigation/Additional Info |  |
|:---:|:---:|:---:|---|
| Fast Forward Features  | A fast forward feature is a feat that needs to go to stable due a business decision and should not wait for validation time. This may cause stability issues  | The fast forward features ARE always manual so the risk is assumed and measured. The Engineer should assure that prerelease has the feature as well to avoid issues after force update |  |
| Functional Test must be modular | At the moment the functional testing is capable to execute the whole set of tests instead of a modular solution that execute the affected libraries of a change. This imply that the functional test might take some time to be executed which imply a performance issue | Tech Debt to be implemented |  |
| Migration between Jenkins | Migration of the solution between Jenkins imply that the functional and jsl pipelines need to be on same server to eb able to run the full solution. If not the JSL pipeline and release generation may fail | Consider migration of all impacted jobs when it is required. |  |
| Dated Regression Tests | Dated regression Tests  |  |  |
| Long Term Reverts | In case a revert is required after a feature was introduced to stable, the revert operation might be complex | To create a new fix or feat PR depending in the context that will go to the stable after merge. |  |

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