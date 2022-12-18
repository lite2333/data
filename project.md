---
elm:
  dependencies:
    gicentre/elm-vegalite: latest
---
# How China achieve the positive economic growth in 2020?
## Introduction

In 2020, the world economy got into a deep recession, the worst since the Great Depression of the 1930s, as the "black swan" of the New Coronary Pneumonia epidemic hit the global economy hard. 2020 will see the global economy shrink by 4.4%, seven times the rate of decline of the 2009 world economic crisis. Coronavirus disease (COVID-19) is an infectious disease caused by the SARS-CoV-2 virus. New coronary pneumonia has a higher rate of death and transmission than the influenza virus. It has caused worldwide panic and has had a significant influence on the world economy. This analysis represents the condition of the world economy by world GDP analysis. By analysing the world's GDP ranking, China is the only country in the top 15 countries with positive GDP growth in 2020. This paper explores how China can achieve positive GDP growth in 2020 by analysing its achievements in controlling the spread of the epidemic and its development and strengths.

Further study of the spread of the epidemic in 2020 combined with GDP changes in each country reveals that controlling the spread of the epidemic can benefit economic recovery. China's timely containment of Covid-19 in 2020 created the conditions for population movement and resumption of work and production. Positive year-on-year growth in the retail sector in Q4 2020 contributed to the economic recovery. An analysis of China's GDP components and developments, comparing the GDP components of the TOP 4 economies vertically, shows that China has an advantage in attracting investment, which contributes to positive GDP growth. And by further comparing China's GDP changes over the past ten years horizontally, it is found that China has maintained steady growth and has good economic development prospects, so the amount of foreign investment attracted by China contributes the most to GDP in the TOP4 economic development comparison. Despite the influence of Covid-19, the trend of China being favoured by investors is still ongoing.

### 1.2020 world economics outlook and the achievement of China
#### 1.1 2020 Global Outbreak of the Coronavirus
In 2020, humanity entered the third decade of the 21st century. The New Coronavirus ravages the world. A sudden outbreak of New Coronavirus pneumonia has shocked and stirred the world. The New Coronavirus has many adverse effects on the human body. In the short term, muscle aches, pains, and loss of taste and smell may occur. While in a long time, impaired lung function due to New Coronavirus may lead to cognitive decline and neurological pathology, with reduced oxygen supply to brain cells, thus affecting intelligence. If one carries an underlying disease, this can cause other complications in a chain reaction.

Moreover, in 2020 there is no vaccine for the new coronavirus, no specific drug to treat it, and the virus spreads quickly through the population. Widespread transmission can lead to mutation of the virus. In 2020, the structure research of this new coronavirus and the development of a vaccine and an effective drug had been ongoing, but this has been hampered by mutations, such as the Alpha-virus, which was discovered in the UK in September 2020 and contained more than ten mutations. According to the Chinese Centre for Disease Control and Prevention, the new coronavirus that will be prevalent in 2020 has a higher mortality rate for people of older ages. To better protect people, governments have imposed lockdown to reduce the movement of people and maintain social distance to minimise the spread of the epidemic. People are constantly in lockdown conditions, which blows the global economy. Because people physically lockdown at home, consumer demand and production supply are reduced, which is detrimental to economic development. Gross domestic product (GDP) is used to measure the economic condition of a country. However, in this economic context, China achieved positive economic growth in 2020. This article focuses on how China has achieved positive economic growth.

Choropleth maps display divided geographical areas or regions that are coloured, shaded, or patterned with data variables. The Choropleth map below includes the areas of different countries with different colors according to the GDP range. Darker colours indicate countries with particularly large or small GDP values on the graph. The change in colour shade reflects the difference in GDP growth rate. 

```elm {l=hidden}
import VegaLite exposing (..)
path : String
path =
    "https://gicentre.github.io/data/"
```
```elm {l=hidden interactive}
globe : Projection -> List ProjectionProperty -> Spec
globe proj props =
    let
        cfg =
            configure
                << configuration (coView [ vicoStroke Nothing ])

        pDetails =
            [ width 700, height 400, projection (prType proj :: props) ]

        enc =
            encoding
                << color [
                    mName "properties.rate",
                    mQuant
                ]
                <<  tooltip [ tName "properties.name"]

        countrySpec =
            asSpec
                (pDetails
                    ++ [ dataFromUrl "./output/result1.json" [ topojsonFeature "countries1" ]
                        , enc []

                       , geoshape [ maStroke "white",
                       maStrokeWidth 0.1, maTooltip ttEncoding]
                       ]
                )
    in
    toVegaLite [
        cfg [],
        layer [ countrySpec ]
    ]
```

```elm {v}
-- worldMap : Spec
-- worldMap =
--     globe equalEarth []
```

```elm {v interactive}
geoMap : Spec
geoMap =
    let
        cfg =
            configure
                << configuration (coView [ vicoStroke Nothing ])

        data =
            dataFromUrl "https://raw.githubusercontent.com/lite2333/data/main/result.json" [ topojsonFeature "countries1" ]

        enc =
            encoding
                << color [
                    mName "properties.rate"
                    , mQuant
                    , mScale [ scScheme "blueorange" [ -1, 1 ] ]
                ]
                << tooltips
                [ [ tName "properties.title" ]
                , [ tName "properties.growthRate" ]
                ,[ tName "properties.gdp" ]
                , [ tName "properties.share" ]
                ]
    in
    toVegaLite
        [ width 600
        , height 400
        , cfg []
        , data
        , enc []
        , geoshape [
                maStroke "white",
                maStrokeWidth 0.1,
                maTooltip ttEncoding
            ]
        ]
```
<center>Fig.1.2 GDP (2020) by Country</center>
<center>Source: International Monetary Fund, World Economic Outlook Database, April 2021</center>


According to International Monetary Fund data, the United States remains the largest economy globally, with GDP (Nominal) over \$20 trillion in 2020. It represents a quarter share of the global economy (24.8%). China follows, with nearly \$15 trillion, or 17.4% of the world economy. Japan, Germany, and United Kingdom are \$5 trillion, $3.8 trillion, and \$2.7 trillion, respectively, next to China. China is the only developing country in the top 4 world GDP rankings, three times the third place in Japan's total GDP. Above all, China is a powerful player in the world economy.

#### 1.2 China achieve positive development under global economic retrenchment in 2020.
Among the 15 major world economic contributors, only China achieved positive economic growth in 2020 under Covid-19.

A pie chart is a two-dimensional circle which enables the audience to see a data comparison at a glance to make an immediate analysis or to understand information quickly. Accumulative Bar Chat represents an apparent relationship between size and value that allows easy comparison. The combination of pie and bar chart can clearly show the percentage of the top 15 countries that contributed to the world and others as a whole. At the same time, a use bar chart with different colours and lengths of each country gives more information about the top 15 GDP countries. It represents the quantity of each country’s contribution respectively.


[pie chart]
<center>Fig.1.2 GDP(2020) Contribution by Country</center>
<center>Source: International Monetary Fund, World Economic Outlook Database, April 2021</center>

The Fig.1.2 represents that 76% of the world GDP is contributed by 15 countries, e.g., the United States, China, Japan... They are the main components of the world economy.

According to International Monetary Fund data, the world's total GDP is $84,537.692. Compared to 2019, the global economy retreated by 3.21% on the impact of Covid-19. This is mainly because of the recession of the main components of the world economy.

The bar chart represents the world's leading economic contributors' GDP growth rate. Red indicates positive growth, and green indicates a negative GDP growth rate. Contrasting colours clearly show growth and decay.

[bar chart]

<center>Fig.1.3 GDP Growth Rate Ranking(2020) by Country</center>
<center>Source: International Monetary Fund, World Economic Outlook Database, April 2021</center>

China's economy continues to grow despite the uncertainty of 2020 due to Covid-19, rising to 2.67%, the only major global economy to achieve positive GDP growth in 2020. The analysis below will focus on how China accomplished this grade.

### 2.Reasons for China's positive economic growth
#### 2.1 China effectively controls the spread of the epidemic and creates conditions for the resumption of work and production.
Prevalence is a measure of disease that allows us to determine a person's likelihood of having a disease. The formula is "Accumulative Patients in the country/the population of the country." The prevalence rate choropleth map can represent the intensity of prevalence in each country and distribution worldwide.

The Choropleth Map clearly shows the prevalence rate of the GDP Top15 country, combining the representation of the land area, prevalence rate, accumulative patients, and population. The higher the prevalence, the darker the red. The lower the prevalence rate, the darker the green. China has a large land area and a low prevalence rate.

```elm {v interactive}
geoMap2 : Spec
geoMap2 =
    let
        cfg =
            configure
                << configuration (coView [ vicoStroke Nothing ])

        data =
            dataFromUrl "https://raw.githubusercontent.com/lite2333/data/main/result2.json" [ topojsonFeature "countries1" ]

        enc =
            encoding
                << color [
                    mName "properties.rate"
                    ,mScale rateColours
                    , mLegend []
                ]

                << tooltips
                [ [ tName "properties.name" ]
                , [ tName "properties.prevalenceRate" ]
                , [ tName "properties.accumulativePatients" ]
                , [ tName "properties.population" ]
                ]
    in
    toVegaLite
        [ width 600
        , height 400
        , cfg []
        , data
        , enc []
        , geoshape [
                maStroke "white",
                maStrokeWidth 0.1,
                maTooltip ttEncoding
            ]
        ]
```
```elm {l=hidden}
rateColours : List ScaleProperty
rateColours =
    categoricalDomainMap
        [ ( "none", "#c0c1c2" )
        , ( ">6%", "#A11F43" )
        , ( "2%~4%", "#cb3838" )
        , ( "1%~2%", "#f17343" )
        , ( "0.5%~1%", "#c2f19e" )
        , ( "0.1%~0.5%", "#0eb947" )
        , ( "<0.1%", "#048028" )
        ]
```
