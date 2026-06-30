# Cocos Creator — Physics Module

Last verified: 2026-06-30 | Engine: 3.8.8

## 2D (Box2D)

```typescript
import { RigidBody2D, Collider2D, Contact2DType } from 'cc';
```

- `RigidBody2D` + `BoxCollider2D` / `CircleCollider2D` / `PolygonCollider2D`
- Listen: `collider.on(Contact2DType.BEGIN_CONTACT, callback)`
- Use `PhysicsSystem2D` for global gravity and debug draw

## 3D (Bullet)

```typescript
import { RigidBody, Collider, ICollisionEvent } from 'cc';
```

- `RigidBody` + `BoxCollider` / `SphereCollider` / `MeshCollider`
- `USE_GEOMETRY_COLLIDER` for complex meshes — higher cost
- Configure groups in Project → Physics

## Best Practices

- Prefer simple colliders over mesh colliders
- Kinematic bodies for character controllers driven by script
- Fixed timestep: use physics system settings, not raw `update` hacks

## Official Reference

https://docs.cocos.com/creator/3.8/manual/en/physics/
