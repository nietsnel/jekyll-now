---
layout: page
title: IR
permalink: /IR/
---


R for institutional research
================
Jordan Prendez
2016-09-02

-   [Points](#points)
-   [Statewide level](#statewide-level)
-   [Big Ten universities research funding](#big-ten-universities-research-funding)

Points
------

Points about points

``` r
library(leaflet)
library(webshot)

m <- leaflet() %>%
  addTiles() %>%  # Add default OpenStreetMap map tiles
  addMarkers(lng=-76.930576, lat=38.993662, popup="The Estate") %>%
  addMarkers(lng=-76.954220, lat=39.004796, popup="University System of Maryland")
m  # Print the map
```

COMING SOON!

Graphic here.

Statewide level
---------------

![alt text](https://raw.githubusercontent.com/nietsnel/nietsnel.github.io/master/IR_files/figure-markdown_github/unnamed-chunk-1-1.png "Logo Title Text 1")

Big Ten universities research funding
-------------------------------------

This graph compares external research funding of Big 10 universities in the top 40 nationwide.

``` r
library(dplyr)
library(maps)
library(leaflet)

cities <- read.csv(textConnection("
                                  City,Lat,Long,Pop
                                  UIndiana, 39.169763, -86.516894,645966
                                  UMaryland, 38.986125, -76.942889, 931406
                                  UMichigan, 42.277472, -83.736706, 1322711
                                  UWisconsin, 43.076937, -89.412209, 1169779
                                  UMinnesota, 44.974377, -93.227750 ,826173
                                  PennState, 40.797425, -77.860423, 797679
                                  OhioState, 40.013599, -83.031183, 766513
                                  PurdueU, 40.424498, -86.921302, 602501
                                  Uillinois, 40.102715, -88.226893, 583754
                                  MichiganState,42.701430, -84.482236, 507061
                                  "))

leaflet(cities) %>% addTiles() %>% addCircles(lng = ~Long, lat = ~Lat, weight = 1, 
    radius = ~sqrt(Pop) * 50, popup = ~City)
```

COMING SOON!

image here
