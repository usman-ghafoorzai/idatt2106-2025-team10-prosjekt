# Security and Public Repository Review

## Scope
This document is a concise security/public-repository review of **Krisefikser** as a university team project.  
Assessment basis: static repository analysis and documented project context (course/demo oriented).

## Summary
The repository shows solid engineering effort for a student full-stack project, but several security practices are not suitable for public or production-facing use.  
Overall status: **acceptable for university/demo use with clear caveats**, **not production-ready as-is**.

## Findings

### 1. Committed JWT secret and security configuration
- Description: Security-sensitive authentication configuration is committed in repository files.
- Potential risk: Token forgery risk, weaker trust boundary, and accidental reuse across environments.
- Recommended improvement: Move secrets to environment variables/secret manager; keep only safe defaults in versioned config; rotate existing secrets.
- Acceptable for university/demo project: **Partially acceptable** for local coursework, **not acceptable** for public long-term use.

### 2. Committed database/email/reCAPTCHA-related configuration
- Description: Repository includes committed connection/configuration details related to database, mail, and captcha flows.
- Potential risk: Environment leakage, easier reconnaissance, and accidental misuse of shared services.
- Recommended improvement: Replace with `.env.example` and placeholder values; document required variables centrally; isolate demo infrastructure from personal/shared accounts.
- Acceptable for university/demo project: **Partially acceptable** for controlled coursework, but should be cleaned before broader public exposure.

### 3. Sensitive logging in captcha verification flow
- Description: Captcha verification logging includes sensitive request/secret-related values.
- Potential risk: Secret/token exposure in logs, especially if logs are retained or shared.
- Recommended improvement: Remove sensitive fields from logs; use structured logging with redaction; keep only high-level success/failure events.
- Acceptable for university/demo project: **Generally not acceptable**, even in demos, because logging leaks can propagate easily.

### 4. Hardcoded login credentials in Cypress tests
- Description: End-to-end test code contains hardcoded account credentials.
- Potential risk: Credential reuse exposure, account misuse, and poor secret hygiene patterns for team members.
- Recommended improvement: Use environment-provided test credentials in CI/local runs; use seeded disposable test users; avoid committing fixed credentials.
- Acceptable for university/demo project: **Partially acceptable** if credentials are disposable and isolated, but still a practice to replace.

### 5. Sentry DSN committed and `sendDefaultPii` enabled
- Description: Client monitoring setup includes committed DSN configuration and personal-data collection enabled.
- Potential risk: Unintended telemetry collection, privacy concerns, and misconfigured monitoring in public forks.
- Recommended improvement: Move monitoring keys/config to environment variables; disable or strictly scope PII collection for demo environments; document data-handling intent.
- Acceptable for university/demo project: **Partially acceptable** for observability learning, but privacy defaults should be stricter.

### 6. Admin/demo credentials documented in backend README
- Description: README documentation includes explicit demo/admin-style credentials.
- Potential risk: Credential scraping and misuse if reused elsewhere; poor public security posture.
- Recommended improvement: Remove static credentials from docs; describe account bootstrapping scripts or one-time local setup instead.
- Acceptable for university/demo project: **Partially acceptable** for supervised classroom demos, not recommended in public repository docs.

### 7. Missing centralized environment variable documentation
- Description: Required runtime variables are spread across files and not documented in one canonical location.
- Potential risk: Misconfiguration, insecure local workarounds, and inconsistent team setup.
- Recommended improvement: Add centralized setup docs plus `.env.example` files (backend/frontend) with clear variable purpose and safe defaults.
- Acceptable for university/demo project: **Common but improvable**; acceptable short-term, should be addressed for portfolio quality.

### 8. Course/demo-oriented configuration baseline
- Description: Repository configuration appears optimized for coursework and demonstration rather than hardened deployment.
- Potential risk: False confidence if reused as a production baseline.
- Recommended improvement: Keep explicit non-production disclaimer; add a "hardening checklist" for any future real deployment.
- Acceptable for university/demo project: **Acceptable**, provided scope and limitations are clearly stated.

## Recommended Next Steps (Documentation-First)
1. Add centralized environment setup docs and `.env.example` files with placeholders only.
2. Remove hardcoded/demo credentials from repository documentation and tests.
3. Sanitize sensitive logging paths and document logging policy.
4. Add a short security posture section in the root README clarifying non-production status and required hardening.

## Final Note
Krisefikser is a strong academic team project and portfolio artifact.  
Its current security posture is appropriate for learning and demonstration contexts, but it requires hardening before any production or public-service deployment.
