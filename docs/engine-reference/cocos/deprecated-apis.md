# Cocos Creator — Deprecated APIs

Last verified: 2026-06-30 | Engine: Cocos Creator 3.8.8

## Do Not Use → Use Instead

| Deprecated | Replacement | Context |
|------------|-------------|---------|
| `cc.Class` (2.x style) | `@ccclass` decorator + ES6 class | All new components |
| `cc.loader` | `assetManager`, `resources` | Asset loading |
| `cc.director` (global) | `import { director } from 'cc'` | Scene management |
| `cc.game` (global) | `import { game } from 'cc'` | Lifecycle |
| `node.runAction` (2.x) | `tween(node).to(...).start()` | Animation |
| `cc.instantiate` (global) | `import { instantiate } from 'cc'` | Prefab spawn |
| `getComponent('StringName')` | `getComponent(ComponentClass)` | Type-safe lookup |
| Synchronous large `resources.load` | `resources.load` with callback or `assetManager` async | Performance |
| Deep `find('path')` every frame | `@property` references or cached lookup in `onLoad` | Performance |

## Creator 2.x Only — Never in 3.x Projects

- `cc.Animation` clip API from 2.x without migration
- `cc.Sprite` direct property patterns from 2.x docs
- `cc.sys` global — use `import { sys } from 'cc'`

## Verification

If an API appears in old tutorials but not in `docs.cocos.com/creator/3.8/api`,
treat it as deprecated and search this table plus official migration guides.
