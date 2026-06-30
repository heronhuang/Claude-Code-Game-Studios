# Cocos Creator — Current Best Practices

Last verified: 2026-06-30 | Engine: Cocos Creator 3.8.8

Practices for Cocos Creator 3.8.x that differ from older tutorials or Creator 2.x.

## Components and TypeScript

- Use **TypeScript** as the default language for new projects
- Enable `strict` in `tsconfig.json` where project template allows
- Unique `@ccclass('Name')` per component — required for serialization
- Use `@property({ type: Node })` for node references, not raw strings

## Asset Loading

- **Asset Bundles** for scalable content — avoid overusing `resources/`
- `assetManager.loadBundle` → `bundle.load(path, Type, callback)`
- Release with `assetManager.releaseAsset` when bundles are unloaded
- Remote bundles: configure server address in build settings + version manifest

## Object Pooling

```typescript
import { NodePool, instantiate, Prefab } from 'cc';

const pool = new NodePool();
// acquire: pool.get() ?? instantiate(prefab)
// release: pool.put(node)
```

## Animation and Motion

- Prefer `tween()` from `'cc'` over manual `update` interpolation
- `Animation` component for skeletal/keyed animation; tweens for UI and simple motion

## Events

- System input: `input.on(Input.EventType.TOUCH_END, ...)`
- Custom gameplay: `node.emit` / `node.on` with cleanup in `onDestroy`
- Global bus: dedicated `EventTarget` component — not raw `window` globals

## UI (3.8)

- `Canvas` + `Widget` for resolution adaptation
- `Layout` for dynamic lists — pair with `NodePool` for virtualized scroll content
- Localization: external string tables, not hardcoded `Label.string`

## Physics

- 2D: Box2D via `RigidBody2D` / `Collider2D`
- 3D: Bullet/cannon.js via `RigidBody` / `Collider`
- Use physics layers and collision matrix in Project Settings

## Build and Platforms

- Web: primary for rapid iteration; watch bundle size
- Native: rebuild after engine updates; test JSB on device, not only editor
- Mini-games (WeChat, etc.): separate build templates — confirm subpackage limits early
