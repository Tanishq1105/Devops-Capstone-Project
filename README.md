# DevOps Capstone Project

## Build Status
[![CI Build](https://github.com)](https://github.com)
[![License](https://shields.io)](https://opensource.org)
[![Python 3.9](https://shields.io)](https://shields.io)

This repository contains my completed capstone project for the [**IBM-CD0285EN-SkillsNetwork DevOps Capstone Project**](https://coursera.org) course, part of the [**IBM DevOps and Software Engineering Professional Certificate**](https://coursera.org).

---

## Developer Details
* **Developer:** Tanishq Kumar Sinha
* **GitHub Profile:** [https://github.com/Tanishq1105](https://github.com/Tanishq1105)
* **Project Completion Date:** June 2026
* **Status:** Fully Implemented (REST API, CI/CD Pipeline, Security Headers, Dockerization, and Kubernetes Deployment)

---

## Development Environment

These labs are executed in the IBM Developer Skills Network Cloud IDE with OpenShift. 

To initialize the environment, source the setup script:

```bash
source bin/setup.sh
```

This installs Python 3.9, modifies the bash prompt, creates a Python virtual environment, and activates it.

Your prompt should look like this:
```bash
(venv) theia:project$
```

## Useful Commands

### Activate the Python 3.9 Virtual Environment
```bash
source ~/venv/bin/activate
```

### Installing Python Dependencies
```bash
make install
```

### Starting the Postgres Docker Container
```bash
make db
```

---

## Project Layout

The microservice follows the **Model-View-Controller (MVC)** pattern. Database code and business logic are in `models.py`, while RESTful routing is in `routes.py`.

```text
├── service         <- microservice package
│   ├── common/     <- common log and error handlers
│   ├── config.py   <- Flask configuration object
│   ├── models.py   <- code for the persistent model
│   └── routes.py   <- code for the REST API routes
├── setup.cfg       <- tools setup config
└── tests                       <- folder for all of the tests
    ├── factories.py            <- test factories
    ├── test_cli_commands.py    <- CLI tests
    ├── test_models.py          <- model unit tests
    └── test_routes.py          <- route unit tests
```

## Data Model

The Account model contains the following fields:

| Name | Type | Optional |
|------|------|----------|
| id | Integer| False |
| name | String(64) | False |
| email | String(64) | False |
| address | String(256) | False |
| phone_number | String(32) | True |
| date_joined | Date | False |

---

## Implemented Tasks

I have completed this microservice by implementing REST APIs for `READ`, `UPDATE`, `DELETE`, and `LIST` while maintaining **over 95%** code coverage.

* **Sprint 1**: REST API development and TDD testing.
* **Sprint 2**: GitHub Actions CI Pipeline setup, Flake8/Pylint integration, and Talisman security header configurations.
* **Sprint 3**: Application dockerization, local K3D/Kubernetes testing, and Tekton CD pipeline deployment.

---

## Local Kubernetes Development

This repo can be used for local Kubernetes development with Docker Desktop and VS Code Remote Containers.

1. Bring up a local K3D Kubernetes cluster:
    ```bash
    make cluster
    ```
2. Install Tekton:
    ```bash
    make tekton
    ```
3. Install the ClusterTasks:
    ```bash
    make clustertasks
    ```

---

## Original Course Author
[John Rofrano](https://coursera.org), Senior Technical Staff Member, DevOps Champion, @ IBM Research, and Instructor @ Coursera

## License
Licensed under the Apache License. See [LICENSE](LICENSE)

### © IBM Corporation 2022. All rights reserved.
