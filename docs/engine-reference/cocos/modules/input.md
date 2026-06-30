# Cocos Creator — Input Module

Last verified: 2026-06-30 | Engine: 3.8.8

## System Input

```typescript
import { input, Input, EventKeyboard, KeyCode } from 'cc';

input.on(Input.EventType.KEY_DOWN, this.onKeyDown, this);
input.on(Input.EventType.TOUCH_START, this.onTouchStart, this);
```

- Always `input.off(...)` in `onDestroy`
- Multi-touch: use event `getTouches()` / touch ID APIs

## UI Input

- `Button` component `clickEvents` for designer-wired handlers
- For custom UI: `node.on(Node.EventType.TOUCH_END, ...)`

## Gamepad

- Check `input` gamepad APIs for target platform support
- Abstract input behind a project `InputService` — map keys/touch/gamepad uniformly

## Official Reference

https://docs.cocos.com/creator/3.8/manual/en/engine/input/
