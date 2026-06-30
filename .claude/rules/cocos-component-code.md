---
paths:
  - "assets/scripts/**"
  - "src/cocos/**"
  - "src/gameplay/**"
  - "src/ui/**"
---

# Cocos Creator Component Code Rules

Applies when the project engine is Cocos Creator 3.x. Complements generic
`gameplay-code.md` and `ui-code.md` with engine-specific patterns.

## Architecture

- Every gameplay script is a `Component` with `@ccclass` — no loose static utility classes that hold scene state
- Use **composition**: attach behavior components to nodes; avoid deep inheritance trees
- Prefabs are the unit of reuse — scenes orchestrate prefabs, not duplicate node trees
- Cross-system communication via **events** (`node.emit` / `EventTarget`) — never direct UI imports from gameplay

## TypeScript Standards

- Explicit types on `@property` fields and public APIs — avoid `any`
- Unique `@ccclass('Name')` string per component class
- Cache node/component references in `onLoad` — never `find()` in `update()`
- Clean up in `onDestroy`: `node.off()`, `input.off()`, `unscheduleAllCallbacks()`

## Data-Driven Gameplay

- Gameplay values from JSON assets, `JsonAsset`, or config under `assets/config/` — never magic numbers in components
- Use `deltaTime` in `update()` for all time-based movement and cooldowns

## Asset Loading

- Prefer **Asset Bundles** over bloated `resources/` folders
- Async load only — no blocking the main thread on large assets
- Release bundle assets when scenes unload

## Performance

- Disable idle components: `this.enabled = false`
- Use `NodePool` for projectiles, list items, damage numbers, VFX
- Prefer `tween()` over manual per-frame interpolation

## Before Using Engine APIs

Consult `docs/engine-reference/cocos/VERSION.md` and `deprecated-apis.md`.
Do not use Creator 2.x APIs (`cc.Class`, `cc.loader`) in 3.x code.

## Examples

**Correct** (data-driven, typed property):

```typescript
@property({ type: JsonAsset })
public combatConfig: JsonAsset | null = null;

start(): void {
  const baseDamage = this.combatConfig?.json?.baseDamage ?? 10;
}
```

**Incorrect** (hardcoded, untyped):

```typescript
start(): void {
  const baseDamage = 25; // VIOLATION: hardcoded gameplay value
}
```
