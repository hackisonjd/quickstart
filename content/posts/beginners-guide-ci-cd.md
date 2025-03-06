---
title: A Beginner's Guide to CI and CD
date: 2025-03-05
draft: false
tags:
- uug-talks
---
# What is CI/CD?

**Continuous Integration (CI)**: Automate the process of merging new code into a shared repository, early and often.
- Each commit triggers an automated workflow on a server that runs a series of tasks to ensure new code doesn't break the codebase.
- A natural evolution of test-driven development.

**Continuous Deployment/Delivery (CD)**: One step further than CI, code that passes all tests is automatically deployed to production, without manual intervention.
- Significantly harder to pull off, typically only used on basic, stateless systems.
	- Web servers and APIs, which are easy to rollback if something breaks
- The more complex and stateful the system is, the harder it is to make it truly rely on CD.

Most developer platforms have their own CI/CD solutions (GitHub Actions), but many people also self-host these solutions themselves (a topic for another time).

# The Theory

The idea is to automate the testing and delivery of software from the initial code commit all the way through to deployment.

### Why do this?

- Limits amount of human intervention required to build a project. (Automate once, be "lazy" forever)
- Allows for multiple people, with drastically different roles, to deploy code without conflicts ("merge hell")
- For large corporations, time is money!

**Is it worth it?** It depends!

# What Are We Doing?

We will be setting up a sample GitHub repository, and setting up a GitHub Actions configuration file to ensure that code will be checked and, if it passes the tests, will deploy a new build automatically.


**Terminology to understand:**
- **Events**: Trigger for a workflow. "When new code is pushed to this repository, run the below job."
- **Jobs**: A series of *steps* and *actions* that only run once triggered by an event (typically linters and testing software).
- **Runners**: An isolated environment (container) that runs our code throughout the CI/CD process.

```yaml
name: Lint

on: push

jobs:
  lint:
    name: Lint code base
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Run linter
        uses: github/super-linter@v3
        env:
          DEFAULT_BRANCH: main
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```