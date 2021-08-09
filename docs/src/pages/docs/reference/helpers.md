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

## `CursorOptions`

```typescript
export type CursorOptions = {
  value?: unknown
  show?: boolean
  showLine?: boolean
  showLabel?: boolean
  axisId?: string
  onChange?: (value: any) => void
}
```

## `TooltipOptions<TDatum>`

```typescript
export type TooltipOptions<TDatum> = {
  align?: AlignMode
  alignPriority?: AlignPosition[]
  padding?: number
  arrowPadding?: number
  groupingMode?: TooltipGroupingMode
  show?: boolean
  render?: (props: TooltipRendererProps<TDatum>) => React.ReactNode
  invert?: boolean
}
```

## `AlignMode`

```typescript
export type AlignMode =
  | 'auto'
  | 'right'
  | 'topRight'
  | 'bottomRight'
  | 'left'
  | 'topLeft'
  | 'bottomLeft'
  | 'top'
```

## `AlignPosition`

```typescript
export type AlignPosition =
  | 'top'
  | 'right'
  | 'bottom'
  | 'left'
  | 'topRight'
  | 'bottomRight'
  | 'topLeft'
  | 'bottomLeft'
```

## `TooltipGroupingMode`

```typescript
export type TooltipGroupingMode = 'primary' | 'single' | 'secondary' | 'series'
```
