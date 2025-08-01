# Project template setup

It includes common tooling, configurations, and automation needed to maintain consistency, code quality, and scalability across projects.

## Boilerplate should include

This template sets up essential project tooling out of the box:

- Typescript and other dependent libraries
- ESLint and configuration changes
- Prettier and configuration changes
- Storybook and configuration setup
- Test setup and configuration
- CI/CD
- Repository scanners

## Husky

Use Husky to automate pre-commit checks like linting, formatting, and commit message validation.

Why this is a best practice:

- Prevent broken code from entering the repo

- Enforces local checks, saving CI/CD time and cost

- Ensures developer consistency even before code hits the CI pipeline

[Setup](https://typicode.github.io/husky/)

## Conventional Commits – Commit Message Conventions

Use Conventional Commits for structured and consistent commit messages.

Why this is a best practice:

- Enables automated changelog generation

- Makes it easier to track changes and releases

- Helps tools like semantic-release determine version bumps

[Documentation](https://www.conventionalcommits.org/en/v1.0.0/#specification)

```
 npm install -D @commitlint/{config-conventional,cli}
```

Add `.husky/commit-msg` and `git add commitlint.config.cjs`

Change permissions `chmod +x .husky/commit-msg`

Use `install.mjs` to skip husky on CI

## Github Actions

Automate workflows using GitHub Actions inside .github/workflows.

Benefits:

- Automates build, test, and deployment

- Ensures consistent release pipelines

- Reduces manual errors and improves reliability

`.github/workflows`

### TODO: Conventional changelog (Post merge - Should only run on main)

https://github.com/TrigenSoftware/simple-release/blob/main/GUIDE.md

### TODO: Release (Post merge - Should only run on main)

Semantic release / Simple release setup

### TODO: Deploy (Post merge - Should only run on main)

Trigger only after successful release

### TODO: Repository Protections

To ensure safe and traceable code merges:

- Mark main and release branches (if any) as protected

Require:

- PR reviews if possible
- Successful CI runs before merge
- Disallow force pushes to main

These protections help maintain code integrity and auditability.

## Scanners and Security

Integrate tools like:

- npm audit
- CodeQL
- Snyk (optional)
- License checkers

Why:

- Catch vulnerabilities and dependency issues early
- Ensure legal compliance with open-source licenses

## Create a template repository

Once setup is complete, mark the repo as a template repository:
https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository
https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template

Why:

- Promotes consistency across projects
- Speeds up project bootstrapping
- Reduces time spent on repeated setup work
