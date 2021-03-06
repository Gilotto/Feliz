# Feliz.Recharts - Straight Angle

Taken from [Recharts - StraightAnglePieChart](http://recharts.org/en-US/examples/StraightAnglePieChart).

```fsharp:recharts-pie-straightangle
module App

open Feliz
open Feliz.Recharts
open Fable.Core.Experimental

type PieSlice = { name: string; value: int }

let data = [
    { name = "Group A"; value = 400 }
    { name = "Group B"; value = 300 }
    { name = "Group C"; value = 300 }
    { name = "Group D"; value = 200 }
    { name = "Group E"; value = 278 }
    { name = "Group F"; value = 189 }
]

let chart = React.functionComponent <| fun () ->
    Recharts.pieChart [
        pieChart.width 400
        pieChart.height 400
        pieChart.children [
            Recharts.pie [
                pie.data data
                pie.dataKey (fun point -> nameof point.value)
                pie.startAngle 180
                pie.endAngle 0
                pie.cx 200
                pie.cy 200
                pie.outerRadius 80
                pie.fill "#8884d8"
                pie.label true
            ]
        ]
    ]


open Browser.Dom

ReactDOM.render(chart, document.getElementById "root")
```