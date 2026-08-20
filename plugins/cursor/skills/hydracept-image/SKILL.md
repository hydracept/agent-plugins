---
name: hydracept-image
description: >
  Generate production game images through Hydracept image.generate.v1 — transparent
  sprites, icons, variants, and receipted jobs.
---

# Hydracept Image

Production image generation judgment for game assets.

## Capability

Use `image.generate.v1` through `hydracept_submit_job`.

## Common options

- Transparent PNG sprites/icons: `requestTransparentOutput: true`
- Multiple takes: `variantCount` between 2 and 4
- Sheet workflows: prefer the `hydracept-sheet` skill for cohesive families

## Workflow

1. Describe the asset need in game terms, not provider terms
2. Submit a job with project context from the workspace
3. Poll until `succeeded`
4. Download artifacts to the workspace and inspect transparency or silhouette locally
5. Keep the receipt for cost and provenance review
