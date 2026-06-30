# Cocos Creator — UI Module

Last verified: 2026-06-30 | Engine: 3.8.8

## Core Components

```typescript
import { Canvas, Widget, UITransform, Label, Button, Layout } from 'cc';
```

- `Canvas` — root UI coordinate space; set design resolution
- `Widget` — anchors UI to screen edges (safe area adaptation)
- `UITransform` — size and anchor (replaces old `cc.Node` size APIs from 2.x)

## Patterns

- One Canvas per screen or use multiple Canvas for layered HUD
- Gameplay must not set `Label.string` directly — emit events to UI controllers
- ScrollView + Layout + pooled item prefab for inventory/lists

## Localization

- Load string tables from JSON/CSV assets
- UI controller maps keys → `Label.string`
- RTL: verify font and layout support for target locales

## Official Reference

https://docs.cocos.com/creator/3.8/manual/en/ui-system/
