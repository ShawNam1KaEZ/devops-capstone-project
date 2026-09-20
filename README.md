# devops-capstone-project

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

## Project Overview

`devops-capstone-project` is a customer accounts microservice developed as part of the IBM DevOps and Software Engineering Professional Certificate capstone project. The goal of this service is to manage customer account records for an e-commerce platform by providing a well-formed REST API that interacts with a PostgreSQL database storing basic customer information (names, emails, addresses, and phone numbers).

As part of the initial planning phase (Sprint 0), Agile planning techniques are applied using GitHub Issues and GitHub Projects Kanban boards to establish user stories, backlog refinement, and sprint allocation.

---

## Lab Objectives & Agile Planning Setup

This project uses Agile methodologies to manage development tasks, structured into the following exercises:

1. **Repository Setup:** Created public repository `devops-capstone-project` from the initial starter template.
2. **GitHub Kanban Board:** Established a project board with 7 core pipelines:
   - `New issues`
   - `Icebox`
   - `Product backlog`
   - `Sprint backlog`
   - `In progress`
   - `Review/QA`
   - `Done`
3. **User Story Template:** Configured standard issue templates under `.github/ISSUE_TEMPLATE/user-story.md` featuring standard Gherkin syntax for Acceptance Criteria.
4. **Product Backlog & Triage:** Created and categorized initial user stories across sprint iterations (`Product Backlog` vs. `Icebox`).
5. **Backlog Refinement:** Applied label categorization (`enhancement`, `technical debt`) and story prioritization.
6. **Sprint 1 Planning:** Created sprints, assigned story points ($3, 5, 8, 13$), and populated the initial `Sprint Backlog`.

---

## User Stories & Backlog Structure

| Story Title | Classification / Label | Estimate | Target Sprint | Pipeline Status |
| :--- | :--- | :---: | :---: | :---: |
| Setup the development environment | Technical Debt | 3 | Sprint 1 | Sprint Backlog |
| Read an account from the service | Enhancement | 5 | Sprint 1 | Sprint Backlog |
| Update an account in the service | Enhancement | 5 | Sprint 1 | Sprint Backlog |
| Delete an account from the service | Enhancement | 3 | Sprint 1 | Sprint Backlog |
| List all accounts in the service | Enhancement | 5 | Sprint 1 | Sprint Backlog |
| Containerize your microservice using Docker | Enhancement | 8 | Future Sprint | Icebox |
| Deploy your Docker image to Kubernetes | Enhancement | 13 | Future Sprint | Icebox |

---

## Data Model

The `Account` model managed by this microservice includes the following fields:

| Field Name | Type | Optional | Description |
| :--- | :--- | :---: | :--- |
| `id` | Integer | False | Primary key |
| `name` | String(64) | False | Full name of the customer |
| `email` | String(64) | False | Customer contact email address |
| `address` | String(256) | False | Physical address |
| `phone_number` | String(32) | True | Contact phone number |
| `date_joined` | Date | False | Account creation timestamp |

---

## Microservice Architecture & Directory Structure

```text
.
├── .github/
│   └── ISSUE_TEMPLATE/
│       └── user-story.md     <- Standardized Markdown issue template
├── service/                  <- Microservice Python package
│   ├── common/               <- Common log and error handlers
│   ├── config.py             <- Flask configuration settings
│   ├── models.py             <- SQLAlchemy database persistent model
│   └── routes.py             <- REST API routing definitions
├── tests/                    <- Unit test suite
│   ├── factories.py          <- Fake data generator factories
│   ├── test_cli_commands.py  <- CLI unit tests
│   ├── test_models.py        <- Model layer unit tests
│   └── test_routes.py        <- REST API endpoint unit tests
├── setup.cfg                 <- Tool and linter configurations
└── README.md                 <- Project overview documentation
