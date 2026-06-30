# Cocos Creator — Rendering Module

Last verified: 2026-06-30 | Engine: 3.8.8

## Key APIs

```typescript
import { MeshRenderer, Material, gfx } from 'cc';
```

- Materials reference `.effect` assets
- Modify instance properties at runtime: `materialInstance.setProperty('mainColor', color)`
- Prefer shared materials; use `material` vs `sharedMaterial` intentionally

## Effect Shaders

- File extension: `.effect`
- Structure: `CCEffect` → techniques → passes → `CCProgram` blocks
- Builtin macros: `CC_USE_MODEL`, `CC_DEVICE_CAN_COMPUTE` — check official docs per version

## Performance

- Atlas sprites and UI textures to reduce draw calls
- Mark static geometry for batching where applicable
- Limit real-time lights in 3D mobile targets
- Profile overdraw in native/debug builds

## Official Reference

https://docs.cocos.com/creator/3.8/manual/en/shader/
