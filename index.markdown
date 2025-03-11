<p align="center">
  <a href="" rel="noopener">

<img src="./assets/banner.webp" alt="GiHub"></a>


</p>

<h3 align="center">CI/CD Shared Libraries Release Management Automation</h3>
<div align="center">
  <code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/git.png" alt="Git" title="Git"/></code>
  <code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/github.png" alt="GitHub" title="GitHub"/></code>
  <code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/jira.png" alt="Jira" title="Jira"/></code>
  <code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/javascript.png" alt="JavaScript" title="JavaScript"/></code>
  <code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/npm.png" alt="npm" title="npm"/></code>
  <code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/groovy.png" alt="Groovy" title="Groovy"/></code>
  <code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/jenkins.png" alt="Jenkins" title="Jenkins"/></code>
</div>


# Table of Contents


<!-- TOC -->

- [Table of Contents](#table-of-contents)
- [Executive Summary](#executive-summary)
    - [🎯 Strategic Impact](#-strategic-impact)
    - [Project Context and Challenges](#project-context-and-challenges)
        - [Project Overview](#project-overview)
            - [Background](#background)
            - [DORA Devops KPI](#dora-devops-kpi)
            - [Objectives](#objectives)
            - [Solution Strategy](#solution-strategy)
    - [Requirements Overview](#requirements-overview)
    - [Quality Goals](#quality-goals)
    - [Systems Stakeholders](#systems-stakeholders)
- [Technological Constraints](#technological-constraints)
- [System Context and Scope](#system-context-and-scope)
    - [System Context Diagram](#system-context-diagram)
- [System Context and Scope](#system-context-and-scope)
    - [Withebox - Container Diagram](#withebox---container-diagram)
    - [Blackbox - Components Diagram](#blackbox---components-diagram)
            - [Code Implementation Example](#code-implementation-example)
        - [Regression Verify](#regression-verify)
            - [Code Implementation Example](#code-implementation-example)
        - [Functional Execution and Verify](#functional-execution-and-verify)
            - [Code Implementation Example](#code-implementation-example)
        - [Functional Execution](#functional-execution)
            - [Code Implementation Example](#code-implementation-example)
        - [Functional Test Configuration](#functional-test-configuration)
        - [Release Generation](#release-generation)
            - [Code Implementation Example](#code-implementation-example)
        - [Stable Preparation/Generation](#stable-preparationgeneration)
            - [Code Implementation Example](#code-implementation-example)
        - [Hotfix Generation](#hotfix-generation)
            - [Code Implementation Example](#code-implementation-example)
- [Runtime View](#runtime-view)
    - [Scenario 1 - PR](#scenario-1---pr)
    - [Scenario 2 - Standard Master Merge](#scenario-2---standard-master-merge)
    - [Scenario 3 - Stable Release Generation](#scenario-3---stable-release-generation)
- [Design Decisions](#design-decisions)
    - [Use of branch rather than tag](#use-of-branch-rather-than-tag)
    - [Conventional Commits](#conventional-commits)
    - [Reverts](#reverts)
- [Technical Risks](#technical-risks)
- [Results](#results)

<!-- /TOC -->

# Executive Summary

The **Jenkins CI/CD Shared Libraries Release Management** initiative was a strategic effort to enhance the **reliability, automation, and scalability** of CI/CD pipelines across a **large-scale DevSecOps environment**. 

The system in nature was increasingly complex with over **1,000 applications and 3,000 repositories** which where needed to be digitally transformed in order to adop industr-level standards.

As part of the Enterprise opbjective of **reducing the time to market**, it was required to integrate with the change management tools and being able to generate automated Changes. However, change management intoduced as a requirement that the libraries used need to be at least **[DORA](#dora-devops-kpi) HIGH** and be available as soon as possible tpo the applications in order to validate the change management automation.

To achieve this the team needed to **eliminate deployment inconsistencies, reduce technical debt, and streamline release processes** while ensuring compliance with DevSecOps standards.

The challeneges addressed by this initiative were:
- :no_entry_sign: **Unstable CI/CD Pipelines**
- :no_entry_sign: **Lack of Change Control**
- :no_entry_sign: **Inconsistent Release Management**
- :no_entry_sign: **Low Visibility & Observability**
- :no_entry_sign: **Technical Debt & Security Risks**


To address these challenges, I designed and implemented **a multi-layered optimization strategy** centered around **automated release management** and **high level code testing**:
- :one: Automated Release & Versioning System
    - Introduced **Conventional Commits** to enforce structured releases.
    - Implemented **automated changelog generation** to improve transparency and traceability.
    - Established **a governance model** ensuring backwards compatibility across library versions, called **STABLE RELEASE**

- :two: CI/CD Reliability Optimization
    - Integrated **preemptive validation testing** (Regression) to catch issues before publishing.
    - Introduced functional testing framework for Jenkins Shared Libraries to ensure **correctness and stability**.


- :three: Security & DevSecOps Alignment
    - Reduced **SonarQube Code Quality Issues** to meet **[DORA](#dora-devops-kpi) HIGH**  standards
    - Increase **Unit Test Coverage to 80%** and **Functional Testing to 30%**.


## Strategic Impact

<img align="right" width="300" height="300" src="./assets/happy.gif">


This initiative not only **modernized SL** but also **set a new foundation for scalable, high-reliability CI/CD practices**. By combining **automation, observability, and governance**, the project significantly improved **developer experience, operational efficiency, and release stability**.

It also provided **transformative effect** for the organization by enabling **development teams** and other important teams, such as **Change Management**, to rely on the **Jenkins Shared Libraries**—the backbone of the **CI/CD system**—accelerating the adoption of **DevSecOps standards** across the enterprise, ultimately expediting the **time-to-market** for mature applications through an **automated change management process**.

The project provided significant improvements in key metrics:

- :star2: Nearly doubled the number of onboarded repositories within six months post-adoption (**674 -> 1031**).
- :star2: Reduced the number of repositories with outdated libraries from **534 to 320**.
- :star2: Increased the number of applications achieving a **[DORA](#dora-devops-kpi) HIGH**  Performance KPI from **10 to 75**. And added 1 application framework to the **Elite category**
- :star2: Boosted test coverage to 80% and functional testing to 30%.
- :star2: Enhanced code quality in SonarQube, achieving **[DORA](#dora-devops-kpi) HIGH**  standards.

For more detailed insights, refer to the [Results](./08-Results.md) section.

##  2. <a name='ProjectContextandChallenges'></a>Project Context and Challenges
![Context](assets/context.png)

This document aim to describe a project that caused high impact over my career on one or more of the following areas:

- Infrastructure maintenance & monitoring. Cloud and on-premise.
- CI/CD & automation testing
- Runbooks and disaster recovery processes
- New UAT/DEV environment setup
- Incident tracking and analysis
- SLO monitors, alerts, and notifications
- Performance monitoring, load tests, auto-scaling
- Cloud cost optimizations
- Security

###  2.1. <a name='ProjectOverview'></a>Project Overview


This initiative was designed to **enhance trust, reliability, and adoption** of the shared libraries that serve as the **core foundation of the enterprise CI/CD system**. This project played a **crucial role in accelerating DevSecOps adoption** by ensuring development teams had **a stable and reliable** set of shared libraries, ultimately **reducing deployment risks and increasing time-to-market efficiency** for mature applications.  

The initiative was originated from an effort to automate the change management process in order to reduce the time to market of mature Applications, but as the project progressed, it diverged into two separated but interconnected streams:  

1. **CI/CD Shared Libraries Release Management Automation** (the primary focus of this document).  
2. **Automatic Change Management Process**, which later aimed to integrate with the enhanced Jenkins Shared Libraries.  

Although the ultimate objective was to seamlessly integrate CICD with the Automated Change Management process, this document primarily focuses on thefirst initiative 

> [!WARNING] 
> **Code Disclaimer** :The code presented in this project is a **simplified version** of the original implementation and is **not intended for production use**. Additionally, **all proprietary and confidential information has been removed** to comply with security and data protection policies.  


> [!WARNING] 
> **AI Ussage** : Some of the content of this documentation has been redacted or reviewed by AI to ensure that no sensitive information is shared or to simplify the content as well as summarixing pseudocode that might be copnfusing after the sensitive code removal. Tools used included OpenAI and GH Copitlot.

####  2.1.1. <a name='Background'></a>Background

In **2022**, a leading telecommunications company embarked on a massive DevSecOps transformation project, aiming to onboard **over 3,000 repositories across 1,000 applications** to adopt **DevSecOps standards**. The **Jenkins Shared Libraries team**, a group of just **five engineers**, was responsible for maintaining the **core CI/CD automation layer**.  

However, the initial project didn´t consider the increasing demmand of the development teams and ledership stakeholders and  it became clear that the **existing shared libraries management process was unsustainable**, leading to **bottlenecks, reliability issues, and slower time-to-market**

The team identified **several critical issues** that contributed to pipeline instability and slowed DevSecOps adoption:  

 - :one: Unstable Release & Versioning Management**  
    - Cherry-picking updates 
    - No centralized versioning process
    - Lack of structured Release Not, making debugging and tracking difficult for new adopters

- :two: Technical Debt & Outdated Libraries**  
    - **534 out of 674 pipelines (79%) were using outdated libraries.**  
    - **No structured process to enforce updates**,
    - **Regression issues** due to unmanaged **technical debt accumulation**.  

- :three: Insufficient Testing & Quality Control**  
    - Only 30% unit test coverag  
    -No functional testing framework** implemented.
    - **No regression testing**, making changes **risky and unpredictable**.  
    - **SonarQube reported low-quality code**, further increasing the risk of instability.  

- :four: Inefficient Change Management Process (GCR)
    - Development teams prepared a release and ensured all stories were completed.  
    - Teams manually submitted a Change Request (GCR), requiring extensive documentation.  
    - The Change Management Team reviewed the request, which could takeseveral hours.  
        - ✅ If approved, the release was scheduled.  
        - ❌ If rejected, the process restarted, delaying deployments.  
    - The development team executed the release on the scheduled date.  
    - Teams manually reported release results back into ServiceNow.  

The company recognized that automating the Change Management proces was essential to enabling DORA High/Elite-Performance development teams. However, for automation to succeed it was required that the Jenkins Shared Libraries and related core components where stable, reliable and tested enough to ensure that the applications that are using them will not be affected by the changes that are made to the libraries and also to be able to receive the latest updates as soon as possible.

At the time, Jenkins Shared Libraries **lacked the stability required to support automatic change approvals**. Specifically:

- **No automated testing**, making releases unpredictabl.  
- **Frequent critical failures**, requiring cherry-picked updates.  
- **Security patches** were not consistently adopted across teams.  

By addressing these challenges, this project played a key role in accelerating DevSecOps adoption, improving CI/CD reliability, and enabling faster, more secure software delivery.  

####  2.1.2. <a name='DORADevopsKPI'></a>DORA Devops KPI

![DORA](https://dora.dev/guides/dora-metrics-four-keys/dora-metrics-four-keys.png)

The [DORA](https://dora.dev/guides/dora-metrics-four-keys/) metrics are a set of metrics that are used to measure the performance of the development teams and the applications. Internally this was adapted as below

| KPI | Low | Medium | High | Elite |
|-----|-----|--------|------|-------|
| **Deployment Frequency** | Less than a month | 1/month - 1/week | 1/week - 1/day | On demand |
| **Avg deployment speed** | 2h | 30-120 minutes | 15-30 minutes | < 15 minutes |
| **Average time for changes** | more than a month | 1 week - 1 month | 1 day - 1 week | < 1 day |
| **MTTR (Mean Time to Restore)** | more than a week | 1 day - 1 week | 1 day - 1 hour | < 1 hour |
| **Change Failure Rate** | > 45%| 31-45% | 16-30% | 0-15% |
| **Code Quality Bug Score** | At last 1 blocker or critical Bug (E & D Score) | At least 1 major Bug (C Score) | At least 1 minor Bug (B Score) | No Bugs (A Score) |
| **Static Application Security Testing (SAST)** | At last 1 blocker or critical Vulnerability (E & D Score) | At least 1 major Vulnerability (C Score) | At least 1 minor Vulnerability (B Score) | Info Only (A Score) |
| **Dependency Vulnerabilities** | At last 1 Critical or HighSeverity Level |  At least 1 Medium Severity Level | At least 1 Low Severity Level | No Vulnerabilities |
| **Test Automation** | Less than 20% |20-80% | >80% | >80% |
| **Functional Testing** | No | All Test Run | All Test Pass | All tests Pass |

This in important to understand what is a mature application and what was the objective of the JSL improvements.


####  2.1.3. <a name='Objectives'></a>Objectives

The main objectives of this project were:

| **Objective ID** | Objective | Details |
|--------------|-----------|---------|
| **OBJ-001** | Increase Maturity (**[DORA](#dora-devops-kpi) HIGH** ) of the Jenkins Shared Libraries and related core components | - Increase Unit Test Coverage to 80%<br>- Implement Functional Testing with at least 30% of coverage<br>- Implement Regression Testing for Unit and Functional Testing<br>- Fix SonarQube Issues or justify the existence of them |
| **OBJ-002** | Create a way to automatically generate Release Notes and Change Logs | - Releases should be automatically updated each 15 days to ensure features are under testing on latest code and be incorporated to Stable when ready for production<br>- Hot Fixes should be automatically included on stable release if possible<br>- Fixes should be included on current release if possible |
| **OBJ-003** | Create a way to automatically update the applications that are using the Jenkins Shared Libraries and related core components | |


####  2.1.4. <a name='SolutionStrategy'></a>Solution Strategy


![AllInOne](assets/allinone.gif)  

This section outlines the **high-level strategy** used to resolve the challenges of the project . The core **design principles** ensured that:  
- ✅ The **existing Groovy (JDK 11) & Jenkins** execution environment remained unchanged.  
- ✅ **Testing automation** improved reliability while maintaining **scalability & maintainability**.  
- ✅ **Release generation & management** need to follow an **automated, predictable process**.  
- ✅ **Security & governance** were reinforced via **controlled GitHub workflows & access policies**.  

- :one: Functional Testing & Validation  
Since Jenkins lacks **efficient functional testing frameworks**, we developed a **custom pipeline-based approach**:  
    - **Test Execution**: A dedicated pipeline dynamically loads JSL components in a controlled execution context.  
    - **Reporting & Tracking**: All test results are **published to Jira via Xray**.  
    - **Configuration**: Tests are defined in **YAML**, ensuring both **human readability** and machine compatibility.  
    - **Docker-Based Execution**: A bundled Dockerfile was created to support all required dependencies & capabilities.  
    - **Regression Testing**: Implemented using **[JenkinsPipelineUnit](https://github.com/jenkinsci/JenkinsPipelineUnit)** for consistency.  

- :two: Release Automation: All release generation and lifecycle management were built around the [GitHub API](https://docs.github.com/en/rest/releases?apiVersion=2022-11-28) 

- :three: Automated Release Process**  
    - **Bi-Weekly Release Cycle**: A new stable release is generated every 15 days.  
    - **Pre-Release Strategy**: The **prerelease tag** acts as the stable reference for the next production release.  

- :four: Stable Release Governance
    - **Force-Push Policy**: The prerelease tag is force-pushed **only by GitHub Apps**, ensuring **same tag** can be used across systems and users/admins **can´t overwrite** the contents.  
    - **Manual Review for PRs**: Engineers are still required to create pull requests (PRs) for any change or manual merge.

- :five: Hotfix & Patch Management: to reduce the mean time to restore and the change failure rate, the following strategy was implemented
    - **Fixes are automatically backported** to both the **current release & prerelease**.  
    - **Conflict Handling**: If a conflict occurs, the engineer must **manually resolve and create a PR**.  
    - **Hotfix PRs Target the Stable Branch**
    - **Automated Release Notes**

- :six: Automated Release Notes
    - **GitHub Release Notes System** is used to document changes. based on **[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)** which are enforced to **auto-classify changes (fix, feat, chore, etc.)**.  



- [Introduction and Goals](#introduction-and-goals)
    - [Requirements Overview](#requirements-overview)
    - [Quality Goals](#quality-goals)
    - [Systems Stakeholders](#systems-stakeholders)
- [Solution Content](#solution-content)



The overall goal is to be able to have a stable and functionally tested release for the JSL that can be seamlessly used by the different teams to operate their pipelines, with the capability to receive fixes in the shorter term as possible and features in a maximum period of one month. Once done, the libraries should be prepared to integrate with the Automatic Change Management process to be able to be used by the mature applications.

One of the main decisions made to continue with this project was the creation of Stable release concept.

The stable release is considered a release that has lived for some time in the system, used by early adopter and that and is considered as tested enough to be released to the rest of the teams.

## 1.1 Requirements Overview

![Use Case Diagram](./assets/uml-render/01-ucStable/01-ucStable.png)

| ID | Use Case (Functional Requirement) | Description |
|----|-----------------------------------|-------------|
| UC-001 | Release Generation | - Jenkins should be able to automatically generate a release without the intervention of any engineer. <br>- The release is considered as an standard one (Timed YYYY.MM.DD) and should include Minor and Patch Version (YYYY.MM.DD.Minor.Patch).<br>- Release should be possible to be still manually generated on request.<br>- Releases on same day should automatically increase Minor.<br>- Release Should include Release Notes of what has been done from one release to another in a proper documented way.<br>- Any issue on a release generation should be notified |
| UC-002 | Regression Tests | System should automatically detect regressions when possible and Engineers and collaborators should be able to generate and verify the regression traces |
| UC-003 | Functional Tests | - System should automatically trigger functional Tests that need to be passed in order to continue with any release generation.<br> - Functional Tests need to run out of JSL pipeline but results should be stored in Jira.<br> - JSL pipeline should wait for external execution and retrieve Jira test when finished.<br> - JSL pipeline need to verify the execution result. |
| UC-004 | Functional Test Configuration | DevOps Engineer should be able to configure, add, delete or modify functional tests that are executed as part of the JSL vía GitHub |
| UC-005 | Stable Preparation | - System should be able to prepare the next stable release which should include features from prior to the PRE-release generation and fixes and hot fixes from that point of time until the stable release generation.<br>- Prerelease should include release notes of what is included.<br>- Prerelease should be never consider as a final release and will be always considered a prerelease version (not published). |
| UC-006 | Stable Generation | - Twice a month (each 15 days) a stable release should be automatically generated based on prerelease.<br> - A stable generation execution does not need to build, test or pass any mandatory execution.<br> - A stable release will only verify that functional Tests have been passed prior generation. |
| UC-007 | Fix | - A DevOps Engineer or Collaborator should be able to generate a fix whenever is required.<br>- A Fix should pass all the regression tests.<br>- A Fix should pass all the functional tests prior release generation<br>- A fix should be automatically included in current release<br>- A fix should be automatically included in the pre-release if possible<br>- Release notes with the Fix should be included as part of the release |
| UC-008 | Hot Fix | - A DevOps engineer or Collaborator  should be able to tag a Fix as a HotFix <br> - A HotFix is a special type of fix where the fix need to be passed to stable.<br> - A HotFix will generate a branch which will produce a pull request to stable with a label as a hot-fix<br> - Branch will include a CHANGE-LOG that will generate the release notes.<br> - Once merged to Stable, it should automatically generate new release.<br> - Any failure on the process need to be notified |
| UC-009 | Fast-Forward Feature | - As a DevOps Engineer I should be able to manually generate a branch that will be later used to produce a pull request to stable.<br>- A fast Forward feature is an important feature that need to enter in stable due an exceptional event, for that reason this procedure should not be automatic. |

## 1.2 Quality Goals

Based on [ISO 25010](https://www.iso.org/es/contents/data/standard/07/81/78176.html) we have defined the following quality goals for the project:


| Priority | Quality | Motivation |
|---|---|---|
| 1 | Compatibility | The   System should be compatible with current release system, therefore, might   support standard releases by request apart of the manual ones. |
| 1 | Suitability | Functional   Testing should emulate the target environment (Jenkins) and therefore should   be executed in the environment |
| 1 | Operability | - Any release operation, success or fail   should notify JSL administrators about it.<br> - Also, errors should be self explanatory enough to be able to evaluate the   problem. |
| 2 | Usability | Regression Testing should be easily enough explained to be generated by a Collaborator |
| 2 | Maintainability | All the code should be available for JSL Administrators in GitHub |
| 3 | Transferability | System should be able to run in any of the Jenkins instances |
| 3 | Performance | System should be able to complete the compile, test and release generation in less   than an hour. |

## 1.3 Systems Stakeholders

| Role | Description | Goal/Intention |
|---|---|---|
| DevOps Administrator | Administrate de JSL and provides review to the whole process, releases and peer reviews | - Wants   to be able to generate releases on request. <br> - Want to be able to administrate Fixes, Hot Fixes and Fast-Forward elements. <br> - Needs to review release generation issues. <br> - Administrate Functional Tests. |
| DevOps Collaborator | Collaborate with new code to the JSL | - Wants   to add new features or fixes to the JSL. <br> - Needs to generate or regenerate regression traces. <br> - Need to be informed on the issues in their pull request. |
| DevOps Users | Use the   JSL as part of their pipelines | Want an   stable and functional library version that does not require changes in self pipelines in time.|
| GitHub App | Application that will be used aas an automated layer to authenticate M2M to the system and GitHub | - Wants   to be able to authenticate to GitHub and Jenkins. <br> - Needs to be able to generate branches and pull requests. <br> - Needs to be able to generate releases. |


# 2 Technological Constraints



- [Technological Constraints](#technological-constraints)
- [Solution Content](#solution-content)



At the moment of the design of the solution the following constraints were considered:

1. System should run on current Jenkins Implementations
2. Code should be stored in GitHub and releases should be administrated and generated there.
3. Only automated users/app should be able directly update stable
4. Regression Tests includes Unit Test
5. Functional Tests have it’s own repository and pipeline
6. Regression Tests can’t be applied to date generation libraries at the moment due that the stacktrace should be unique and independent.

# 3 System Context and Scope



- [System Context and Scope](#system-context-and-scope)
    - [System Context Diagram](#system-context-diagram)
- [Solution Content](#solution-content)



This architecture follow the patterns of [C4 Model](https://c4model.com/) and the [4+1 Architectural View Model](https://en.wikipedia.org/wiki/4%2B1_architectural_view_model)

This section contain all the delimits of the systems and communications

## 3.1 System Context Diagram

![Business System Context Diagram](./assets/uml-render/02-bizContext/02-bizContext.png)

![Technical System Context Diagram](./assets/uml-render/02-techContext/02-techContext.png)

| Neighbour | Description |
|:---:|:---:|
| DevOps Engineer | In charge of administrate the solution |
| GitHub | Source Code Management Tool used to store the code of the functional tests and the JSL. Tool to administrate the releases generated in the JSL |
| Jira | Agile Development tool used to store the Tests using XRAY to be later consume by the JSL Pipeline |
| MS Teams | Main Communication tool where the notifications about the status of the pipelines, releases generation and publish release notes |
| Jenkins | Build system which will execute the different componentes and pipelines |
| Apigee | API Gateway used to communicate Internet Apps to Jenkins |


# 4 System Context and Scope



- [4 System Context and Scope](#4-system-context-and-scope)
    - [4.1 Withebox - Container Diagram](#41-withebox---container-diagram)
    - [4.2 Blackbox - Components Diagram](#42-blackbox---components-diagram)
            - [4.2.1.1 Code Implementation Example](#4211-code-implementation-example)
        - [4.2.2 Regression Verify](#422-regression-verify)
            - [4.2.2.1 Code Implementation Example](#4221-code-implementation-example)
        - [4.2.3 Functional Execution and Verify](#423-functional-execution-and-verify)
            - [4.3.2.1 Code Implementation Example](#4321-code-implementation-example)
        - [4.2.4 Functional Execution](#424-functional-execution)
            - [4.2.4.1 Code Implementation Example](#4241-code-implementation-example)
        - [4.2.5 Functional Test Configuration](#425-functional-test-configuration)
        - [4.2.6 Release Generation](#426-release-generation)
            - [4.2.6.1 Code Implementation Example](#4261-code-implementation-example)
        - [4.2.7 Stable Preparation/Generation](#427-stable-preparationgeneration)
            - [4.2.7.1 Code Implementation Example](#4271-code-implementation-example)
        - [4.2.8 Hotfix Generation](#428-hotfix-generation)
            - [4.2.8.1 Code Implementation Example](#4281-code-implementation-example)



Based on the context diagrams we can detail the different components of the solution

## 4.1 Withebox - Container Diagram

Understanding the Containers a separately runnable/deployable unit (e.g. a separate process space) that executes code or stores data, we can define the following containers:

![Container Diagram](./assets/uml-render/03-ContainerDiag/03-ContainerDiag.png)

| Component | Description |
|:---:|:---:|
| Commit Verify | This component will take the commit on any PR and verify that it is compliant with the conventional commits, except merge or reverts. Once extracted the type, it will label the PRs.  |
| Regression Verify | This component will be included as part of the current build system and will check the stacktraces and compare with the build in order to verify the existance of Regressions |
| Functional Execution and Verify | Simple component designed to request the execution of functional testing and  |
| Release Generation  | This system will be in share of the release generation keeping on demand and automated generation.  The version will be YYYY.MM.DD.MINOR.PATCH |
| Stable Preparation/Generation | Stable Preparation is the component in charge of prepare the prerelease to be used as the next stable generation as well as generate the stable release branch for later generation create (both methods will use the release generation) |
| Functional Execution | Pipeline in charge to load libraries on request and execute the configured tests |
| Functional Test Configuration  | Component in charge to load a yaml configuration for execution of tests |
| HotFix/Fix Generation | This component handle the pull requests that are labeled as fix or hot-fix. This include the manipulation of the releases and therefore include the release generation and stable preparation |

## 4.2 Blackbox - Components Diagram

<!-- ### 4.2.1 Commit Verify -->

This component takes the commits and verify that they comply with the conventional commit using [commitLint](https://github.com/conventional-changelog/commitlint/tree/master)  this is installed through npm, the results are checked by the resultChecker and finally the prLabeler will label the pr accordingly to be compliance with the release notes generation by GitHub with the help of the labelArrayBuilder.

![Commit Verify](./assets/uml-render/04.01-ComponentCommit/04.01-ComponentCommit.png)

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| gitHubLibs | Custom Libraries that supports the GitHub API internally in Jenkins| GitHub API Requirements | Commits<br>PR |
| CommitLint | Verify that the commit is compliant with conventional commit | Git Commits | JSON with results |
| resultChecker | This Component Verifies that the commits lint results are correct and reject or accept the PR depending on the results | commitLintJSON | GitHub Message with negative result and description of errors per commits. Also generate an Error Call to Jenkins |
| labelArrayBuilder | This component receive the conventional commits and generate an array for later manipulaion with the prLabeler | Commits Conventional Regex | Labels Array |
| prLabeler | This component labels the pull request based on the type from the commits  | Labels Array | Label PR Update on GitHub |
| Jenkins | Jenkins is the orchestrator of the components | - | - |
| Code  | Cloned copy of the code to be compiled | - | - |

#### 4.2.1.1 Code Implementation Example

In this code snipped it can be seen a bit the way the components where integrated 

```groovy
steps {
    script {
      def npmHome = './node_modules/'
      def commitLint
      def prTitleLint
      sh (script: "npm install --save-dev @commitlint/cli @commitlint/config-conventional commitlint-format-json")
        sh (script: """
              set -ev
              ${npmHome}.bin/commitlint  --from=origin/${CHANGE_TARGET} --to=${env.GIT_COMMIT} --verbose -o commitlint-format-json > Commitlint.commits.json || true
          """, label: "Linting Things" )
      def catLint = sh (script: "cat Commitlint.commits.json", returnStdout: true).trim()
      commitLint = readJSON text: $/${catLint}/$
      if (!commitLint.valid) {
        archiveArtifacts artifacts: "Commitlint.commits.json", fingerprint: true
        def message = ":bangbang: :bangbang: Errors found in commits<br />Please follow [CONVENTIONAL COMMITS](https://github.com/Org/lib-shared#conventional-commits):<br />"
        for (result in commitLint.results) {
          if (!result.valid) {
            message = message + "<br />" + result.input + "<br />"
            for (errorResult in result.errors) {
              message = message + "<li>" + errorResult.message+ "</li>" + "<br />"
            }
          }
        }
        try {
          libGitHubMessage(message.replaceAll('[\n\r]+','<br />'))
        } catch (e) {
          echo(message)
          message = ":bangbang: :bangbang: Errors found in commits<br />We haven't been able to identify the problems, probably you have included characters that are not acccepted for Github Messages<br />Please follow [CONVENTIONAL COMMITS](https://github.com/Org/lib-shared#conventional-commits) and verify your commits"
          libGitHubMessage(message.replaceAll('[\n\r]+','<br />') )
          error 'Error' + e.getMessage() + 'found in commits: Please follow <a href="https://github.com/Org/lib-shared#conventional-commits>CONVENTIONAL COMMITS</a>"'
        }
        error 'Errors found in commits: Please follow <a href="https://github.com/Org/lib-shared#conventional-commits>CONVENTIONAL COMMITS</a>"'
      } else {
        def message = ":white_check_mark: :white_check_mark: Commit is compliant with Conventional Commits :white_check_mark: :white_check_mark:"
        libGitHubMessage(message)
      }
      def convetionalRegex = /^(?<type>build|chore|ci|docs|feat|fix|perf|refactor|Revert|style|test)(?<scope>\(\w+\)?((?=:\s)|(?=!:\s)))?(?<breaking>!)?(?<subject>:\s.*)/
      def conventionalCommits = commitLint.results.findAll { it.input =~ convetionalRegex  }
      def labelsArray = labelArrayBuilder(conventionalCommits, convetionalRegex)
      prLabeler(labelsArray)      
    }
  }
```

In summmary and taking a bot of advange of AI generated summaries

1. **Setup and Install Dependencies**:
   - The script installs necessary npm packages for commit linting using `npm install --save-dev @commitlint/cli @commitlint/config-conventional commitlint-format-json`.

2. **Linting Commits**:
   - It runs the `commitlint` tool to check commit messages from the target branch to the current commit and outputs the results in JSON format to `Commitlint.commits.json`.

3. **Read and Parse Lint Results**:
   - The script reads the JSON file and parses the results using `readJSON`.

4. **Handle Linting Errors**:
   - If any commit messages are invalid, it archives the JSON file and constructs an error message detailing the issues found.
   - It attempts to send this message to GitHub using `libGitHubMessage`. If this fails, it logs the message and raises an error.

5. **Success Message**:
   - If all commit messages are valid, it sends a success message to GitHub.

6. **Labeling Commits**:
   - The script uses a regex pattern to identify conventional commits and extracts their types.
    - It generates an array of labels based on the commit types using `labelArrayBuilder`.
    - It labels the pull request with the generated labels using `prLabeler`.

```groovy
def prLabeler(def labels) {

  def labelArray = []

  labels.each { type ->

    def label
    if (type == 'fix') {
      label = 'bug'
    } else if (type == 'feat') {
      label = 'enhancement'
    } else if (type == 'docs') {
      label = 'documentation'
    } else if (type == 'style') {
      label = 'style'
    } else if (type == 'refactor') {
      label = 'refactor'
    } else if (type == 'perf') {
      label = 'performance'
    } else if (type == 'test') {
      label = 'test'
    } else if (type == 'ci') {
      label = 'ci'
    } else if (type == 'refactor') {
      label = 'refactor'
    } else if (type == 'revert') {
      label = 'revert'
    } else if (type == 'build') {
      label = 'build'
    } else {
      label = 'chore'
    }

    labelArray.add(label)

  }

  def response = libGitHubLabels('issue','POST',labelArray)

}
```

This get help from the labelArrayBuilder that is a simple function that will generate an array of labels based on the type of the commit

```groovy
@NonCPS
def labelArrayBuilder(def conventionalCommits, def convetionalRegex) {

  def labels = []
  conventionalCommits.each { commit ->
    def match = ( commit.input =~ convetionalRegex )
    def type = match[0][1]
    labels.add(type)
  }

  return labels
}
```


### 4.2.2 Regression Verify



The regression Tests need to be integrated in the unit test without need from developer to update or require any information except when the update of traces is required. the traces are stored as part of the Code, if the traces generated differ with the ones stored in the Code, the system will generate an error and send a message to GH about the errors.

This integration is possible with the help of the [JenkinsPipelineUnit](https://github.com/jenkinsci/JenkinsPipelineUnit?tab=readme-ov-file#compare-the-callstack-with-a-previous-implementation) which already have a way to use this kind of tests.

![Regression Verify](./assets/uml-render/04.02-ComponentRegVerify/04.02-ComponentRegVerify.png)

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| Regression Trace Compare | Regression Test is an internal part of the Unit testing framework which compares traces stored with the generated ones in the Test Execution.  In case of difference, the whole compilation will fail. | Stacktraces (On FS and memory) | OK or NOK |
| Results Checker | This component will check the results of the regression test and will send a message to GitHub in case of failure as well as storing the html results | Gradle & Junit results | GitHub Message<br>HTML Page | 

#### 4.2.2.1 Code Implementation Example

This component had a part of code that was made in the stage of Jenkins (Results Checker) and another that was part of the tests of itself

An example of a trace is like this

```text
  libGitHubDeploymentCreate.call(ARGS)
     libGitHubDeploymentCreate.libGitGetRepoOwner()
     libGitHubDeploymentCreate.libGitGetRepoName()
     libGitHubDeploymentCreate.libGetDebugCallback(github)
     libGitHubDeploymentCreate.libGitHubRequestsHandler(https://api.github.com/repos/null/null/deployments, Create GitHub deployment for ARGS, [Accept: application/vnd.github+json], POST, {ref=ARGS, auto_merge=false, environment=staging, required_contexts=[], deploymentTask=deploy}, GITHUB_TOKEN_CREDENTIALS)
     libGitHubDeploymentCreate.libPrintAnsi(ERROR: Unknown GitHub error and could not create deployment: [meta:[Cache-Control:private, max-age:60, s-maxage:60, Vary:Accept, Authorization, Cookie, X-GitHub-OTP, ETag:bc04f3d6b57b6ebce5397036dc264008fa099935d3074b1c47896d1558ceea00, Contents-Type:application/javascript; charset:utf-8, X-RateLimit-Limit:5000, X-RateLimit-Remaining:4994, X-RateLimit-Reset:1664455756, X-RateLimit-Used:6, X-RateLimit-Resource:core, X-OAuth-Scopes:admin:enterprise, admin:gpg_key, admin:org, admin:org_hook, admin:public_key, admin:repo_hook, delete:packages, delete_repo, gist, notifications, repo, user, workflow, write:discussion,write:packages, X-Accepted-OAuth-Scopes:, X-GitHub-Media-Type:github.v3; format:json, status:200], data:[]]; payload: [ref:ARGS, auto_merge:false, environment:staging, required_contexts:[], deploymentTask:deploy], 3)
```

This is generated once the framework is called internally to run the tests 

```groovy
package io.lib.jenkins

import org.junit.Assert
import org.junit.Before
import org.junit.Test


class GitHubDeploymentCreateTest extends GenericSuccessTest {

    GitHubDeploymentCreateTest() {
        super.scriptName = 'vars/libGitHubDeploymentCreate.groovy'
    }

    @Before
    @Override
    void setUp() throws Exception {
        super.setUp()
		callStackPath = 'test/resources/callstacks/'
        [...]

    }

    @Override
    void callScript() {
        [...]
    }

    @Test
    void testTriggerArgs() {
        [...]
        testNonRegression('testTriggerArgs')
    }

}

```

Once this is done and it is compared with the stored traces, the results are checked by the Results Checker that will actually extract the Junit result a process it in a way the developer can understand what is happening.

```groovy
def result = libBuildGradle('clean test --parallel -q', true)
libPublishTestResults("build/reports/**/*.xml")
if (!result) {
  libPublishHTMLTestResults('index.html','build/unithtml/', 'JSL TEST HTML Report')
  def message = ":bangbang: :bangbang: Errors found in Build Stage, probably because of a Failed Test or you may forgot Regression Tests<br />Guidelines:<br />* [How To Create Unit Tests](https://github.com/Org/lib-shared/wiki/HOWTO-Create-Unit-Test-for-JSL)<br />* [Regression Tests](https://github.com/Org/lib-shared#regression-tests)<br />* [JUnit Tests Result](${env.BUILD_URL}/JSL_20TEST_20HTML_20Report)"
  libGitHubMessage(message)
  error """Build failed, please check <a href="${env.BUILD_URL}/JSL_20TEST_20HTML_20Report"> Test results </a>or logs at build stage"""
}
libPublishHTMLTestResults('index.html','build/jacocoHtml/', 'JSL COVERAGE HTML Report')
```

### 4.2.3 Functional Execution and Verify

The functional tests are executed in a separated pipeline that is triggered by the JSL pipeline. The results are stored in Jira and the JSL pipeline will wait for the results to continue with the release generation.

This particular component help to trigger and wait for the results of the functional tests.

![Functional Execution and Verify](.//assets/uml-render/04.03-ComponentFunExVEr/04.03-ComponentFunExVEr.png)

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| Remote Test Executer | This component will trigger the execution of the functional tests (with the help of alreasy existing jenkins method) with certain parameters related of this execution | Test Execution Request | OK/NOK |
| Jenkins | Jenkins is the orchestrator of the components | - | - |
| Jira Puller (libJiraPullTestResults) | This component will pull the results of the functional tests from Jira and will store them in a file for later use | Jira Test ID | File with Results |
| libCheckQAGates | External component to compare the results between 2 different jira test results | Jira Test Results | OK/NOK |

#### 4.3.2.1 Code Implementation Example

In general this was not a complex element to implement, the main part was the trigger of the functional tests and the wait for the results

```groovy
    script {
      def buildCauses = currentBuild.getBuildCauses()
      def startedFromTimer = buildCauses.any { cause -> cause._class == 'hudson.triggers.TimerTrigger$TimerTriggerCause' }
      if (!startedFromTimer) {
        if (!params.STABLE_RELEASE) {
          libTriggerRemoteJob('main','JSL/lib-functional-validation/', false, true, 1,  [text(name: 'prNbr', value: ''), text(name: 'BRANCH_TO_TEST', value: env.PROD_BRANCH)])
        }
      }
      libJiraPullTestResults('TICKETTEST-1234')
      libCheckQAGates("testRunStatus.json")
    }
```

For the libJiraPullTestResults the flow was as simple as taking a fix testresult feature in Jira and the XRAY licence, we were able to extract the information in a json directly in the pipeline. However this still required several steps:

1. **Get Token** : The first step was to get the token from Xray to be able to access the information, implementing retry mechanish in case of failure.
2. **Get Test Execution ID** : Once the token was obtained, the next step was to get the Test Execution ID from Jira.
3. **Get Test Results** : With the Test Execution ID, the final step was to get the Test Results from Jira and store them in a file for later use after some test processing

```groovy
import groovy.json.JsonOutput 

def call(def issueKey, def jiraCredentials = env.JIRA_TESTAUTO_CREDENTIALS, def xrayCredentialId = env.XRAY_TESTAUTO_ID_SECRET) {
    token = getAuthorizationToken(xrayCredentialId)
    objectId = getObjectId(issueKey, jiraCredentials)
    if (objectId != null && token != null) {
        return getTests(token, objectId)
    }
    return null
}

def getAuthorizationToken(def xrayCredentialId) {
    def tokenResponse = ''
    def maxWaitForSeconds = 5
    def retries = 5
    while (retries > 0) {
        def sleepTime = maxWaitForSeconds * (1/retries)
        withCredentials([file(credentialsId: xrayCredentialId, variable: 'XRAY_CREDENTIALS_FILE')]) {
	        def jira_file = sh script: """
            set + x
            cat \$XRAY_CREDENTIALS_FILE
            """,label: 'getting XRAY credentials',returnStdout: true
            
            def CLIENT_ID = (jira_file.tokenize('\n')[0]).tokenize('=')[1]
	        def CLIENT_SECRET = (jira_file.tokenize('\n')[1]).tokenize('=')[1]

            tokenResponse = sh script: """[..]
            """,label: 'getting authentication token', returnStdout: true
        }
        if (tokenResponse.split("\n")[1] == '200') {
            token = tokenResponse.split("\n")[0].replaceAll("\"", "")
            return token
        }
        sleep(time:sleepTime, unit:"SECONDS")
        retries -= 1
    }
    echo "Request failed. Error message: ${tokenResponse.split("\n")[0]}"
    return null
}

def getObjectId(String issueKey, def jiraCredentials) {
    def objectIdResponse = ''
    def maxWaitForSeconds = 5
    def retries = 5
    while (retries > 0) {
        def sleepTime = maxWaitForSeconds * (1/retries)
        withCredentials([usernamePassword(credentialsId: jiraCredentials, passwordVariable: 'jira_token', usernameVariable: 'jira_username')]) {
            objectIdResponse = sh(script: """[...]""",
                label: 'getting test plan object id', returnStdout: true).trim()
        }
        if (objectIdResponse.split("\n")[1] == '200') {
            def object = readJSON text: objectIdResponse.split("\n")[0]
            return object.id
        }
        sleep(time:sleepTime, unit:"SECONDS")
        retries -= 1
    }
    echo "Request failed. Error message: ${objectIdResponse.split("\n")[0]}"
    return null
}

def getTotalTestsCount(String token, Object objectId)
{
    def maxWaitForSeconds = 5
    def retries = 5
    while (retries > 0) {
        def sleepTime = maxWaitForSeconds * (1/retries)
        testCountResponse = sh(script: """[...]""",
            label: 'getting test count', returnStdout: true)

        if (testCountResponse.split("\n")[1] == '200') {
            def object = readJSON text: testCountResponse.split("\n")[0]
            return object.data.getTestPlan.tests.total
        }
        sleep(time:sleepTime, unit:"SECONDS")
        retries -= 1
    }
    echo "Request failed. Error message: ${testCountResponse.split("\n")[0]}"
    return null
}

def getTests(String token, Object objectId) {

    def output = '{"tests":[' 
    def maxWaitForSeconds = 5
    def retries = 5
    while (retries > 0) {
        def sleepTime = maxWaitForSeconds * (1/retries)
        def totalTests = getTotalTestsCount(token, objectId) 
        def limit = 100
        def totalTestsCeil = (totalTests + limit - 1).intdiv(limit)
	    boolean flag = false
        for (def test = 0; test < totalTestsCeil; test++) {
            def testResultsResponse = ''
            def startAt = test * limit
            testResultsResponse = sh(script: """[...]""",
                label: 'getting tests result', returnStdout: true)

            if (testResultsResponse.split("\n")[1] == '200') {
                flag = true
                def object2 = readJSON text: testResultsResponse.split("\n")[0]
                def testObjectCount = 1
                len = object2.data.getTestPlan.tests.results.size()
                for (def value: object2.data.getTestPlan.tests.results) {
			        def new_test = JsonOutput.toJson([testKey: "${value.jira.key}", status: "${value.status.name}"])
                    output = output + new_test
                    if (testObjectCount != len || test != totalTestsCeil - 1) {
                        output = output + ','
                    }
                    testObjectCount++
                }
            }
            else{
                echo "Request failed. Error message: ${testResultsResponse.split("\n")[0]}"
                echo "Retrying..."
            }
        }
        if (flag == true) {
            break
        }
        sleep(time:sleepTime, unit:"SECONDS")
        retries -= 1
    }
    output = output + ']}'
    writeFile(file: 'testRunStatus.json', text: output)
    return output
}
```

### 4.2.4 Functional Execution

Functional Test Execution runs out of the JSL Pipeline but inside Jenkins, it loads the libraries on request, JSL only will trigger the master execution, therefore other tests might be called manually. Once the libraries are loaded, it reads the config and proceed to run the tests either on docker or agent. Once finished the tests are verified and the uploaded to Jira to finally cleanup the environments.

![Functional Execution](./assets/uml-render/04.04-ComponentFuncExec/04.04-ComponentFuncExec.png)

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| Map Load | This component load the configuration generated in the repo in order to preprare the tests to be executed | Config from GitHub | Prepared Tests to execute |
| Library Load | This component load the libraries on request either from a branch or a PR | PR Number or Branch to load | Loaded Libraries |
| Test Run | This component execute the prepared tests on the node specified and with the parameters specified (or none) | Prepared Tests to execute | Test Result output |
| Test Writter | This component write the results in a Junit Format | Test Result Output | Test Result files |
| Result Verify | Check all the result files and publish them to jenkins. It Stash them as well for further use | Test Result Files | Publish Test Results Stash (Test files) |
| Result Upload | Unstash the Test Result files adn upload them to Jira using XRAY | Stash (Test files) | Xray Test Result contents |
| Cleaning | This will connect to any environment where the tests were executed and clean all the leftovers that were created by the tests | Config | N/A |


#### 4.2.4.1 Code Implementation Example

This wa one of the most complex components to implement, as per the problems described before on having the environment as similar as the final one to be used by users. In the end this is a pipeline that have conditional load of tests depending on the configuration (YML):

```yml
  - library: libKubeconfigWrapper
    standalone: true
    testCases:
      - name: TestOK
        args:
          - 'kubectl get deployments'
          - 'This is a test'
          - 'none'
      - name: TestMain
        args:
          - 'kubectl get deployments'
          - 'This is a test'
          - 'none'
          - 'main'
      - name: TestMaster
        args:
          - 'kubectl get deployments'
          - 'This is a test'
          - 'none'
          - 'master'
```

This file or map describes the library that is going to be tested, if this run on standalone agent or a docker agent and the test cases that are going to be done and finally the arguments that are going to be passed to the test.

Additional problems was to be able to do a testcall and inject the parameters to the libraries from another function. Which is not possible straight forward for the nature of Jenkins which does not allow to pass parameters to a function that is not in the same scope or that can't control the status of the function.

```groovy
@NonCPS
def testExecArgs(def test, def params) {
    def testExecOut = ''
    testExecOut ="$test"(*params)
    return testExecOut
}

def testExec(def test) {
    def testExecOut = ''
    testExecOut ="$test"()    return testExecOut
}
```

### 4.2.5 Functional Test Configuration

Functional Test Configuration will check and verify that the configuration Generated by the DevOps engineer is valid to be executed. Once executed the pipeline in verify that you are not testing and then execute the linting of the yaml, if correct, the PR will be marked as success, otherwise it will be marked as failed. 

![Functional Test Configuration](./assets/uml-render/04.05-ComponentFuncConf/04.05-ComponentFuncConf.png)

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| Lint | This component verify the yaml of the configuration to guarantee that it is correct | configMap | Ok or NOK |
| configmap | This component will load the configuration from the repo | testConfig | Config Map |

In general this was normally udited using an special call in the same pipeline that is capable to do the test in a controlled PR mode.

### 4.2.6 Release Generation

The release generator will adapt the current method of create a branch for release and generate a GitHub release on request to an automatic flow that will be able to generate an automatic release on fix and hotfix as well as the normal one with the possibility of multiple ones per day (which was a limitation of previous model). Once the the branches are checked and generated, it will be handled to create the release in GitHub with its proper Release Notes and notify the users in the CoP about the new releases. 

![Release Generation](./assets/uml-render/04.06-ComponentRelGen/04.06-ComponentRelGen.png)

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| releaseChecker | This component will get the current release, verify changes and generate the new one if required increasing the DATE, MINOR or PATCH. Also check the tags to verify that the new ones does not exist  | commit current release | new release branch name |
| releaseBranchGenerator | This component generate the release branch with its documentation<br> AlsoThis will update the branch with the new CHANGE_LOG and generate the release in GitHub. This component also notify Teams with the new release | release branch name<br>release notes<br>release data | new release branch |
| releaseNotesGenerator | This will generate a release notes from GitHub logic based on new content | previous tag new tag new release branch | release notes |

#### 4.2.6.1 Code Implementation Example

This appear to be a complex component but at the end it provides almost the same iteration over different scopes.

In general the process is:

- Fetches the repository owner and name.
- Determines the current date and formats it as the release version.
- Retrieves the latest release information from GitHub.
- Checks if there are any changes since the last release.
- If there are changes, it creates a new release or updates the existing one.
- If there are no changes, it identifies the current commit and sets up the environment variables for the release tag and branch.
- If the release is authorized and the build is successful, it proceeds to publish the release.
- Fetches the repository owner and name.
- Determines if the build was triggered by a timer.
- Generates release notes and creates a new GitHub release if necessary.
- If the build was triggered by a timer or a stable release is requested, it updates the stable and prerelease tags and notifies the team.

```groovy
steps {
    script {
        def repoOwner = libGitGetRepoOwner()
        def repoName = libGitGetRepoName()
        def now = new Date()
        def release = now.format("yyyyMMdd", TimeZone.getTimeZone('UTC')) + ".0" + ".0"
        def currentRelease
        def latestRelease = libGitHubRequestsHandler("https://api.github.com/repos/${repoOwner}/${repoName}/releases/latest", "Getting current release").data
        currentRelease = latestRelease.tag_name
        env.CURRENT_RELEASE = currentRelease
        def isReleaseDiff = sh ( script: "git diff ${currentRelease}~1..${env.GIT_COMMIT} --name-only | wc -l", returnStdout: true ).toInteger() != 0
        if (isReleaseDiff) {
        def currentMajor = currentRelease.tokenize('.')[0]
        def currentMinor = currentRelease.tokenize('.')[1] ?: '0'
        def currentPatch = currentRelease.tokenize('.')[2] ?: '0'
        def releaseId = libGitHubReleaseGetId(release)
        sh "touch do_release"
        if (releaseId == null) {
            releaseCreate(release, currentRelease)
        } else {
            release = currentMajor + ".${currentMinor}." + currentPatch.toInteger().plus(1)
            releaseCreate(release, currentRelease)
        }
        } else {
        releaseBranch = latestRelease.target_commitish
        if (!releaseBranch) {
            error ("not able to identify current commitish, aborting release generation")
        }
        env.RELEASE_TAG = currentRelease
        env.RELEASE_BRANCH = releaseBranch
        sh "echo -n yes > do_release"
        stash name: "DO_RELEASE", includes: "do_release"
        }
    }
}
```

For the Release Create

```groovy
def releaseCreate(def release, def currentRelease, def customNotes = null, def hotFix = false, def hotFixBranch = null) {
  echo 'Generating Release Change Log'
  def jiraregex = /((?<!([A-Za-z0-9]{1,10})-?)[A-Za-z0-9]+-\d+)/
  def releaseNotes
  def my_intro = './doc/docuIntro.md'
  def my_class = './vars/'
  def my_destination = "./Class-Documentation.md"
  def my_destPath = "./classDocuments"
  def my_split = true
  if (customNotes != null) {
    releaseNotes = customNotes
  } else {
    try {
      releaseNotes = "# RELEASE NOTES ${release}\n\n" + libGitHubReleaseLog(release, env.PROD_BRANCH, currentRelease, '.github/release.yml')
    } catch (Exception e) {
      unstable("The changelog generation has failed, generating a default file. Error:" + e.toString())
      releaseNotes = "# RELEASE NOTES ${release}\n\n" + libGitHubReleaseLog(release, env.PROD_BRANCH, currentRelease)
    }
  }
  writeFile(file: 'CHANGE_LOG.md', text: releaseNotes)
  if (hotFix) {
    sh script: """
    set +x
    git add .
    git commit -m "docs: add CHANGE_LOG"
    git push -u origin ${hotFixBranch}
    """, label: 'Create new release branch'
  } else {
    libDeployJSL(release)
  }
  env.RELEASE_TAG = release
  def releaseBranch = "release/$release"
  env.RELEASE_BRANCH = releaseBranch
  sh "echo -n yes > do_release"
  stash name: "DO_RELEASE", includes: "do_release"
}
```

### 4.2.7 Stable Preparation/Generation

This is a 2 components in one

The release preparation is a simple component that will generate the prerelease tag to point the release that will be used by stable to update it’s branch and include the needed release notes, this release will be always considered as a pre-release for GitHub and never as a definitive one.

The Stable Release Generator is an important component that force update stable while started from timer on 1st and 15th day of any month, or, by DevOps Engineer request in case it si required. It first check current tags and generate the notes to the previous prerelease tag, then it reset the branch to the commit of the prerelease and create a CHANGE_LOG to further force push the branch and finally update the Stable release in GitHub

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| releaseChecker | This component will get the current tags from prerelease and stable and extract the current release details. | current stable tag current prerelease tag | current stable release current prerelease tag next stable tag |
| branchUpdater | it resets the stable branch to the prerelease commitish and add the CHANGE_LOG to force push the branch | prerelease commitish Release Notes | forced update stable branch |

#### 4.2.7.1 Code Implementation Example

The stable release is integrated in several plases but in general the process (Code) is as below

```groovy
def staticReleaseNotes
def preReleaseReleaseNotes
def stableReleaseId = libGitHubReleaseGetId(currentStableTag.trim())
def prereleaseId = libGitHubReleaseGetId(currentPrereleaseTag.trim())
def preReleaseCommitish = libGitHubRequestsHandler("https://api.github.com/repos/${repoOwner}/${repoName}/releases/${prereleaseId}", "Getting current prerelease").data.target_commitish
if (!preReleaseCommitish) {
    error ("not able to identify current commitish on ${currentPrereleaseTag.trim()} tag, aborting stable release update")
}
try {
    staticReleaseNotes = "# RELEASE NOTES STABLE\n\n" + libGitHubReleaseLog(stable, preReleaseCommitish, currentStableTag.trim(), '.github/release.yml')
    preReleaseReleaseNotes = "# RELEASE NOTES STABLE\n\n" + libGitHubReleaseLog(prereleaseTag, branchName, currentPrereleaseTag.trim(), '.github/release.yml')
} catch (Exception e) {
    unstable("The changelog generation has failed, generating a default file. Error:" + e.toString())
    staticReleaseNotes = "# RELEASE NOTES STABLE\n\n" + libGitHubReleaseLog(stable, preReleaseCommitish, currentStableTag.trim())
    preReleaseReleaseNotes = "# RELEASE NOTES STABLE\n\n" + libGitHubReleaseLog(prereleaseTag, branchName, currentPrereleaseTag.trim())
}
def repo_name = libGitGetRepoName()
def repo_owner = libGitGetRepoOwner()
libGitHubCloneRepo(repo_name,repo_owner)
dir(repo_name) {
    withCredentials([usernamePassword(credentialsId: env.GITHUB_TOKEN_CREDENTIALS, usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_PASSWORD')]){
    sh script: """
        set +x
        git config --local credential.helper "!f() { echo username=\$GIT_USERNAME; echo password=\$GIT_PASSWORD; }; f"
        git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"
        git fetch --all
        git checkout stable
        git reset --hard origin/${preReleaseCommitish}
        git push -f origin stable
    """
    }
}
libGitHubReleaseUpdate(stableReleaseId, staticReleaseNotes, env.GITHUB_TOKEN_CREDENTIALS, stable, 'stable', null, false, false, repo_owner, repo_name, 'false')
libNotifyTeams(staticReleaseNotes, 'success',true, env.RELEASE_MSTEAMS_CREDS)
libGitHubReleaseUpdate(prereleaseId, preReleaseReleaseNotes, env.GITHUB_TOKEN_CREDENTIALS, prereleaseTag, branchName, "STABLE PRERELEASE", false, true)
if (currentRelease != tagName) {
    releaseId = libGitHubReleaseCreate(tagName,branchName,env.GITHUB_TOKEN_CREDENTIALS,releaseNotes, false, false,false, repoOwner, repoName, 'true')
    if (releaseId == null) {
    error("There was an error publishing the release")
    }
    libNotifyTeams(releaseNotes, 'success',true, env.RELEASE_MSTEAMS_CREDS)
}
```

### 4.2.8 Hotfix Generation

The Hot Fix Generation is a complex component that will communicate to GitHub to know the current status of the releases based on a Pull Request flagged as fix or HotFix, this will make the component to check the type of PR merged and check the current release for later manipulation. The Release Notes are generated and request a release to be generated, after that, the prerelease is rettaged with latest release. 

For stable there are two flows, the first one that created a pull request only on hot-fix and the other that update the release on stable branch after merge.

The hot-fix flag is always a manual tag due that the engineer is who knows what fix is required to be transfered to stable

| Component | Description | Inputs | Outputs |
|:---:|:---:|:---:|:---:|
| typeChecker | This component will gather the latest PR and check the tags to verify the type of PR, if stable and not PR it will skip.  | Commit | isFix isHotFix |
| releaseChecker | This component gather the latest release and prerelease in order to update the releases with the cherry picker commit | release prerelease commit | cherry picked updated branches |
| taggerPrUpdate | This component will create a branch based on the ticket to stable,  It will cherry pick the commit prior to that, if not possible will notify the failure for further check. The pr will be automatically flagged as hotfix.<br> Also will update the tag of the prerelease based on the new release generated | commit PR<br>release tag | branch PR to stable <br> updated prerelease |

In general the release notes and the release as itself generation will be leveraged to the release component

#### 4.2.8.1 Code Implementation Example

In general  the code is designed with a general fix calculation and a iteration over different scopes

```groovy
 stage('Fix Release') {
      stages {
        stage('Gather Fix Info') {
          steps {
            script {
              def repoOwner = libGitGetRepoOwner()
              def repoName = libGitGetRepoName()
              def branchPr = libGitHubGetLastPR()
              if (branchPr == null && env.BRANCH_NAME == "stable") {
                echo "skiping due force update"
                env.DO_HOTFIX_RELEASE = false
              } else {
                def isFix = branchPr.labels.any{ it.name == 'bug' }
                def isHotFix = branchPr.labels.any{ it.name == 'hot-fix' }
                if (isFix || isHotFix) {
                  env.DO_HOTFIX_RELEASE = true
                  echo "We will try to apply the fix to current_release, preproduction and stable (if applicable)"
                  def currentRelease = libGitHubRequestsHandler("https://api.github.com/repos/${repoOwner}/${repoName}/releases/latest", "Getting current release")
                  def currentReleaseTag = currentRelease.data.tag_name
                  def currentMajor = currentReleaseTag.tokenize('.')[0]
                  def currentMinor = currentReleaseTag.tokenize('.')[1] ?: '0'
                  def currentPatch = currentReleaseTag.tokenize('.')[2] ?: '0'
                  def nextReleaseTag = currentMajor + ".${currentMinor}." + currentPatch.toInteger().plus(1)
                  def repositoryTags = libGitHubRequestsHandler("https://api.github.com/repos/${repoOwner}/${repoName}/tags", "Getting current tags")
                  def stableTags = repositoryTags.data.findAll { it.name.endsWith("stable") }
                  def prereleaseTags = repositoryTags.data.findAll { it.name.endsWith("prerelease") }
                  def currentStableTag = stableTags[0].name
                  def currentPrereleaseTag = prereleaseTags[0].name
                  def stableReleaseId = libGitHubReleaseGetId(currentStableTag.trim(), env.GITHUB_TOKEN_CREDENTIALS,  repoOwner, repoName)
                  def currentMajorStable = currentStableTag.trim().tokenize('.')[0]
                  def currentMinorStable = currentStableTag.trim().tokenize('.')[1] ?: '0'
                  def currentPatchStable = currentStableTag.trim().tokenize('.')[2] ?: '0'
                  def nextStableTag = currentMajorStable + ".${currentMinorStable}." + currentPatchStable.toInteger().plus(1) + ".stable"
                  def prereleaseId = libGitHubReleaseGetId(currentPrereleaseTag.trim(), env.GITHUB_TOKEN_CREDENTIALS, repoOwner, repoName)
                  def currentMajorPrerelease = currentPrereleaseTag.trim().tokenize('.')[0]
                  def currentMinorPrerelease = currentPrereleaseTag.trim().tokenize('.')[1] ?: '0'
                  def currentPatchPrerelease = currentPrereleaseTag.trim().tokenize('.')[2] ?: '0'
                  def nextPrereleaseTag = currentMajorPrerelease + ".${currentMinorPrerelease}." + currentPatchPrerelease.toInteger().plus(1) + ".prerelease"
                  def stableCurrentRelease = libGitHubRequestsHandler("https://api.github.com/repos/${repoOwner}/${repoName}/releases/${stableReleaseId}", "Getting current release")
                  def prereleaseCurrentRelease = libGitHubRequestsHandler("https://api.github.com/repos/${repoOwner}/${repoName}/releases/${prereleaseId}", "Getting current release")
                  def fixApplierBranch = [
                    "repoName" : repoName,
                    "repoOwner" : repoOwner,
                    "branchPr" : branchPr,
                    "currentRelease" : currentRelease,
                    "currentReleaseTag" : currentReleaseTag,
                    "nextReleaseTag" : nextReleaseTag,
                    "stableCurrentRelease" : stableCurrentRelease,
                    "currentStableTag" : currentStableTag,
                    "nextStableTag" : nextStableTag,
                    "prereleaseCurrentRelease" : prereleaseCurrentRelease,
                    "currentPrereleaseTag" : currentPrereleaseTag,
                    "nextPrereleaseTag" : nextPrereleaseTag
                  ]
                  writeJSON file: 'fixApplierBranch.json', json: fixApplierBranch
                  stash(name: 'FIX_APPLIER_BRANCH', includes: 'fixApplierBranch.json')
                } else {
                  env.DO_HOTFIX_RELEASE = false
                }
              }
            }
          }
        }
        stage('Latest Release Fix/HotFix') {
          steps {
            script {
              unstash name: 'FIX_APPLIER_BRANCH'
              def fixApplierBranch = readJSON file: 'fixApplierBranch.json'
              def repoName = fixApplierBranch.repoName
              def repoOwner = fixApplierBranch.repoOwner
              def branchPr = fixApplierBranch.branchPr
              def currentRelease = fixApplierBranch.currentRelease
              def currentReleaseTag = fixApplierBranch.currentReleaseTag
              def nextReleaseTag = fixApplierBranch.nextReleaseTag
              def stableCurrentRelease = fixApplierBranch.stableCurrentRelease
              def currentStableTag = fixApplierBranch.currentStableTag
              def nextStableTag = fixApplierBranch.nextStableTag
              def prereleaseCurrentRelease = fixApplierBranch.prereleaseCurrentRelease
              def currentPrereleaseTag = fixApplierBranch.currentPrereleaseTag
              def nextPrereleaseTag = fixApplierBranch.nextPrereleaseTag
              hotFixApplier("latest", repoName, repoOwner, branchPr, currentRelease, currentReleaseTag, nextReleaseTag)
            }
          }
        }
        stage('Prerelease Release Fix/HotFix') {
          when {
            beforeAgent true
            allOf {
              expression { return env.DO_HOTFIX_RELEASE.toBoolean() }
              branch PROD_BRANCH
            }
          }
          steps {
            script {
              [...]
            }
          }

        }
        stage('Stable Release HotFix') {
          steps {
            script {
              unstash name: 'FIX_APPLIER_BRANCH'
                [...]
              def isFix = branchPr.labels.any{ it.name == 'bug' }
              def isHotFix = branchPr.labels.any{ it.name == 'hot-fix' }
              if (env.BRANCH_NAME == env.PROD_BRANCH) {
                if (isHotFix) {
                  hotFixApplier("stable", repoName, repoOwner, branchPr, stableCurrentRelease, currentStableTag, nextStableTag)
                }
              } else if (env.BRANCH_NAME == "stable" && isHotFix) {
                releaseChangeLog = readFile(file: 'CHANGE_LOG.md').replaceAll("(\\r|\\n|\\r\\n)+", "\\\r\\\n")
                libGitHubReleaseUpdate(stableCurrentRelease.data.id,releaseChangeLog,env.GITHUB_TOKEN_CREDENTIALS,nextStableTag,"stable", null, false, false, repoOwner, repoName, "false", null)
              } else {
                echo "Skipping due that is not a Hot Fix and therefore not applicable on stable"
              }
            }
          }
        }
      }
    }
```

# 5 Runtime View

![Runtime](assets/runtime.gif)



- [Runtime View](#runtime-view)
    - [Scenario 1 - PR](#scenario-1---pr)
    - [Scenario 2 - Standard Master Merge](#scenario-2---standard-master-merge)
    - [Scenario 3 - Stable Release Generation](#scenario-3---stable-release-generation)
- [Solution Content](#solution-content)




The runtime view describes concrete behavior and interactions of the system’s building blocks in form of scenarios, for the case of this project we will just summarize the main scenarios that are part of the system.

## 5.1 Scenario 1 - PR

| Actor | Description |
|---|---|
| **DevOps Engineer** | Interacts with GitHub to review and merge PRs. |
| **DevOps Collaborator** | Codes, generates unit tests, and regression traces, and creates PRs. |


| Participant | Description |
|---|---|
| **IDE** | Used by the DevOps Collaborator for coding and generating tests. |
| **GitHub** | Central repository for code, handles PRs, and communicates with Jenkins. |
| **Jenkins** | CI/CD tool that handles various stages of the build and deployment process. |

Workflow: 

> [!NOTE] 
> This workflow does not include steps that are not relevant to the runtime view specific of this process

```mermaid
graph TD
     A[Code and PR Creation] -->|Create PR| B[Jenkins Build Process]
     B --> C[Commit Linting]
     C -->|Commit OK| D[Labeling PRs]
     C -->|Commit Linting Fails| E[Send Failure Message]
     D --> F[Build and Test]
     F -->|Tests Pass| G[Publish Test Results]
     F -->|Tests Fail| E[Send Failure Message]
     G --> I[Final Steps]
     J[DevOps Engineer] -->|Review and Merge PR| I
```

1. **Code and PR Creation**: The Collaborator codes, generates unit tests, and regression traces in the IDE and creates a PR in GitHub. Optionally label the PR as Hot-fix
2. **Jenkins Build Process**: GitHub triggers a webhook to Jenkins, acknowledges the webhook and scans the project.
3. **Commit Linting**: Jenkins verifies the commit and runs `npm install` and `commitlint`.
    - If commit linting is valid, Jenkins sends a "Commit OK" message to GitHub.
    - If commit linting fails, Jenkins checks for errors and sends detailed messages to GitHub, failing the build if necessary.
4. **Labeling PRs**:
    - If there are conventional commits, Jenkins generates a label array and labels the PR in GitHub.
    - If there are revert commits, Jenkins labels the PR as a revert.
    - If neither, Jenkins sends a failure message and fails the build.
5. **Build and Test**:
    - Jenkins builds the project and checks test results (unit and regression).
    - If tests pass, Jenkins publishes the test results.
    - If tests fail, Jenkins publishes the test results, sends detailed messages to GitHub, and fails the build.
6. **Final Steps**:
    - The DevOps Engineer reviews and merges the PR in GitHub.

## 5.2 Scenario 2 - Standard Master Merge


| Actor              | Description                                              |
|--------------------|----------------------------------------------------------|
| **DevOps Engineer**| Interacts with Jenkins UI to authorize releases.         |


| Participant | Description |
|---|---|
| **Jenkins** | CI/CD tool that handles various stages of the build and deployment process. |
| **Jenkins UI** | Interface for Jenkins where the DevOps Engineer authorizes releases. |
| **GitHub** | Central repository for code, handles PRs, and communicates with Jenkins. |
| **Jira** | Project management tool used for pulling XRAY test results. |
| **MS Teams** | Communication tool used for notifications. |

Workflow:

> [!NOTE]
> This workflow does not include steps that are not relevant to the runtime view specific of this process


```mermaid
graph TD
    A[GitHub Webhook] -->|Trigger| B[Revert Check]
    B -->|Not Revert| C[Build and Test]
    B -->|Is Revert| D[Set IS_REVERT]
    D --> J[Generate Release Branch]
    C -->|Tests Pass| E[Publish Test Results]
    C -->|Tests Fail| F[Send Failure Message]
    E --> G[Functional Testing]
    G -->|Quality Gate Pass| H[HotFix Release]
    G -->|Quality Gate Fail| F[Send Failure Message]
    G -->|Is HotFix| H[HotFix Release]
    G -->|Not HotFix| K[Skip HotFix]
    H -->J[Generate Release Branch]
    K -->J[Generate Release Branch]
    J --> L[Generate GitHub Release]
    L -->|Release Success| M[Notify MS Teams]
    L -->|Release Fail| F
```

1. **GitHub Webhook**: GitHub triggers a webhook to Jenkins, acknowledges the webhook and scans the project.
2. **Revert Check**: Jenkins checks if the head is a revert commit and sets the environment variable `IS_REVERT` accordingly to skip checks.
3. **Build and Test**: Jenkins builds the project and checks test results (unit and regression).
   - If tests pass, Jenkins publishes the test results.
   - If tests fail, Jenkins publishes the test results, sends detailed messages to GitHub, and fails the build.
4. **Functional Testing**:
   - Jenkins requests functional tests and waits for execution to finish.
   - Jenkins pulls XRAY test results from Jira and checks the results (Quality Gate 2).
5. **HotFix Release**:
   - Jenkins retrieves the last PR from GitHub and checks PR labels.
   - If the PR is a fix or hotfix, Jenkins retrieves the last release and generates the next tag.
   - Jenkins checks stable and prerelease tags and processes the release accordingly.
   - Jenkins sets the environment variable `IS_HOTFIX` and loads the release config.
   - Jenkins generates the fix CHANGE_LOG, clones the repo, checks out the release, and cherry-picks changes.
   - If the cherry-pick is successful, Jenkins commits and pushes the changes, generates the release, and notifies MS Teams.
   - If the cherry-pick fails, Jenkins notifies MS Teams of the failure.
6. **Release Authorization**: Jenkins requests release authorization from the DevOps Engineer via Jenkins UI.
   - The DevOps Engineer authorizes the release by providing a password and user.
   - If authorization is successful, Jenkins sets the environment variable `AUTH_RELEASE`.
7. **Generate Release Branch**:
    - Jenkins retrieves the last release from GitHub and checks for differences.
    - If differences exist, Jenkins checks the tag, retrieves the last release, and generates the next tag.
    - Jenkins generates the CHANGE_LOG, checks out a new branch, commits, and pushes the changes.
    - Jenkins sets the environment variable `DO_DEPLOY`.
8. **Generate GitHub Release**:
    - If `AUTH_RELEASE` and `DO_DEPLOY` are defined and the status is SUCCESS, Jenkins retrieves tags from GitHub.
    - Jenkins checks stable and prerelease tags and generates release notes.
    - Jenkins generates the release and notifies MS Teams if successful.
    - If the release fails, Jenkins fails the build.

## 5.3 Scenario 3 - Stable Release Generation

| Actor              | Description                                              |
|--------------------|----------------------------------------------------------|
| **DevOps Engineer**| Interacts with Jenkins UI to manually trigger and authorize releases. |

| Participant        | Description                                              |
|--------------------|----------------------------------------------------------|
| **Jenkins**        | CI/CD tool that handles various stages of the build and deployment process. |
| **Jenkins UI**     | Interface for Jenkins where the DevOps Engineer authorizes releases. |
| **Jenkins Timer**  | Triggers the release process on a schedule.              |
| **GitHub**         | Central repository for code, handles PRs, and communicates with Jenkins. |
| **Jira**           | Project management tool used for pulling XRAY test results. |
| **MS Teams**       | Communication tool used for notifications.               |

Workflow:

> [!NOTE] 
> This workflow does not include steps that are not relevant to the runtime view specific of this process

```mermaid
graph TD
    A[Trigger Release] -->|Timer Trigger| C
    A -->|Manual Trigger| B[Functional Testing]
    H -->|Wait for Auth| H
    G[DevOps Engineer] -->|Authorize| H
    B --> C[Authorize Release]
    C -->|Request Auth if Manual| H[JenkinsUI]
    H -->|Manual Request| D[Generate Release Branch]
    C -->|Timer Trigger| D
    D --> E[Generate GitHub Release]
    E --> F[Post-Release Actions]
```

1. **Trigger Release**:
   - **Timer Trigger**: Jenkins Timer triggers the release process on the 1st or 15th of the month.
   - **Manual Trigger**: The DevOps Engineer manually requests a stable release generation.
2. **Functional Testing**:
   - Jenkins pulls XRAY test results from Jira and checks the results (Quality Gate 2).
3. **Authorize Release**:
   - **Manual Request**: Jenkins requests release authorization from the DevOps Engineer via Jenkins UI.
     - The DevOps Engineer authorizes the release by providing a password and user.
     - If authorization is successful, Jenkins sets the environment variable `AUTH_RELEASE`.
     - If authorization times out or fails, Jenkins fails the build.
   - **Timer Trigger**: Jenkins sets the environment variable `AUTH_RELEASE` automatically once checking the timer.
4. **Generate Release Branch**:
   - Jenkins retrieves the last release from GitHub and checks for differences.
   - If differences exist, Jenkins checks the tag, retrieves the last release, and generates the next tag.
   - Jenkins generates the CHANGE_LOG, checks out a new branch, commits, and pushes the changes.
   - Jenkins sets the environment variable `DO_DEPLOY`.
5. **Generate GitHub Release**:
   - If `AUTH_RELEASE` and `DO_DEPLOY` are defined and the status is SUCCESS, Jenkins retrieves tags from GitHub.
   - Jenkins checks stable and prerelease tags and generates release notes.
   - Jenkins retrieves stable and prerelease releases from GitHub.
   - If the prerelease commitish does not exist, Jenkins fails the build.
   - Jenkins clones the JSL repo, checks out the stable branch, and resets from the prerelease commitish.
   - Jenkins force pushes the changes and updates the stable release on GitHub.
   - Jenkins publishes the release to MS Teams.
   - Jenkins updates the prerelease release with the new commitish and tag.
6. **Post-Release Actions**:
   - If the release process fails, Jenkins publishes the failure to MS Teams.

# 6 Design Decisions



- [Design Decisions](#design-decisions)
    - [Use of branch rather than tag](#use-of-branch-rather-than-tag)
    - [Conventional Commits](#conventional-commits)
    - [Reverts](#reverts)
- [CONTENT](#content)



This Section aim to document all the architectural decisions taken

## 6.1 Use of branch rather than tag

| Problem | Constraints | Decision |
| --- | --- | --- |
| At the moment of selecting the best way to keep a “latest" or stable reference it was given the option to use a tag, in order to create a point on time decision to consider as a functional part of the JSL, other option was the use of a branch that will be updated from time to time | :children_crossing: The selected option need to be able to be reseted or force updated without impacting development or solution running. <br> :children_crossing: Tag and branch concept are refered to git as scm tool used on GitHub | The decision taken is to use a branch as per it point to commit objects instead than a single revision, this will allow an easier manipulation of fixes as well as release update as well as the force push, additionally, according to the git glossary the tag is not changed by a commit and therefore may not be suitable for the solution |

## 6.2 Conventional Commits

| Problem | Constraints | Alternatives | Decision |
| --- | --- | --- | --- |
| We need to use an automated release management that is capable to detect what kind of changes were made in order to generate a proper change log and be able to manipulate the releases if required | :children_crossing: The identification of the change as well as the release generation must be automatic | :twisted_rightwards_arrows: Accept any commit but rely on developer to tag the pull requests as they consider <br> :twisted_rightwards_arrows: Use conventional commits types to identify the type | To use conventional commits due that it allow the automatic identification of the change without additional intervention of a developer rather than the identification of the commit. |

## 6.3 Reverts

| Problem | Constraints | Alternatives | Decision |
| --- | --- | --- | --- |
| When a revert is required by any reason, the system may identify issues at sonar level due the not tested coverage or similar issues, this might go againts the controls of the standard pipeline if those are forced skipped. | :children_crossing: Sonar consider a revert as a new code <br> :children_crossing: Revert is done automatically from GitHub | :twisted_rightwards_arrows: Manual issues resolution <br> :twisted_rightwards_arrows: Skip controls for reverts | Reverts automatically created from Github can skip the controls due that if they are required is due an issue detected that is impacting the end users. The code is considered to be already in the code in the past and therefore was already tested. |


# 7 Technical Risks


- [7 Technical Risks](#7-technical-risks)



| Risk/Debt | Description | Mitigation/Additional Info |  |
|:---:|:---:|:---:|---|
| Fast Forward Features  | A fast forward feature is a feat that needs to go to stable due a business decision and should not wait for validation time. This may cause stability issues  | The fast forward features ARE always manual so the risk is assumed and measured. The Engineer should assure that prerelease has the feature as well to avoid issues after force update |  |
| Functional Test must be modular | At the moment the functional testing is capable to execute the whole set of tests instead of a modular solution that execute the affected libraries of a change. This imply that the functional test might take some time to be executed which imply a performance issue | Tech Debt to be implemented |  |
| Migration between Jenkins | Migration of the solution between Jenkins imply that the functional and jsl pipelines need to be on same server to eb able to run the full solution. If not the JSL pipeline and release generation may fail | Consider migration of all impacted jobs when it is required. |  |
| Dated Regression Tests | Dated regression Tests  |  |  |
| Long Term Reverts | In case a revert is required after a feature was introduced to stable, the revert operation might be complex | To create a new fix or feat PR depending in the context that will go to the stable after merge. |  |

# 8 Results

<img align="right" width="200" height="200" src="assets/stats.gif">

From the moment of the launch the general adoption by the High Teams was very good, the teams were able to use the JSL without any major issue and the feedback was very positive as per they were able to have more information on the changes being made across the libraries with the release notes:



![Release Notes](./assets/notification.png)

In terms of the applications adopting the DevSecOps standard, the ammount of onboarded applications increased from 15% to 40% in the first month (July 2022) of adoption of the stable release, which in combination with other actions led to almost 75% of the applications being onboarded by automations or self onboardings by the end of the year.

![Automated Onboarding and Registration Process](./assets/track.png)

Addtionally the ammount of applications being standarized pass from 129 to 292 across the year with an increase on adopted in the quarter of adoption of about 40% compared to the previous quarter (21 new apps against 61) and the applications connected to the system increased from 674 to 1031 with an increase of more than 200 from the adoption of the stable release.

![Applications Standarization](./assets/standard.png)

The ammount of repositories that have outdated libraries was reduced from 534 to 320 by the end of year.

In terms of Sonar the code was pulished enough to have a High Certification on Dora Metrics.

![SonarQube](./assets/sonardebt.png)

Additionally there were some results that were not expected as for example the general adoption of conventional commits across teams, specially those using NodeJs, in order to integrate with automatic release notes.

Finally, please remember that the objective was to be able to automate change management, this change helped not only to fulfil those requirements but to help in the delivery of 84% of the roadmap, increasing from 42% to almost 72% in the first month after delivery.

![Roadmap](./assets/Roadmap.png)


