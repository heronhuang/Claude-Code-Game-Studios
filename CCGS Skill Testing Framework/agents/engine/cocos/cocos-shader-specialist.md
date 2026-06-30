# Agent Test Spec: cocos-shader-specialist

## Agent Summary
Domain: Cocos Effect (.effect) shaders, materials, rendering performance.
Model tier: Sonnet (default).

---

## Static Assertions

- [ ] References `.effect` file structure (CCEffect, CCProgram)
- [ ] References `docs/engine-reference/cocos/modules/rendering.md`
- [ ] Naming convention: `category-name.effect`

---

## Test Cases

### Case 1: Water shader request
**Input:** "Create a stylized water surface shader for mobile."
**Expected:** `.effect` structure, mobile precision notes, documents draw/batch impact.

### Case 2: Wrong engine shader
**Input:** "Write a .gdshader for Godot glow."
**Expected:** Redirects to Godot specialist or Cocos Effect equivalent.

### Case 3: Performance review
**Input:** "Shader samples 8 textures per fragment."
**Expected:** Flags mobile risk; suggests reduction or LOD variant.

### Case 4: Material runtime update
**Input:** "How do scripts change shader color at runtime?"
**Expected:** `materialInstance.setProperty` pattern; defers script details to TS specialist.

### Case 5: Protocol
**Input:** "Write env-water.effect now."
**Expected:** Proposes structure first; asks approval before write.
