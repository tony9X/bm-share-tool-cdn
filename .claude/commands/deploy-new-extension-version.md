---
name: deploy-new-extension-version
description: Workflow command scaffold for deploy-new-extension-version in bm-share-tool-cdn.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /deploy-new-extension-version

Use this workflow when working on **deploy-new-extension-version** in `bm-share-tool-cdn`.

## Goal

Publishes a new version of the Chrome extension by updating the CRX file and related update/installation files.

## Common Files

- `bm-share-tool.crx`
- `index.html`
- `update.xml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Build and sign the new bm-share-tool.crx file.
- Update index.html with new install instructions or version info.
- Update update.xml with the new version and CRX URL.
- Commit and deploy all updated files to the CDN repository.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.