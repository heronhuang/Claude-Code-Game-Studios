# Cocos Creator — Breaking Changes

Last verified: 2026-06-30 | Engine: Cocos Creator 3.8.8

Version transitions that affect code written against pre-3.8 or Creator 2.x knowledge.

## Creator 2.x → 3.x (HIGH — do not mix patterns)

| Old (2.x) | New (3.x) | Notes |
|-----------|-----------|-------|
| `cc.Class({ extends: cc.Component })` | `@ccclass` + `extends Component` | ES6 class + decorators |
| `cc.loader.load` | `resources.load` / `assetManager.loadAny` | Asset Manager pipeline |
| `cc.director` global | `import { director } from 'cc'` | Modular imports |
| `cc.v2()` / `cc.v3()` | `new Vec2()` / `new Vec3()` | From `'cc'` module |
| `this.node.on('click', ...)` (2.x events) | `Node.EventType` constants | Typed event names |

## 3.7 → 3.8

- Review custom Effect shaders after engine upgrade — builtin macro changes possible
- Rebuild native projects (Android/iOS) after every minor engine bump
- Verify JSB `callStaticMethod` signatures if using native SDK bridges

## 3.8.x Patch Notes (verify per upgrade)

- Check official release notes for physics, rendering, and build-template changes
- Run `/setup-engine refresh` after pinning a new 3.8.x patch

## Migration Checklist

1. Update `package.json` / Creator editor to target version
2. Reimport all custom Effects and materials
3. Rebuild native platforms from clean template
4. Run smoke tests on Web + primary native target
5. Update `VERSION.md` pin date
