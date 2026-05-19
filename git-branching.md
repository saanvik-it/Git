# GitFlow Branching Strategy

GitFlow is one of the most widely used Git branching models for managing:
- Features
- Releases
- Hotfixes
- Production deployments

It provides a structured workflow for teams working on large projects.

---

# Why GitFlow?

GitFlow helps:
- Organize development
- Separate production and development code
- Manage releases cleanly
- Handle emergency fixes safely
- Improve collaboration

---

# GitFlow Main Branches

## 1. main (or master)

- Production-ready code
- Stable releases only
- Tagged with versions

Example:
```text
v1.0
v1.1
v2.0
```

---

## 2. develop

- Main integration branch
- Contains latest development changes
- Features are merged here first

---

# Supporting Branches

## 1. feature/*

Used for:
- New features
- Enhancements

Created from:
```text
develop
```

Merged back into:
```text
develop
```

Example:
```text
feature/login
feature/payment
feature/dashboard
```

---

## 2. release/*

Used for:
- Release preparation
- Final testing
- Bug fixes before production

Created from:
```text
develop
```

Merged into:
```text
main and develop
```

Example:
```text
release/1.0.0
```

---

## 3. hotfix/*

Used for:
- Critical production fixes

Created from:
```text
main
```

Merged into:
```text
main and develop
```

Example:
```text
hotfix/payment-fix
```

---

# GitFlow Architecture Diagram

```text
                                      +----------------+
                                      |     main       |
                                      | Production     |
                                      +----------------+
                                               ▲
                                               │
                              release merge    │   hotfix merge
                                               │
                  +----------------------------+--------------------------+
                  │                                                       │
                  │                                                       │
          +---------------+                                      +----------------+
          | release/1.0   |                                      | hotfix/1.0.1   |
          +---------------+                                      +----------------+
                  ▲                                                       ▲
                  │                                                       │
                  │                                                       │
                  │                                                       │
          +---------------------------------------------------------------+
          |
          |
+----------------+
|    develop     |
| Integration    |
+----------------+
      ▲
      │
      │
+-----+------+-------------------+--------------------+
|            |                   |                    |
|            |                   |                    |
▼            ▼                   ▼                    ▼

+-----------+  +---------------+  +---------------+  +----------------+
| feature/  |  | feature/      |  | feature/      |  | feature/       |
| login     |  | payment       |  | dashboard     |  | notifications  |
+-----------+  +---------------+  +---------------+  +----------------+
```

---

# GitFlow Workflow

## Step 1 – Create Feature Branch

```bash
git checkout develop
git checkout -b feature/login
```

---

## Step 2 – Develop Feature

```bash
git add .
git commit -m "Added login functionality"
```

---

## Step 3 – Merge Feature into Develop

```bash
git checkout develop
git merge feature/login
```

---

## Step 4 – Create Release Branch

```bash
git checkout develop
git checkout -b release/1.0.0
```

---

## Step 5 – Merge Release into Main

```bash
git checkout main
git merge release/1.0.0
```

---

## Step 6 – Tag Release

```bash
git tag -a v1.0.0 -m "Production release 1.0.0"
```

---

## Step 7 – Merge Back into Develop

```bash
git checkout develop
git merge release/1.0.0
```

---

# Hotfix Workflow

## Step 1 – Create Hotfix Branch

```bash
git checkout main
git checkout -b hotfix/payment-fix
```

---

## Step 2 – Fix Issue

```bash
git add .
git commit -m "Fixed payment production issue"
```

---

## Step 3 – Merge into Main

```bash
git checkout main
git merge hotfix/payment-fix
```

---

## Step 4 – Merge into Develop

```bash
git checkout develop
git merge hotfix/payment-fix
```

---

# GitFlow Lifecycle Diagram

```text
Feature Development
        ↓
feature/*
        ↓
develop
        ↓
release/*
        ↓
main
        ↓
Production

Emergency Fix
        ↓
hotfix/*
        ↓
main + develop
```

---

# Advantages of GitFlow

- Structured workflow
- Stable production branch
- Better release management
- Supports parallel development
- Easy hotfix handling
- Clear branch separation

---

# Disadvantages of GitFlow

- Complex for small teams
- Too many long-lived branches
- Slower delivery for rapid deployments
- Not ideal for pure continuous deployment

---

# When to Use GitFlow

Recommended for:
- Enterprise applications
- Large teams
- Scheduled releases
- Multiple environments
- Strict release management

---

# When NOT to Use GitFlow

Avoid for:
- Small startups
- Fast CI/CD environments
- Continuous deployment-only projects

Alternative:
- Trunk-based development

---

# GitFlow Best Practices

## Use Naming Standards

```text
feature/*
release/*
hotfix/*
bugfix/*
```

---

## Protect Main Branch

Enable:
- PR approvals
- Branch protection
- CI checks

---

## Keep Feature Branches Small

Smaller branches:
- Easier reviews
- Fewer conflicts

---

## Delete Merged Branches

```bash
git branch -d feature/login
```

---

# GitFlow vs Trunk-Based Development

| GitFlow | Trunk-Based |
|---|---|
| Multiple long-lived branches | Single main branch |
| Better release control | Faster deployments |
| More structured | Simpler |
| Slower CI/CD | Faster CI/CD |

---

# GitFlow Interview Questions

## Q1. What is GitFlow?

GitFlow is a branching strategy that uses separate branches for:
- Features
- Releases
- Hotfixes
- Production

---

## Q2. Difference between main and develop?

| main | develop |
|---|---|
| Production code | Integration code |

---

## Q3. What is a release branch?

A temporary branch used for release preparation and final testing.

---

## Q4. What is a hotfix branch?

A branch created from main to fix urgent production issues.

---

## Q5. Why merge hotfix into develop also?

To ensure production fixes are included in future releases.

---

# Real-World Example

```text
Production:
main

Current Development:
develop

New Features:
feature/login
feature/payment

Upcoming Release:
release/2.0

Critical Production Bug:
hotfix/auth-fix
```

---

# Conclusion

GitFlow is a powerful and structured branching strategy suitable for:
- Enterprise DevOps
- Large development teams
- Controlled production releases

Understanding GitFlow is important for:
- DevOps Engineers
- Developers
- Release Managers
- Platform Engineers

It is one of the most commonly asked topics in DevOps and Git interviews.

---
