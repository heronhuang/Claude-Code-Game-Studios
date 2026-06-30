# Agent Test Spec: cocos-specialist

## Agent Summary
Domain: Cocos Creator component/node architecture, asset bundles, events, TypeScript vs JSB decisions.
Does NOT own: line-level TypeScript implementation (delegates to cocos-typescript-specialist).
Model tier: Sonnet (default).

---

## Static Assertions (Structural)

- [ ] `description:` references Cocos Creator architecture / components / bundles
- [ ] Agent references `docs/engine-reference/cocos/VERSION.md`
- [ ] Delegation to cocos-typescript-specialist, cocos-shader-specialist, cocos-native-specialist documented

---

## Test Cases

### Case 1: Component vs manager decision
**Input:** "Should player inventory be a Component on the player node or a separate manager?"
**Expected:** Pattern guide with prefab composition, event bus trade-offs; no full implementation code.

### Case 2: Wrong-engine redirect
**Input:** "Write a MonoBehaviour for Unity that loads Addressables."
**Expected:** Identifies Unity pattern; maps to Cocos Asset Bundle + Component lifecycle equivalent.

### Case 3: Version awareness
**Input:** "Use cc.loader to load the player prefab."
**Expected:** Flags deprecated 2.x API; directs to `assetManager` / `resources.load` per deprecated-apis.md.

### Case 4: Bundle strategy
**Input:** "We have 2GB of level content. How should we structure assets?"
**Expected:** Recommends Asset Bundles over `resources/`; mentions release and remote bundle options.

### Case 5: Protocol compliance
**Input:** "Implement the combat system now."
**Expected:** Asks architecture questions; requests approval before writing files.
