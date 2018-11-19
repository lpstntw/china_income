Mapping China City Economy
================
Po-Sheng Lee

Get the Map
===========

The first trouble I encounter is I cannot find a proper vector map data for China. Many of them are too detailed and are designed for specialized GIS software (such as the one provided on Harvard World map). These vector files take forever to read and to draw a map.

Fortunately, I find the vector data from [The Humanitarian Data Exchange](https://data.humdata.org/dataset/china-administrative-boundaries), which allows me to draw a prefectural level Chinese Map.

As in [Home Work 5](https://github.com/lpstntw/hw05/blob/master/china_city_income_land_economy.md), I take advantage of the tidy dataset from Kevin Luo, and analysze it through spatial visualization.

    ## Warning: package 'tidyverse' was built under R version 3.4.2

    ## ─ Attaching packages ──────────────────────────── tidyverse 1.2.1 ─

    ## ✔ ggplot2 3.1.0.9000     ✔ purrr   0.2.5     
    ## ✔ tibble  1.4.2          ✔ dplyr   0.7.6     
    ## ✔ tidyr   0.8.1          ✔ stringr 1.3.1     
    ## ✔ readr   1.1.1          ✔ forcats 0.3.0

    ## Warning: package 'tibble' was built under R version 3.4.3

    ## Warning: package 'tidyr' was built under R version 3.4.4

    ## Warning: package 'purrr' was built under R version 3.4.4

    ## Warning: package 'dplyr' was built under R version 3.4.4

    ## Warning: package 'stringr' was built under R version 3.4.4

    ## Warning: package 'forcats' was built under R version 3.4.3

    ## ─ Conflicts ───────────────────────────── tidyverse_conflicts() ─
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

    ## Warning: package 'sf' was built under R version 3.4.4

    ## Linking to GEOS 3.6.1, GDAL 2.1.3, PROJ 4.9.3

    ## Warning: package 'leaflet' was built under R version 3.4.4

    ## Warning: package 'viridis' was built under R version 3.4.4

    ## Loading required package: viridisLite

    ## Warning: package 'viridisLite' was built under R version 3.4.3

    ## Reading layer `chn_admbnda_adm1_ocha' from data source `/Users/leepo-sheng/Dropbox/UChicago/cfss/hw 07/chn_admbnda_adm1_ocha/chn_admbnda_adm1_ocha.shp' using driver `ESRI Shapefile'
    ## Simple feature collection with 57 features and 6 fields
    ## geometry type:  MULTIPOLYGON
    ## dimension:      XY
    ## bbox:           xmin: 73.5577 ymin: 18.16132 xmax: 134.7264 ymax: 53.53136
    ## epsg (SRID):    4326
    ## proj4string:    +proj=longlat +datum=WGS84 +no_defs

    ## Reading layer `chn_admbnda_adm2_ocha' from data source `/Users/leepo-sheng/Dropbox/UChicago/cfss/hw 07/chn_admbnda_adm2_ocha/chn_admbnda_adm2_ocha.shp' using driver `ESRI Shapefile'
    ## Simple feature collection with 361 features and 12 fields
    ## geometry type:  MULTIPOLYGON
    ## dimension:      XY
    ## bbox:           xmin: 73.5577 ymin: 18.16132 xmax: 134.7264 ymax: 53.53136
    ## epsg (SRID):    4326
    ## proj4string:    +proj=longlat +datum=WGS84 +no_defs

    ## Warning: package 'bindrcpp' was built under R version 3.4.4

    ## Parsed with column specification:
    ## cols(
    ##   code = col_integer(),
    ##   city = col_character(),
    ##   province = col_character(),
    ##   year = col_integer(),
    ##   built_district = col_integer(),
    ##   pub_income = col_integer(),
    ##   pub_expend = col_integer(),
    ##   dist_pop = col_double(),
    ##   city_pop = col_double(),
    ##   gdp = col_integer(),
    ##   primary_gdp_per = col_double(),
    ##   secondary_gdp_per = col_double(),
    ##   tertiary_gdp_per = col_double(),
    ##   output_value = col_double(),
    ##   output_dom = col_integer(),
    ##   vat = col_integer(),
    ##   invest_fixassets = col_integer(),
    ##   invest_realestate = col_integer(),
    ##   electric_use = col_double()
    ## )

    ## Warning in rbind(names(probs), probs_f): number of columns of result is not
    ## a multiple of vector length (arg 1)

    ## Warning: 6 parsing failures.
    ## row # A tibble: 5 x 5 col     row col              expected              actual file                 expected   <int> <chr>            <chr>                 <chr>  <chr>                actual 1  1460 output_dom       no trailing characte… .1     'cityincome2003_13.… file 2  1548 output_dom       no trailing characte… .8     'cityincome2003_13.… row 3  1812 output_dom       no trailing characte… .3     'cityincome2003_13.… col 4  1817 secondary_gdp_p… no trailing characte… :19:00 'cityincome2003_13.… expected 5  2159 output_value     no trailing characte… :      'cityincome2003_13.…
    ## ... ................. ... .......................................................................... ........ .......................................................................... ...... .......................................................................... .... .......................................................................... ... .......................................................................... ... .......................................................................... ........ ..........................................................................
    ## See problems(...) for more details.

Maping Local Deficit
====================

Absolute Local Debt
-------------------

As we can see from the maps below, the anount of local deficit across China is homogenously small in 2003. However, in 2013, we can see an unequal distribution across China, with coastal region lower than northeastern and middle region. This result is identical with our previous result.

    ## Warning: Column `ADM2_EN`/`city` joining factor and character vector,
    ## coercing into character vector

    ## Warning: Column `ADM2_EN`/`city` joining factor and character vector,
    ## coercing into character vector

    ## Warning: Column `ADM2_EN`/`city` joining factor and character vector,
    ## coercing into character vector

![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20deficit%20in%20same%20scale-1.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20deficit%20in%20same%20scale-2.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20deficit%20in%20same%20scale-3.png)

Relative Local Debt
-------------------

The three plots below illustrate the ranking of local debt in 2003, 2008 and 2013. Dark red denotes the highest rank of deficit and light orange indicates the lowest rank of deficit. We can see that the southern coastal areas used to be some of the most indebted locales in 2003; however, in 2008, the most indebted region became the central region, and this trend keeps on to 2013. Aside from the changes in central and coastal region, northeastern region was still highly indebted during this time period. It might be attributed to the decline of heavy industry in this region.

![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20deficit%20in%20comparison-1.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20deficit%20in%20comparison-2.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20deficit%20in%20comparison-3.png)

Domestic Industrial Output
--------------------------

The following are mapping of domestic industrial output. During this time period, there's a significant rise in industrial output in coastal and middle region prefactural level cities. Particularly around Shandong and Jiangsu provinces. This might be the result of expansion in petroleum, chemical and car industry in this area.

![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20output-1.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20output-2.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20output-3.png)

The percantage of secondary and tertiary industry in all GDP is reported as followed. 2003 to 2008 is a industrialization period, as the secondary industry boom in many central and coastal region. From 2008 to 2013, industrialization seems to come to a stalemate, with some coastal prefectures' secondary industry output shrinking as tertiary industry output rising.

![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20gdp%20structure-1.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20gdp%20structure-2.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20gdp%20structure-3.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20gdp%20structure-4.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20gdp%20structure-5.png)![](Mapping_Chinese_Debt_files/figure-markdown_github/mapping%20gdp%20structure-6.png)

Conclusion Remark
-----------------

As we can see from the maps in this report, during 2003 to 2008, the rise of debt is mild, accomapnying with a rise in industrial sector. In contrast, local debt rise drastically from 2008 to 2013 despite the waning industrial sector in many area. This spatial visualization analysis informs us on the varieties of industrial transformation, debt accumulation and their possible relation. While coastal area underwent a post-industrial transformation with moderate deficit growth, middle and northeastern region witness a drastic rise in debt accompanying by (heavy) industry expansion. This unequal geographical development could be a starting point for further study.
