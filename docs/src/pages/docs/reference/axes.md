---
id: axes
title: Axes
---

## `AxisOptionsBase`

**Options**

- `primaryAxisId: string`
  - Optional
  - ID assigned to the primary axis
- `elementType: 'line' | 'area' | 'bar' | 'bubble'`
  - Optional
  - Type of element that will represent data on this axis
  - defaults to `line`
- `showDatumElements: boolean`
  - Optional
- `curve: CurveFactory`
  - Optional
  - TODO
- `invert: boolean`
  - Optional
  - If set to true, axis coordinates will be inverted (i.e. vertical axis would grow from bottom left corner upwards)
  - TODO
- `position:` [`Position`](./helpers#position)
  - Optional
  - Position on the chart this axis will be rendered at
- `minTickPaddingForRotation: number`
  - Optional
  - defaults to `10`
  - used for calculating tick labels - if labels don't fit horizontally, they get rotated
- `tickLabelRotationDeg: number`
  - Optional
  - angle of rotation of tick labels in degrees, applied if rotation is necessary
- `tickCount: number`
  - Optional
  - if set, will define number of ticks rendered on this axis, otherwise will be determined automatically by `d3`
- `innerBandPadding: number`
  - TODO: shouldn't this be moved to `AxisBandOptions<TDatum>` instead? Same for the next 5
  - Optional
  - defaults to `0.5`
  - defines a proportion of a band reserved for blank space (used e.g. with bar charts)
  - see [d3 docs](https://github.com/d3/d3-scale/blob/v4.0.0/README.md#band_paddingInner)
- `outerBandPadding: number`
  - Optional
  - defaults to `0.2`
  - defines a proportion of a `step` to be reserved before first and after last band for blank space
  - see [d3 docs](https://github.com/d3/d3-scale/blob/v4.0.0/README.md#band_paddingOuter)
- `innerSeriesBandPadding: number`
  - Optional
  - like `innerBandPadding`, but for series band scales
  - TODO
- `outerSeriesBandPadding: number`
  - Optional
  - like `outerBandPadding, for for series band scales
  - TODO
- `minBandSize: number`
  - Optional
  - sets minimum band width
- `maxBandSize: number`
  - Optional
  - sets maximum band width
- `minDomainLength: number`
  - Optional
  - sets minimum length of the domain
- `showGrid: boolean`
  - Optional
  - defaults to `true`
  - if `true`, displays full length lines on tick positions
- `show: boolean`
  - Optional
  - if `false`, doesn't render this axis on the chart
- `stacked: boolean`
  - Optional
  - determines if data series on this axis are stacked (think stacked bar chart, stacked area chart)
- `stackOffset: TODO`
  - Optional
  - see [d3 docs](https://github.com/d3/d3-shape/blob/v3.0.1/README.md#stack-offsets)
- `id: string | number`
  - Optional
  - ID for this axis
- `styles: CSSProperties & { line: CSSProperties, tick: CSSProperties }`
  - Optional
  - used for direct styling of the axis

## `AxisTimeOptions<TDatum>`

**Options**

- all [`AxisOptionsBase`](#axisoptionsbase) options
- `scaleType: 'time' | 'localTime'`
  - discriminator
  - 'time' uses UTC time while 'localTime' uses local time
- `getValue: (datum: TDatum) => ChartValue<Date>`
  - accessor function to get the date value from your datum object
- `min: Date`
  - Optional
  - manually sets the minimum for your date range
  - respects your data range, i.e. when your series contains lower values, those will be determined as minimum
- `max: Date`
  - Optional
  - manually sets the maximum for your date range
  - respects your data range, i.e. when your series contains higher values, those will be determined as maximum
- `hardMin: Date`
  - Optional
  - unlike `min`, sets minimum disregarding your data range, i.e. `hardMin` will be used as minimum regardless of your data
- `hardMax: Date`
  - Optional
  - same as `hardMin`
- `formatters`
  - TODO
  - formatting functions for the scale, tooltip and cursor

## `AxisLinearOptions<TDatum>`

**Options**

- all [`AxisOptionsBase`](#axisoptionsbase) options
- `scaleType: 'linear' | 'log'`
  - discriminator
- `getValue: (datum: TDatum) => ChartValue<number>`
  - accessor function to get the numeric value from your datum object
- `min: number`
  - Optional
  - manually sets the minimum for your date range
  - respects your data range, i.e. when your series contains lower values, those will be determined as minimum
- `max: number`
  - Optional
  - manually sets the maximum for your date range
  - respects your data range, i.e. when your series contains higher values, those will be determined as maximum
- `hardMin: Date`
  - Optional
  - unlike `min`, sets minimum disregarding your data range, i.e. `hardMin` will be used as minimum regardless of your data
- `hardMax: Date`
  - Optional
  - same as `hardMin`
- `formatters`
  - TODO
  - formatting functions for the scale, tooltip and cursor

## `AxisBandOptions<TDatum>`

**Options**

- all [`AxisOptionsBase`](#axisoptionsbase) options
- `scaleType: 'band'`
  - discriminator
- `getValue: (datum: TDatum) => ChartValue<any>`
  - accessor function to get the value from your datum object
- `originalSinBandSize: number`
  - TODO
- `formatters`
  - TODO
  - formatting functions for the scale, tooltip and cursor

## `AxisOptions<TDatum>`

This type describes one of [`AxisTimeOptions<TDatum>`](#axistimeoptionstdatum), [`AxisLinearOptions<TDatum>`](#axislinearoptionstdatum) and [`AxisBandOptions<TDatum>`](#axisbandoptionstdatum) with `scaleType` used as discriminator.
