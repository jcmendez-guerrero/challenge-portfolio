# 3 System Context and Scope

<!-- TOC -->

- [3 System Context and Scope](#3-system-context-and-scope)
    - [3.1 System Context Diagram](#31-system-context-diagram)

<!-- /TOC -->

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