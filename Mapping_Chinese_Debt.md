Mapping China City Economy
================
Po-Sheng Lee

Get the Map
===========

The first trouble I encounter is I cannot find a proper vector map data for China. Many of them are too detailed and are designed for specialized GIS software (such as the one provided on Harvard World map). These vector files take forever to read and to draw a map.

Fortunately, I find the vector data from [The Humanitarian Data Exchange](https://data.humdata.org/dataset/china-administrative-boundaries), which allows me to draw a prefectural level Chinese Map.

As in [Home Work 5](https://github.com/lpstntw/hw05/blob/master/china_city_income_land_economy.md), I take advantage of the tidy dataset from Kevin Luo, and analysze it through spatial visualization.

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

Maping Local Deficit
====================

Absolute Local Debt
-------------------

As we can see from the maps below, the anount of local deficit across China is homogenously small in 2003. However, in 2013, we can see an unequal distribution across China, with coastal region lower than northeastern and middle region. This result is identical with our previous result.

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
