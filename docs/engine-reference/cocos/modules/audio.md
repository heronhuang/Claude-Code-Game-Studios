# Cocos Creator — Audio Module

Last verified: 2026-06-30 | Engine: 3.8.8

## Components

```typescript
import { AudioSource, AudioClip, resources } from 'cc';
```

- `AudioSource` on node — `play()`, `stop()`, `volume`, `loop`
- Load clips via bundle or `resources.load('audio/bgm', AudioClip, callback)`

## Patterns

- **AudioManager** component or service — pool `AudioSource` nodes for SFX
- Separate buses: BGM vs SFX vs Voice with independent volume
- Preload frequently used clips; stream long BGM if platform supports

## Performance

- Limit simultaneous one-shot SFX (e.g., max 8 footstep sounds)
- Compress assets per platform (OGG/Web, MP3/AAC native)

## Official Reference

https://docs.cocos.com/creator/3.8/manual/en/audio/
