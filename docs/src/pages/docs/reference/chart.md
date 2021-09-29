---
id: Chart
title: Chart component
---

## `Chart` component

The `Chart` component is used to render a chart in your application.

```jsx
import { Chart } from 'react-charts'

function App() {
  return <Chart options={...}></Chart>
}
```

**Options**

- `options: ChartOptions<TDatum>`
  - **Required**
  - a configuration object used to render the chart
  - generic with respect to type of a single data point (called datum)
- inherit all props from `div`, so you can apply `style`, `className` etc. directly

**Types**

**`ChartOptions<TDatum>`**:

- `data:` [`UserSerie<TDatum>[]`](./helpers#userserietdatum)
  - **Required**
  - an array of data series to be visualized
  - at least one series is required
- `primaryAxis:` [`AxisOptions<TDatum>`](./axes#axisoptionstdatum)
  - **Required**
  - configuration options for the primary axis
- `secondaryAxes:` [`AxisOptions<TDatum>[]`](./axes#axisoptionstdatum)
  - **Required**
  - an array of configuration options for all the secondary axes
- `padding?: number | { left?: number, right?: number, top?: number, bottom?: number }`
  - Optional
  - if `number` is passed, it is applied on all sides equally, otherwise specifies different paddings for each side
  - defaults to `5`
- `getSeriesStyle: (series: Series<TDatum>, status: SeriesFocusStatus) => SeriesStyles`
  - `TODO`
  - Optional
  - a function that computes CSS properties applied to a series based on whether or not it is focused
- `getDatumStyle: (datum: Datum<TDatum>, status: DatumFocusStatus) => DatumStyles`
  - `TODO`
  - Optional
  - a function that computes CSS properties applied to a datum based on whether or not it is focused
- `interactionMode:` [`InteractionMode`](helpers#interactionmode)
  - Optional
  - determines tiling of the chart for resolving any interaction callbacks
  - use `showVoronoi: true` to see it in action
- `showVoronoi: boolean`
  - Optional
- `showDebugAxes: boolean`
  - Optional
- `memoizeSeries: boolean`
  - Optional
- `defaultColors: string[]`
  - Optional
- `initialWidth: number`
  - Optional
- `initialHeight: number`
  - Optional
- `brush`
  - `TODO`
  - Optional
- `onFocusDatum: (datum: Datum<TDatum> | null) => void`
  - `TODO`
  - Optional
- `onClickDatum: (datum: Datum<TDatum> | null, event: React.MouseEvent) => void`
  - Optional
  - Callback called when clicking on a datum
- `dark: boolean`
  - Optional
  - if passed, the chart is rendered with a dark background
- `renderSVG: () => React.ReactNode`
  - Optional
- `primaryCursor: boolean | `[`CursorOptions`](helpers#cursoroptions)
  - `TODO`
  - Optional
- `secondaryCursor: boolean | `[`CursorOptions`](helpers#cursoroptions)
  - `TODO`
  - Optional
- `tooltip: boolean | TooltipOptions<TDatum>`
  - `TODO`
  - Optional
- `useIntersectionObserver: boolean`
  - Optional
  - if set to `false`, charts will be rendered even if not currently in viewport
  - defaults to `true`
- `intersectionObserverRootMargin`
  - `TODO`
  - Optional
