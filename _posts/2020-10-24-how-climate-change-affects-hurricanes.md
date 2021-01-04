---
layout: single
title: How Climate Change Affects Hurricanes
date: '2020-10-24T16:18:00.008-04:00'
author: Sonny Parlin
categories:
  - Blog
tags:
- analysis
- python
- noaa
- hurricanes
- research
- climate change
modified_time: '2020-10-25T00:39:10.500-04:00'
blogger_id: tag:blogger.com,1999:blog-274791723093518550.post-1078983741956560737
blogger_orig_url: https://www.sparl.in/2020/10/how-climate-change-affects-hurricanes.html
---

This post reports on data analysis of NOAA hurricane data from 1851 (when we started tracking hurricanes) to 2017, all the data I could get from NOAA for my analysis. There are some key findings that show how specific indicators for hurricanes like ACE data ("ACE" - Accumulated Cyclone Energy, which is an index that combines the numbers of systems, how long they existed and how intense they became. It is calculated by squaring the maximum sustained surface wind in the system every six hours that the storm is a "named storm" and summing it up for the season. It is expressed in 10 to the 4th kt\*\*2.) and Rapid Intensification (The National Hurricane Center (NHC) defines rapid intensification as, “an increase in the maximum sustained winds of a storm of at least 30 knots (35 mph) in a 24-hour period).

Let's start with the ACE DATA

[![Ace index scatter plot](https://plotly.com/~sonnyjitsu/22.png)](https://plotly.com/~sonnyjitsu/22/ "Ace index scatter plot")

Link to originl graph and data: [https://chart-studio.plotly.com/~sonnyjitsu/22#plot](https://chart-studio.plotly.com/~sonnyjitsu/22#plot)

There is a very slight uptick in Accumulated Cyclone Energy, the uptick is likely due to the number of storms increasing over the period given, a strong indication of climate change. Now let's take a look at number of storms per year.

[![Storms per year line chart](https://plotly.com/~sonnyjitsu/24.png)](https://plotly.com/~sonnyjitsu/24/ "Storms per year line chart")

Link to original graph and data: [https://chart-studio.plotly.com/~sonnyjitsu/24/storms-from-1850-to-present/#/](https://chart-studio.plotly.com/~sonnyjitsu/24/storms-from-1850-to-present/#/).

We can clearly see the number of storms has been steadily increasing over time, another indicator of the climate changing as this is likely due to increases in ocean surface temperatures. However the number of hurricanes and major hurricanes has only slightly increased. Yes there are more storms but many of them die off at sea and never make landfall. The hurricanes we shoud be most concerned with are the ones that make landfall, which we will explore further into this article.

Probably the most damming evidence of climate change affecting hurricanes is Rapid Intensification. Again, Rapid intensification (RI Index) is an increase in the maximum sustained winds of a storm of at least 30 knots (35 mph) in a 24-hour period. Let's take a look at the RI Index graph.

[![RI Index Histogram](https://plotly.com/~sonnyjitsu/32.png)](https://plotly.com/~sonnyjitsu/32/ "RI Index Histogram")

Link to original graph and data: [https://chart-studio.plotly.com/~sonnyjitsu/32/hurricane-ri-index-derived-from-httpswwwnhcnoaagovdatahurdathurdat2-1851-2017-05/#/](https://chart-studio.plotly.com/~sonnyjitsu/32/hurricane-ri-index-derived-from-httpswwwnhcnoaagovdatahurdathurdat2-1851-2017-05/#/)

Notice anything funny about this graph? Me too, it's missing data. According to the [Union of Concerned Scientists](https://www.ucsusa.org/resources/hurricanes-and-climate-change):

> The advent of satellite technology in the 1970s made it possible to more consistently track hurricanes. Storm counts and strength measurements from before to the 1970s are less consistent, further complicating the study of long-term trends.

In other words, we didn't have the tools in place to take these measurements until the 70s, and while our tools are getting better and our methods are becoming more solid, we are still left with [interpolation](https://en.wikipedia.org/wiki/Interpolation) as our only looks into the past and future, and without proper measurements with actual data, these are just highly educated guesses.

So let's take a look at what I consider to be the most important measurements, category and wind speed AFTER LANDFALL. Yes, it's true that the number of storms is increasing with time and those storms are rapidly instensifying faster than ever, however we see something very interesting once those hurricanes make landfall.

[![Category Scatter Plot](https://plotly.com/~sonnyjitsu/26.png)](https://plotly.com/~sonnyjitsu/26/ "Category Scatter Plot")

Link to original graph and data: [https://chart-studio.plotly.com/~sonnyjitsu/26/hurricane-category-historical-data-for-continental-us-landfalling-hurricanes/#/](https://chart-studio.plotly.com/~sonnyjitsu/26/hurricane-category-historical-data-for-continental-us-landfalling-hurricanes/#/)

We've had three category 5 hurricanes, ever. The last one was hurricane Emily, which hit in 1991, 29 years ago. As you see from the graph the line is almost flat, meaning that after landfall there has been virtually no change. This is largely due to hurricanes losing much of their speed after hitting land. From [https://sciencing.com/long-hurricane-travel-over-land-12327531.html](https://sciencing.com/long-hurricane-travel-over-land-12327531.html)

> Hurricanes weaken over land because they are fueled by evaporation from warm ocean water, which dry land surfaces do not provide. After only a few hours over land, hurricanes begin rapidly to deteriorate, with wind speeds decreasing significantly.

This becomes even more evident when we look at windspeed over time

[![Wind speed scatter plot](https://plotly.com/~sonnyjitsu/14.png)](https://plotly.com/~sonnyjitsu/14/ "Wind speed scatter plot")

Link to original graph and data: [https://chart-studio.plotly.com/~sonnyjitsu/14/wind-speeds-of-all-hurricanes-after-landfall-from-1850-to-present/#/](https://chart-studio.plotly.com/~sonnyjitsu/14/wind-speeds-of-all-hurricanes-after-landfall-from-1850-to-present/#/)

Again, we have an almost flat line over a span of almost 200 years. This is also explained by the slow down of hurricanes once they hit landfall. (NOTE; WIND SPEED DATA IS NOT AVAILABLE BETWEEN 1961 and 1979, it's not in the [raw data](https://web.archive.org/web/20190405010652/http://www.aoml.noaa.gov/hrd/tcfaq/E23.html).)

So while we can see significant increases in the number of storms and their severity at sea, there has been very little difference between category and windspeed since 1851 after these storms reach landfall. Lastly, monetary damage is not covered in this post as an indicator because it's not an indicator of weather changes but more an indicator of the value of materials, property, property growth and the value of labor over time, which are arbitrary. In other words, if a CAT 5 hurricane hits a beach with 5 houses, 5 houses may be damaged. Now let's say repairs are made to those houses and in addition, more houses get built on the same beach. Then let's say a few years later another CAT 5 hurricane hits the same beach, the dollar amount of damage increases, not because of weather but because more property was there to damage.

For complete transparency, my [source code is available on GitHub](https://github.com/sonnyparlin/hurricane_research).
