# AGENTS.md

## Repository overview

This repository is a minimal GitHub project currently centered around deployment and repository hygiene. It contains:

- `README.md` — project landing page
- `SECURITY.md` — security reporting guidance
- `.github/workflows/aws.yml` — Amazon ECR/ECS deployment workflow for pushes to `main`

The repository does not yet contain a full application codebase or established framework structure, so keep changes small, explicit, and easy to review.

## Working conventions for agents

- Prefer minimal, targeted edits over broad refactors.
- Preserve existing repository intent and naming conventions.
- Do not add secrets, credentials, or environment-specific AWS values into source files unless explicitly required by the task.
- If you modify deployment automation, keep it consistent with the existing AWS ECR/ECS workflow and avoid breaking GitHub Actions configuration.
- Keep documentation updates factual and aligned with the actual repository state.

## Development and deployment notes

- The repo is configured for GitHub Actions deployment to Amazon ECS/ECR as defined in `.github/workflows/aws.yml`.
- The workflow triggers on pushes to the `main` branch.
- AWS environment variables in the workflow are placeholders and should only be updated when the actual deployment environment is known.

## Before finalizing work

- Verify that any new file or change matches the repository's minimal structure.
- Check whether the change affects deployment behavior, documentation, or security policy.
- Keep commit scope narrow and explain any assumptions made during edits.

## Safety rules

- Never expose or hardcode AWS access keys, credentials, or secrets.
- Do not remove or disable security policies without a clear requirement.
- If the repo later gains application code, follow the project’s established build/test commands and architecture instead of inventing new patterns.
