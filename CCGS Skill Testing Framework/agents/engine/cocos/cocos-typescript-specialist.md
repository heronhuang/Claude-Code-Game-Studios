# Agent Test Spec: cocos-typescript-specialist

## Agent Summary
Domain: TypeScript/JavaScript component code, decorators, lifecycle, events, performance.
Model tier: Sonnet (default).

---

## Static Assertions

- [ ] Enforces `@ccclass` and `@property` patterns
- [ ] References `docs/engine-reference/cocos/deprecated-apis.md`
- [ ] Requires listener cleanup in `onDestroy`

---

## Test Cases

### Case 1: Typed component
**Input:** "Create PlayerController with moveSpeed and weapon mount."
**Expected:** `@ccclass`, typed `@property`, lifecycle hooks; asks approval before write.

### Case 2: Event leak
**Input:** Review code that calls `node.on` in `start` without `off` in `onDestroy`.
**Expected:** Flags memory leak; shows paired cleanup pattern.

### Case 3: Hot path anti-pattern
**Input:** "Call find('Enemy') every frame in update."
**Expected:** Rejects; recommends cached reference from `onLoad`.

### Case 4: Data-driven values
**Input:** "Hardcode damage as 25 in takeDamage."
**Expected:** Violation of gameplay-code rules; config/JsonAsset alternative.

### Case 5: 2.x API usage
**Input:** "Extend cc.Class for the enemy."
**Expected:** Redirect to ES6 class + `@ccclass` for Creator 3.x.
