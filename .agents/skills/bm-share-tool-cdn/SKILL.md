```markdown
# bm-share-tool-cdn Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the development, deployment, and maintenance patterns for the `bm-share-tool-cdn` repository. The project is written in TypeScript and serves as a CDN for distributing the `bm-share-tool` Chrome extension. It includes versioned extension files, update manifests, and installation instructions. The repository follows specific coding conventions and a structured workflow for deploying new extension versions.

## Coding Conventions

### File Naming
- Use **camelCase** for filenames.
  - Example: `updateXml.ts`, `bmShareTool.crx`

### Import Style
- Use **relative imports** for referencing modules.
  ```typescript
  import { updateXml } from './updateXml';
  ```

### Export Style
- Use **named exports**.
  ```typescript
  // updateXml.ts
  export function updateXml(version: string) {
    // ...
  }
  ```

### Commit Patterns
- Commits are freeform, sometimes prefixed with `deploy` or `init`.
  - Examples:
    - `deploy: update crx`
    - `init repo`
    - `update index.html`

## Workflows

### Deploy New Extension Version
**Trigger:** When releasing a new version of the browser extension  
**Command:** `/deploy-extension-version`

1. **Build and sign the new CRX file**
   - Generate `bm-share-tool.crx` for the new version.
2. **Update installation instructions**
   - Edit `index.html` to reflect the new version or update install instructions.
3. **Update the update manifest**
   - Edit `update.xml` with the new version number and CRX download URL.
   - Example snippet:
     ```xml
     <updatecheck codebase="https://cdn.example.com/bm-share-tool.crx" version="1.2.3" />
     ```
4. **Commit and deploy**
   - Commit all updated files (`bm-share-tool.crx`, `index.html`, `update.xml`) to the CDN repository.
   - Example commit message:
     ```
     deploy: v1.2.3 release
     ```
   - Push changes to deploy.

## Testing Patterns

- **Testing Framework:** Unknown (not detected)
- **Test File Pattern:** Files named with `*.test.*`
  - Example: `updateXml.test.ts`
- **Style:** Place test files alongside source files, using the `.test.` infix.

## Commands

| Command                   | Purpose                                                |
|---------------------------|--------------------------------------------------------|
| /deploy-extension-version | Deploy a new version of the Chrome extension to the CDN |
```
