---
title       : Describing:"When Can I (legally) Drive" Shiny_app.
subtitle    : Developing Data Products, Assignment week 4.
author      : HagenC
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
ext_widgets: {rCharts: [libraries/nvd3]}
---


## Motivation

**"When can I (legally)drive?"** is an Shiny-app that calculates the blood alcohol level (permille),
the units consumed and the time in hours before you can legally drive.

The app can give you an idea what a couple of beers or a glass of wine will do to you!

The calculations are described in the following slides.


---  

## Blood alcohol level (concentration)

The alchohol blood level is calculated as: grams of alcohol / (body weight in Kg * body water fraction).
The body water fraction is 70% for males and 60% for females. 

If we consider a person drinking 3 beers of 4.6 % alchohol the blood alcohol dependency on body weight and sex can be illustrated as below: 


<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    800,
"height":    400,
"x": "Kg",
"y": "Pro",
"group": "sex",
"type": "multiBarChart",
"id": "chart1" 
},
        data = [
 {
 "Kg": 50,
"Pro": 1.314285714286,
"sex": "Male" 
},
{
 "Kg": 51,
"Pro": 1.288515406162,
"sex": "Male" 
},
{
 "Kg": 52,
"Pro": 1.263736263736,
"sex": "Male" 
},
{
 "Kg": 53,
"Pro": 1.239892183288,
"sex": "Male" 
},
{
 "Kg": 54,
"Pro": 1.216931216931,
"sex": "Male" 
},
{
 "Kg": 55,
"Pro": 1.194805194805,
"sex": "Male" 
},
{
 "Kg": 56,
"Pro": 1.173469387755,
"sex": "Male" 
},
{
 "Kg": 57,
"Pro": 1.152882205514,
"sex": "Male" 
},
{
 "Kg": 58,
"Pro": 1.133004926108,
"sex": "Male" 
},
{
 "Kg": 59,
"Pro": 1.113801452785,
"sex": "Male" 
},
{
 "Kg": 60,
"Pro": 1.095238095238,
"sex": "Male" 
},
{
 "Kg": 61,
"Pro": 1.077283372365,
"sex": "Male" 
},
{
 "Kg": 62,
"Pro": 1.059907834101,
"sex": "Male" 
},
{
 "Kg": 63,
"Pro": 1.043083900227,
"sex": "Male" 
},
{
 "Kg": 64,
"Pro": 1.026785714286,
"sex": "Male" 
},
{
 "Kg": 65,
"Pro": 1.010989010989,
"sex": "Male" 
},
{
 "Kg": 66,
"Pro": 0.995670995671,
"sex": "Male" 
},
{
 "Kg": 67,
"Pro": 0.9808102345416,
"sex": "Male" 
},
{
 "Kg": 68,
"Pro": 0.9663865546218,
"sex": "Male" 
},
{
 "Kg": 69,
"Pro": 0.952380952381,
"sex": "Male" 
},
{
 "Kg": 70,
"Pro": 0.9387755102041,
"sex": "Male" 
},
{
 "Kg": 71,
"Pro": 0.9255533199195,
"sex": "Male" 
},
{
 "Kg": 72,
"Pro": 0.9126984126984,
"sex": "Male" 
},
{
 "Kg": 73,
"Pro": 0.9001956947162,
"sex": "Male" 
},
{
 "Kg": 74,
"Pro": 0.8880308880309,
"sex": "Male" 
},
{
 "Kg": 75,
"Pro": 0.8761904761905,
"sex": "Male" 
},
{
 "Kg": 76,
"Pro": 0.8646616541353,
"sex": "Male" 
},
{
 "Kg": 77,
"Pro": 0.8534322820037,
"sex": "Male" 
},
{
 "Kg": 78,
"Pro": 0.8424908424908,
"sex": "Male" 
},
{
 "Kg": 79,
"Pro": 0.8318264014467,
"sex": "Male" 
},
{
 "Kg": 80,
"Pro": 0.8214285714286,
"sex": "Male" 
},
{
 "Kg": 81,
"Pro": 0.8112874779541,
"sex": "Male" 
},
{
 "Kg": 82,
"Pro": 0.801393728223,
"sex": "Male" 
},
{
 "Kg": 83,
"Pro": 0.7917383820998,
"sex": "Male" 
},
{
 "Kg": 84,
"Pro": 0.7823129251701,
"sex": "Male" 
},
{
 "Kg": 85,
"Pro": 0.7731092436975,
"sex": "Male" 
},
{
 "Kg": 86,
"Pro": 0.7641196013289,
"sex": "Male" 
},
{
 "Kg": 87,
"Pro": 0.7553366174056,
"sex": "Male" 
},
{
 "Kg": 88,
"Pro": 0.7467532467532,
"sex": "Male" 
},
{
 "Kg": 89,
"Pro": 0.7383627608347,
"sex": "Male" 
},
{
 "Kg": 90,
"Pro": 0.7301587301587,
"sex": "Male" 
},
{
 "Kg": 91,
"Pro": 0.7221350078493,
"sex": "Male" 
},
{
 "Kg": 92,
"Pro": 0.7142857142857,
"sex": "Male" 
},
{
 "Kg": 93,
"Pro": 0.7066052227343,
"sex": "Male" 
},
{
 "Kg": 94,
"Pro": 0.6990881458967,
"sex": "Male" 
},
{
 "Kg": 95,
"Pro": 0.6917293233083,
"sex": "Male" 
},
{
 "Kg": 96,
"Pro": 0.6845238095238,
"sex": "Male" 
},
{
 "Kg": 97,
"Pro": 0.6774668630339,
"sex": "Male" 
},
{
 "Kg": 98,
"Pro": 0.6705539358601,
"sex": "Male" 
},
{
 "Kg": 99,
"Pro": 0.6637806637807,
"sex": "Male" 
},
{
 "Kg": 100,
"Pro": 0.6571428571429,
"sex": "Male" 
},
{
 "Kg": 101,
"Pro": 0.6506364922207,
"sex": "Male" 
},
{
 "Kg": 102,
"Pro": 0.6442577030812,
"sex": "Male" 
},
{
 "Kg": 103,
"Pro": 0.6380027739251,
"sex": "Male" 
},
{
 "Kg": 104,
"Pro": 0.6318681318681,
"sex": "Male" 
},
{
 "Kg": 105,
"Pro": 0.6258503401361,
"sex": "Male" 
},
{
 "Kg": 106,
"Pro": 0.6199460916442,
"sex": "Male" 
},
{
 "Kg": 107,
"Pro": 0.6141522029372,
"sex": "Male" 
},
{
 "Kg": 108,
"Pro": 0.6084656084656,
"sex": "Male" 
},
{
 "Kg": 109,
"Pro": 0.6028833551769,
"sex": "Male" 
},
{
 "Kg": 110,
"Pro": 0.5974025974026,
"sex": "Male" 
},
{
 "Kg": 111,
"Pro": 0.5920205920206,
"sex": "Male" 
},
{
 "Kg": 112,
"Pro": 0.5867346938776,
"sex": "Male" 
},
{
 "Kg": 113,
"Pro": 0.5815423514539,
"sex": "Male" 
},
{
 "Kg": 114,
"Pro": 0.5764411027569,
"sex": "Male" 
},
{
 "Kg": 115,
"Pro": 0.5714285714286,
"sex": "Male" 
},
{
 "Kg": 116,
"Pro": 0.5665024630542,
"sex": "Male" 
},
{
 "Kg": 117,
"Pro": 0.5616605616606,
"sex": "Male" 
},
{
 "Kg": 118,
"Pro": 0.5569007263923,
"sex": "Male" 
},
{
 "Kg": 119,
"Pro": 0.5522208883553,
"sex": "Male" 
},
{
 "Kg": 120,
"Pro": 0.547619047619,
"sex": "Male" 
},
{
 "Kg": 50,
"Pro": 1.533333333333,
"sex": "Female" 
},
{
 "Kg": 51,
"Pro": 1.503267973856,
"sex": "Female" 
},
{
 "Kg": 52,
"Pro": 1.474358974359,
"sex": "Female" 
},
{
 "Kg": 53,
"Pro": 1.446540880503,
"sex": "Female" 
},
{
 "Kg": 54,
"Pro":  1.41975308642,
"sex": "Female" 
},
{
 "Kg": 55,
"Pro": 1.393939393939,
"sex": "Female" 
},
{
 "Kg": 56,
"Pro": 1.369047619048,
"sex": "Female" 
},
{
 "Kg": 57,
"Pro": 1.345029239766,
"sex": "Female" 
},
{
 "Kg": 58,
"Pro":  1.32183908046,
"sex": "Female" 
},
{
 "Kg": 59,
"Pro": 1.299435028249,
"sex": "Female" 
},
{
 "Kg": 60,
"Pro": 1.277777777778,
"sex": "Female" 
},
{
 "Kg": 61,
"Pro": 1.256830601093,
"sex": "Female" 
},
{
 "Kg": 62,
"Pro": 1.236559139785,
"sex": "Female" 
},
{
 "Kg": 63,
"Pro": 1.216931216931,
"sex": "Female" 
},
{
 "Kg": 64,
"Pro": 1.197916666667,
"sex": "Female" 
},
{
 "Kg": 65,
"Pro": 1.179487179487,
"sex": "Female" 
},
{
 "Kg": 66,
"Pro": 1.161616161616,
"sex": "Female" 
},
{
 "Kg": 67,
"Pro": 1.144278606965,
"sex": "Female" 
},
{
 "Kg": 68,
"Pro": 1.127450980392,
"sex": "Female" 
},
{
 "Kg": 69,
"Pro": 1.111111111111,
"sex": "Female" 
},
{
 "Kg": 70,
"Pro": 1.095238095238,
"sex": "Female" 
},
{
 "Kg": 71,
"Pro": 1.079812206573,
"sex": "Female" 
},
{
 "Kg": 72,
"Pro": 1.064814814815,
"sex": "Female" 
},
{
 "Kg": 73,
"Pro": 1.050228310502,
"sex": "Female" 
},
{
 "Kg": 74,
"Pro": 1.036036036036,
"sex": "Female" 
},
{
 "Kg": 75,
"Pro": 1.022222222222,
"sex": "Female" 
},
{
 "Kg": 76,
"Pro": 1.008771929825,
"sex": "Female" 
},
{
 "Kg": 77,
"Pro": 0.995670995671,
"sex": "Female" 
},
{
 "Kg": 78,
"Pro": 0.982905982906,
"sex": "Female" 
},
{
 "Kg": 79,
"Pro": 0.9704641350211,
"sex": "Female" 
},
{
 "Kg": 80,
"Pro": 0.9583333333333,
"sex": "Female" 
},
{
 "Kg": 81,
"Pro": 0.9465020576132,
"sex": "Female" 
},
{
 "Kg": 82,
"Pro": 0.9349593495935,
"sex": "Female" 
},
{
 "Kg": 83,
"Pro": 0.9236947791165,
"sex": "Female" 
},
{
 "Kg": 84,
"Pro": 0.9126984126984,
"sex": "Female" 
},
{
 "Kg": 85,
"Pro": 0.9019607843137,
"sex": "Female" 
},
{
 "Kg": 86,
"Pro": 0.8914728682171,
"sex": "Female" 
},
{
 "Kg": 87,
"Pro": 0.8812260536398,
"sex": "Female" 
},
{
 "Kg": 88,
"Pro": 0.8712121212121,
"sex": "Female" 
},
{
 "Kg": 89,
"Pro": 0.8614232209738,
"sex": "Female" 
},
{
 "Kg": 90,
"Pro": 0.8518518518519,
"sex": "Female" 
},
{
 "Kg": 91,
"Pro": 0.8424908424908,
"sex": "Female" 
},
{
 "Kg": 92,
"Pro": 0.8333333333333,
"sex": "Female" 
},
{
 "Kg": 93,
"Pro": 0.8243727598566,
"sex": "Female" 
},
{
 "Kg": 94,
"Pro": 0.8156028368794,
"sex": "Female" 
},
{
 "Kg": 95,
"Pro": 0.8070175438596,
"sex": "Female" 
},
{
 "Kg": 96,
"Pro": 0.7986111111111,
"sex": "Female" 
},
{
 "Kg": 97,
"Pro": 0.7903780068729,
"sex": "Female" 
},
{
 "Kg": 98,
"Pro": 0.7823129251701,
"sex": "Female" 
},
{
 "Kg": 99,
"Pro": 0.7744107744108,
"sex": "Female" 
},
{
 "Kg": 100,
"Pro": 0.7666666666667,
"sex": "Female" 
},
{
 "Kg": 101,
"Pro": 0.7590759075908,
"sex": "Female" 
},
{
 "Kg": 102,
"Pro": 0.7516339869281,
"sex": "Female" 
},
{
 "Kg": 103,
"Pro": 0.7443365695793,
"sex": "Female" 
},
{
 "Kg": 104,
"Pro": 0.7371794871795,
"sex": "Female" 
},
{
 "Kg": 105,
"Pro": 0.7301587301587,
"sex": "Female" 
},
{
 "Kg": 106,
"Pro": 0.7232704402516,
"sex": "Female" 
},
{
 "Kg": 107,
"Pro": 0.7165109034268,
"sex": "Female" 
},
{
 "Kg": 108,
"Pro": 0.7098765432099,
"sex": "Female" 
},
{
 "Kg": 109,
"Pro": 0.7033639143731,
"sex": "Female" 
},
{
 "Kg": 110,
"Pro": 0.6969696969697,
"sex": "Female" 
},
{
 "Kg": 111,
"Pro": 0.6906906906907,
"sex": "Female" 
},
{
 "Kg": 112,
"Pro": 0.6845238095238,
"sex": "Female" 
},
{
 "Kg": 113,
"Pro": 0.6784660766962,
"sex": "Female" 
},
{
 "Kg": 114,
"Pro": 0.672514619883,
"sex": "Female" 
},
{
 "Kg": 115,
"Pro": 0.6666666666667,
"sex": "Female" 
},
{
 "Kg": 116,
"Pro": 0.6609195402299,
"sex": "Female" 
},
{
 "Kg": 117,
"Pro": 0.6552706552707,
"sex": "Female" 
},
{
 "Kg": 118,
"Pro": 0.6497175141243,
"sex": "Female" 
},
{
 "Kg": 119,
"Pro": 0.6442577030812,
"sex": "Female" 
},
{
 "Kg": 120,
"Pro": 0.6388888888889,
"sex": "Female" 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        chart
  .margin({
 "left":    100 
})
          
        chart.xAxis
  .axisLabel("Body weight (Kg)")

        
        
        chart.yAxis
  .axisLabel("Blood Alcohol Level (Permille)")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

--- .classe 

## Time before reaching the legal blood alchohol level.

The legal blood alcohol level is dependent on country/state law. In Denmark it is 0.5 permille and in Sweden 0.0.

To calulate the time before reaching legal blood alcohol level I use the the widely accepted alchohol metabolizing constant of 0.15 grams/hour. 

Calculating the grams of alcohol in your body and substratc the legal amount of alcohol in grams (that is dependent on body weight and sex) we can calculate the time before the surplus alcohold is metabolized. 

A unit of alcohol is 12g so it will take 12/0.15 = 80 hours to metabolize one unit, no matter your body weight or sex. However, it is actually influenced by whether you have a full stomach or not. If you have eaten, the alcohol metabolism is FASTER. The reverse is true for the alcohol absorbtion that is SLOWER on a full stomach. Absorption is also influenced on sex and body weight. 

Unfortunately, there are no measures of these phenomenons as we are not sure why it is so. Thus, it is ignored in the calculations. 



--- .classe 

## An App without an Disclaimer?: I dont think so:

So...

Disclaimer:  This is only a rough estimate based on population averages and does not take into account existing disease states, drug interactions, or age.




