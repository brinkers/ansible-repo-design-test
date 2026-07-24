# Ansible AAP Pipeline Sandbox

This repository is a sandbox for testing a GitHub-based promotion pipeline for Ansible Automation Platform (AAP). It works fully without AAP connected.

## Branching Model

- `develop` — Dev environment, auto-updated
- `main` — Prod environment, protected
- Tags (`v*`) — Immutable release versions

## Workflows

### CI - Develop
Runs ansible-lint on every push to `develop`.

### Promote to Prod
Manually triggered workflow that:
1. Creates a PR from `develop` → `main`
2. Waits for approval
3. Merges the PR
4. Creates a version tag

### AAP Sync (optional)
Triggers an AAP project update when a tag is created.

## How to Use

1. Push changes to `develop`
2. Run "Promote to Prod" workflow manually
3. Approve the PR
4. Tag is created automatically
5. (Optional) AAP syncs the new version

This repo is safe for experimentation.