---
id: helpers
title: Helper types
---

## Helper types

This page will probably get removed.

## `Position`

```typescript
export type Position = 'top' | 'right' | 'bottom' | 'left'
```

## `InteractionMode`

```typescript
export type InteractionMode = 'closest' | 'primary'
```

## `UserSerie<TDatum>`

Wraps data to be charted with useful metadata.

```typescript
export type UserSerie<TDatum> = {
  data: TDatum[]
  id?: string
  label?: string
  color?: string
  primaryAxisId?: string
  secondaryAxisId?: string
}
```

**Options**

- `primaryAxisId: string`
  - ID of an axis to be used as primary for this dataset
- `secondaryAxisId: string`
  - ID of an axis to be used as secondary for this dataset
