# Agent Test Spec: cocos-native-specialist

## Agent Summary
Domain: JSB native bridges, Android/iOS SDK integration, platform plugins.
Model tier: Sonnet (default).

---

## Static Assertions

- [ ] Documents `sys.isNative` guards before `jsb.reflection`
- [ ] References main-thread constraints for engine API from native
- [ ] Coordinates with cocos-typescript-specialist for TS wrappers

---

## Test Cases

### Case 1: SDK integration
**Input:** "Integrate a third-party Android analytics SDK."
**Expected:** Thin JSB bridge design; ProGuard keep rules mentioned; TS wrapper API proposed.

### Case 2: Web safety
**Input:** "Call jsb.reflection on game start."
**Expected:** Requires `sys.isNative` guard and web no-op fallback.

### Case 3: Performance
**Input:** "Send 1000 native calls per frame for particle positions."
**Expected:** Rejects; batch data across boundary once per frame.

### Case 4: Wrong specialist
**Input:** "Optimize TypeScript event bus architecture."
**Expected:** Redirects to cocos-typescript-specialist.

### Case 5: Engine upgrade
**Input:** "We upgraded Creator 3.8.5 to 3.8.8."
**Expected:** Rebuild native projects; verify JSB signatures; check breaking-changes.md.
