

Good — let’s continue strictly following the **interview brief topics**.

The next part in the brief is very important:

> **Managing Development Pipelines (SDLC)**  
> Experience designing, implementing, and maintaining end-to-end pipelines  
> Tools you’ve used (GitHub Actions, Jenkins, GitLab CI/CD)  
> Testing, code quality, release cycles, rollback strategies

Dev teams often ask something like:

---

# Question 8 — CI/CD Pipeline

### Interview Question

**“How do you design a CI/CD pipeline for a backend application?”**

They want to see if you understand **how code moves from developer → production safely**.

---

# Typical Pipeline Flow

Developer push code  
        ↓  
Pull request  
        ↓  
Code review  
        ↓  
CI pipeline runs  
   - lint  
   - tests  
   - build  
        ↓  
Docker image build  
        ↓  
Push to container registry  
        ↓  
Deploy to staging  
        ↓  
Deploy to production

---

# Example Using Your Stack

You can answer using **NestJS + Cloud Run** (your real experience).

Example pipeline:

Developer pushes code  
↓  
GitHub / GitLab CI triggered  
↓  
Run lint + unit tests  
↓  
Build Docker image  
↓  
Push image to container registry  
↓  
Deploy to Google Cloud Run

---

# What CI (Continuous Integration) Does

CI ensures:

- code compiles
    
- tests pass
    
- code quality checks
    

Example tools:

- GitHub Actions
    
- GitLab CI
    
- Jenkins
    

Example checks:

Lint  
Unit tests  
Security scanning  
Build verification

---

# What CD (Continuous Deployment) Does

CD handles **deployment automation**.

Example steps:

Build container  
↓  
Push to registry  
↓  
Deploy new version  
↓  
Health check  
↓  
Traffic switch

---

# Testing Strategy

They may ask about testing.

Typical levels:

|Type|Purpose|
|---|---|
|Unit test|test functions/services|
|Integration test|test API interactions|
|End-to-end test|test full system|

Example answer:

> “Unit tests validate business logic, while integration tests ensure services interact correctly.”

---

# Code Quality

Tools often used:

- ESLint
    
- Prettier
    
- SonarQube
    

Example answer:

> “Linting and static analysis help catch issues early in the CI pipeline.”


“In a typical CI/CD pipeline, when developers push code or open a pull request, the CI pipeline runs automated checks such as linting, tests, and builds. If everything passes, a container image is built and pushed to a registry. Then the CD pipeline deploys the image to the cloud environment. Using container-based deployment also makes rollbacks easier because we can redeploy a previous stable image if needed.”