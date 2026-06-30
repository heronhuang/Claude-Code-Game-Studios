# Cocos Creator — Version Reference

| Field | Value |
|-------|-------|
| **Engine Version** | Cocos Creator 3.8.8 |
| **Runtime** | cocos-engine 3.8.8 |
| **Release Date** | December 2025 |
| **Project Pinned** | 2026-06-30 |
| **Last Docs Verified** | 2026-06-30 |
| **LLM Knowledge Cutoff** | May 2025 |
| **Risk Level** | MEDIUM — 3.8.6+ features may be incomplete in training data |

## Knowledge Gap Warning

The LLM's training data covers Cocos Creator 3.x broadly but may miss
patch-level API changes in 3.8.6–3.8.8 and the COCOS 4 open-source transition
(January 2026). Always cross-reference this directory before suggesting API calls.

## Ecosystem Note (2026)

COCOS 4 represents the open-source engine evolution of Cocos Creator 3.x with
MIT licensing. **Cocos Creator 3.8.x remains the stable editor toolchain** for
most production projects. Do not assume COCOS 4 CLI replaces Creator 3.8 workflows
without verifying project migration status.

## Post-Cutoff Highlights

| Area | Change | Risk |
|------|--------|------|
| Engine branding | COCOS 4 open source (engine/editor split) | LOW for 3.8.x projects |
| Native | HarmonyOS export improvements in 3.8.x | MEDIUM |
| Rendering | Effect/shader incremental updates per patch | MEDIUM |
| Legacy 2.x | `cc.Class`, `cc.loader` — never use in 3.x | HIGH if mixed |

## Verified Sources

- Official docs: https://docs.cocos.com/creator/3.8/manual/en/
- Engine repo: https://github.com/cocos/cocos-engine
- 3.8.8 release: https://www.cocos.com/en/creator-download
- API reference: https://docs.cocos.com/creator/3.8/api/en/

## Module Index

| Module | File |
|--------|------|
| Rendering | `modules/rendering.md` |
| Physics | `modules/physics.md` |
| Input | `modules/input.md` |
| UI | `modules/ui.md` |
| Audio | `modules/audio.md` |
