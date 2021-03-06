
{{target: series-funnel}}

# series.funnel(Object)

**Funnel chart**

**sample: **
~[600x400](${galleryViewPath}funnel&reset=1&edit=1)

## type(string) = 'funnel'

{{ use: partial-series-name() }}

## min(number) = 0
The specified minimum value.

## max(number) = 100
The specified maximum value.

## minSize(string) = '0%'
The mapped width from minimum data value [min](~series-funnel.min).

It can be absolute pixel and also the percentage of [layout width](~series-funnel.width). If you don't want the graph of minimum value to be a triangle, you can set up this property larger than 0.

## maxSize(string) = '100%'
The mapped width from maximum data value [max](~series-funnel.max).

It can be absolute pixel and also the percentage of [layout width](~series-funnel.width).

## sort(string) = 'descending'
Data sorting, which can be whether `'ascending'` or `'descending'`.

## gap(number) = 0
Gap between each trapezoid.

{{ use: partial-legend-hover-link }}

## funnelAlign(string) = 'center'
Horizontal align. Defaults to align center. Can be 'left', 'right', 'center'.

## label(Object)
{{use:partial-label-desc(name="funnel chart")}}
### normal(Object)
{{use:partial-funnel-label(
    prefix="###",
    position=true,
    formatter=true
)}}
### emphasis(Object)
{{use:partial-funnel-label(
    prefix="###",
    position=false,
    formatter=true
)}}

## labelLine(Object)
The visual guide line style of label. When [label position](~series-funnel.label.normal.position) is set as `'left'`or`'right'`, the visual guide line will show.
{{ use: partial-funnel-label-line(prefix='##') }}

## itemStyle(Object)
{{use:partial-item-style-desc}}
### normal(Object)
{{use:partial-item-style(
    prefix="###",
    useColorPalatte=true,
    hasCallback=true
)}}
### emphasis(Object)
{{use:partial-item-style(prefix="###")}}


{{ use: component-rect-layout-width-height(
    componentName="funnel chart",
    defaultLeft=80,
    defaultTop=60,
    defaultRight=80,
    defaultBottom=60
) }}


## data(Array)
{{ use: partial-1d-data-desc }}
### name(string)
the name of data item.
### value(number)
data value.

### label(Object)
The label configuration of a single data item.
#### normal(Object)
{{use:partial-funnel-label(
    prefix="####",
    position=true,
    formatter=false
)}}
#### emphasis(Object)
{{use:partial-funnel-label(
    prefix="####",
    position=false,
    formatter=false
)}}

### labelLine(Object)
{{ use: partial-funnel-label-line(prefix='###') }}

### itemStyle(Object)
{{use:partial-item-style-desc}}
#### normal(Object)
{{use:partial-item-style(prefix="####")}}
#### emphasis(Object)
{{use:partial-item-style(prefix="####")}}

{{use: partial-mark-point(
    prefix="#",
    seriesType="funnel"
)}}
{{use: partial-mark-line(
    prefix="#",
    seriesType="funnel"
)}}

{{use:partial-animation(prefix="#")}}




{{ target: partial-funnel-label }}
#${prefix} show(boolean) = false
{{ if: ${position} }}
#${prefix} position(string) = 'outside'
Label position.

**Options: **
+ `'left'`

    Left side of funnel chart. The corresponding trapezoid would be related to through [visual guide line](~series-funnel.labelLine).

+ `'right'`

   Right side of funnel chart. The corresponding trapezoid would be related to through [visual guide line](~series-funnel.labelLine).

+ `'inside'`

    Inside the trapezoid of funnel chart.

+ `'inner'` equals to `'inside'`.
+ `'center'` equals to `'inside'`.

{{ /if }}
{{ if: ${formatter} }}
#${prefix} formatter(string|Function)
{{ use: partial-1d-data-label-formatter(extra = {
    percent: {
        desc: 'percentage',
        type: 'number'
    }
}) }}
{{ /if }}
#${prefix} textStyle(Object)
the font style of lable.
{{ use:partial-text-style(prefix=${prefix} + '#') }}


{{ target: partial-funnel-label-line }}
#${prefix} normal(Object)
The style of visual guide line in normal status.
##${prefix} show(boolean)
Whether to show visual guide line.
##${prefix} length(number)
The length of the first part from visual guide line.
##${prefix} lineStyle(Object)
{{use:partial-line-style(prefix="##" + ${prefix})}}
#${prefix} emphasis(Object)
The style of visual guide line in emphasis status.
##${prefix} show(boolean)
Whether to show visual guide line.
##${prefix} lineStyle(Object)
{{use:partial-line-style(prefix="##" + ${prefix})}}


