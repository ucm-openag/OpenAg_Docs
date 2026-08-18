.. index::
    double: washington; model area

.. _WashingtonModelDoc:

The Walla Walla, Yakima, and Okanogan Model
===========================

====================================================
Land Use by Region Lookup Tables (2015-2025)
====================================================

Overview
========

This document describes two lookup tables prepared for the **Yakima** and
**Walla Walla** basins. Each table reports irrigated acreage by geographic sub-region,
year and crop type.

Schema
======

Both source files share the same five core columns:

.. list-table::
   :header-rows: 1
   :widths: 15 12 73

   * - Column
     - Type
     - Description
   * - ``Region``
     - string
     - Irrigation district, sub-basin, or reporting area within the
       basin.
   * - ``Year``
     - integer
     - Calendar year of the reported acreage (2015-2025 in both
       files).
   * - ``CropGroup``
     - string
     - Broad crop category (e.g. ``Cereal Grain``, ``Orchard``).
   * - ``CropType``
     - string
     - Specific crop grown within the ``CropGroup`` (e.g. ``Barley``,
       ``Apple``).
   * - ``Area_acres``
     - float
     - Irrigated acreage attributed to that ``CropType``, in the given
       ``Region`` and ``Year``.

.. list-table:: File Summary
   :header-rows: 1
   :widths: 40 15 10 12 12 11

   * - File
     - Basin
     - Rows
     - Regions
     - Crop Groups
     - Crop Types
   * - ``WallaWalla_LandUse_By_Region_2015_2025.csv``
     - Walla Walla
     - 2,218
     - 19
     - 17
     - 93
   * - ``Yakima_LandUse_By_Region_2015_2025.csv``
     - Yakima
     - 5,535
     - 25
     - 19
     - 123

.. note::
   The Yakima file, as provided, contains four additional trailing
   columns (unlabeled, empty in every row) and a UTF-8 byte-order mark
   (BOM). Both should be handled during ingestion — see *Before
   Uploading to OpenAg* below.

Crop Classification Reference
==============================

For each basin, every distinct ``CropGroup`` / ``CropType`` combination
that appears in the data. For example, under ``Cereal Grain`` the
tables identify whether acreage was ``Barley``, ``Oat``, ``Wheat``, or
another grain type such as ``Rye``, ``Triticale``, or ``Buckwheat``.

Some crop types appear under more than one ``CropGroup`` because the
grouping changed between 2015 and 2025 (e.g. ``Pasture``, ``Hemp``) —
each combination that actually occurs in the data is listed once. See
*CropGroup labels have shifted over time* under *Data Notes* for
detail.

.. csv-table:: Walla Walla – Crop Classification Reference (96 entries)
   :header-rows: 1
   :widths: 35, 45

   "Crop Group","Crop Type"
   "Berry","Blueberry"
   "Berry","Caneberry"
   "Berry","Strawberry"
   "Cereal Grain","Barley"
   "Cereal Grain","Buckwheat"
   "Cereal Grain","Corn, Field"
   "Cereal Grain","Oat"
   "Cereal Grain","Rye"
   "Cereal Grain","Sorghum"
   "Cereal Grain","Triticale"
   "Cereal Grain","Wheat"
   "Cereal Grain","Wheat Fallow"
   "Commercial Tree","Christmas Tree"
   "Commercial Tree","Poplar"
   "Commercial Tree","Silviculture"
   "Developed","Developed"
   "Green Manure","Cover Crop"
   "Green Manure","Green Manure"
   "Hay/Silage","Alfalfa Hay"
   "Hay/Silage","Alfalfa/Grass Hay"
   "Hay/Silage","Barley Hay"
   "Hay/Silage","Grass Hay"
   "Hay/Silage","Hay/Silage, Mixed"
   "Hay/Silage","Oat Hay"
   "Hay/Silage","Pea Hay"
   "Hay/Silage","Sudangrass"
   "Hay/Silage","Timothy"
   "Hay/Silage","Triticale Hay"
   "Hay/Silage","Wheat Hay"
   "Herb","Cannabis"
   "Herb","Hemp"
   "Herb","Hops"
   "Herb","Marijuana"
   "Herb","Mint"
   "Melon","Watermelon"
   "Nursery","Nursery, Greenhouse"
   "Nursery","Nursery, Lavender"
   "Nursery","Nursery, Orchard/Vineyard"
   "Nursery","Nursery, Ornamental"
   "Oilseed","Camelina"
   "Oilseed","Canola"
   "Oilseed","Soybean"
   "Oilseed","Sunflower"
   "Orchard","Apple"
   "Orchard","Apricot"
   "Orchard","Cherry"
   "Orchard","Chestnut"
   "Orchard","Nectarine/Peach"
   "Orchard","Pear"
   "Orchard","Walnut"
   "Other","Alkali Bee Bed"
   "Other","CRP/Conservation"
   "Other","Developed"
   "Other","Fallow"
   "Other","Fallow, Idle"
   "Other","Fallow, Tilled"
   "Other","Pasture"
   "Other","Research Station"
   "Other","Unknown"
   "Other","Wildlife Feed"
   "Pasture","Pasture"
   "Seed","Alfalfa Seed"
   "Seed","Bean Seed"
   "Seed","Beet Seed"
   "Seed","Corn Seed"
   "Seed","Grass Seed"
   "Seed","Hemp"
   "Seed","Onion Seed"
   "Seed","Pea Seed"
   "Seed","Radish Seed"
   "Seed","Safflower Seed"
   "Seed","Seed, Other"
   "Seed","Sunflower Seed"
   "Turfgrass","Driving Range"
   "Turfgrass","Golf Course"
   "Turfgrass","Sod Farm"
   "Vegetable","Asparagus"
   "Vegetable","Bean, Dry"
   "Vegetable","Bean, Garbanzo"
   "Vegetable","Bean, Green"
   "Vegetable","Chickpea"
   "Vegetable","Corn, Sweet"
   "Vegetable","Garlic"
   "Vegetable","Lentil"
   "Vegetable","Market Crops"
   "Vegetable","Onion"
   "Vegetable","Pea, Dry"
   "Vegetable","Pea, Green"
   "Vegetable","Potato"
   "Vegetable","Pumpkin"
   "Vegetable","Radish"
   "Vegetable","Spinach"
   "Vegetable","Squash"
   "Vegetable","Vegetable, Unknown"
   "Vineyard","Grape, Unknown"
   "Vineyard","Grape, Wine"

.. csv-table:: Yakima – Crop Classification Reference (128 entries)
   :header-rows: 1
   :widths: 35, 45

   "Crop Group","Crop Type"
   "Berry","Blueberry"
   "Berry","Caneberry"
   "Berry","Currant"
   "Berry","Kiwi"
   "Berry","Strawberry"
   "Cereal Grain","Barley"
   "Cereal Grain","Buckwheat"
   "Cereal Grain","Cereal Grain, Unknown"
   "Cereal Grain","Corn, Field"
   "Cereal Grain","Corn, Unknown"
   "Cereal Grain","Mint"
   "Cereal Grain","Oat"
   "Cereal Grain","Rye"
   "Cereal Grain","Triticale"
   "Cereal Grain","Wheat"
   "Cereal Grain","Wheat Fallow"
   "Commercial Tree","Christmas Tree"
   "Commercial Tree","Poplar"
   "Commercial Tree","Silviculture"
   "Developed","Developed"
   "Flower Bulb","Allium"
   "Flower Bulb","Iris"
   "Flower Bulb","Peony"
   "Green Manure","Cover Crop"
   "Green Manure","Green Manure"
   "Green Manure","Legume Cover"
   "Green Manure","Yellow Mustard"
   "Hay/Silage","Alfalfa Hay"
   "Hay/Silage","Alfalfa/Grass Hay"
   "Hay/Silage","Barley Hay"
   "Hay/Silage","Clover Hay"
   "Hay/Silage","Clover/Grass Hay"
   "Hay/Silage","Grass Hay"
   "Hay/Silage","Hay/Silage, Mixed"
   "Hay/Silage","Hay/Silage, Unknown"
   "Hay/Silage","Oat Hay"
   "Hay/Silage","Pea Hay"
   "Hay/Silage","Sorghum"
   "Hay/Silage","Sudangrass"
   "Hay/Silage","Timothy"
   "Hay/Silage","Triticale Hay"
   "Hay/Silage","Wheat Hay"
   "Herb","Cannabis"
   "Herb","Hemp"
   "Herb","Hops"
   "Herb","Marijuana"
   "Herb","Medicinal Herb"
   "Herb","Mint"
   "Herb","Tobacco"
   "Melon","Melon, Unknown"
   "Melon","Watermelon"
   "Nursery","Nursery, Greenhouse"
   "Nursery","Nursery, Lavender"
   "Nursery","Nursery, Orchard/Vineyard"
   "Nursery","Nursery, Ornamental"
   "Nursery","Nursery, Silviculture"
   "Oilseed","Canola"
   "Oilseed","Dill"
   "Oilseed","Mustard"
   "Oilseed","Sunflower"
   "Orchard","Apple"
   "Orchard","Apricot"
   "Orchard","Cherry"
   "Orchard","Chestnut"
   "Orchard","Filbert"
   "Orchard","Nectarine/Peach"
   "Orchard","Orchard, Unknown"
   "Orchard","Pear"
   "Orchard","Plum"
   "Orchard","Walnut"
   "Other","Alkali Bee Bed"
   "Other","CRP/Conservation"
   "Other","Developed"
   "Other","Fallow"
   "Other","Fallow, Idle"
   "Other","Fallow, Tilled"
   "Other","Pasture"
   "Other","Research Station"
   "Other","Unknown"
   "Other","Wildlife Feed"
   "Pasture","Pasture"
   "Seed","Alfalfa Seed"
   "Seed","Bean Seed"
   "Seed","Bluegrass Seed"
   "Seed","Canola Seed"
   "Seed","Carrot Seed"
   "Seed","Clover Seed"
   "Seed","Conifer Seed"
   "Seed","Corn Seed"
   "Seed","Fescue Seed"
   "Seed","Grass Seed"
   "Seed","Hemp"
   "Seed","Onion Seed"
   "Seed","Pea Seed"
   "Seed","Potato Seed"
   "Seed","Seed, Other"
   "Seed","Sunflower Seed"
   "Seed","Swiss Chard Seed"
   "Turfgrass","Driving Range"
   "Turfgrass","Golf Course"
   "Turfgrass","Sod Farm"
   "Unknown","Unknown"
   "Vegetable","Asparagus"
   "Vegetable","Bean, Dry"
   "Vegetable","Bean, Green"
   "Vegetable","Cabbage"
   "Vegetable","Carrot"
   "Vegetable","Corn, Sweet"
   "Vegetable","Cucumber"
   "Vegetable","Eggplant"
   "Vegetable","Garlic"
   "Vegetable","Market Crops"
   "Vegetable","Onion"
   "Vegetable","Pea, Dry"
   "Vegetable","Pea, Green"
   "Vegetable","Pepper"
   "Vegetable","Potato"
   "Vegetable","Pumpkin"
   "Vegetable","Radish"
   "Vegetable","Rhubarb"
   "Vegetable","Rutabaga"
   "Vegetable","Squash"
   "Vegetable","Tomato"
   "Vegetable","Vegetable, Unknown"
   "Vineyard","Grape, Juice"
   "Vineyard","Grape, Table"
   "Vineyard","Grape, Unknown"
   "Vineyard","Grape, Wine"


Region Reference
=================

One row per region across both basins, summarizing the number of
distinct crop types ever reported and total/average acreage across the
full 2015-2025 span (all crop types combined).

.. csv-table:: Region Reference – Both Basins (acreage summed across all Crop Types, 2015-2025)
   :header-rows: 1
   :widths: 30, 12, 14, 10, 16, 14

   "Region","Basin","Years Covered","Crop Types Tracked","Total Acreage (sum, all yrs)","Avg. Annual Acreage"
   "ARTESIA IRRIGATION DISTRICT NO. 8","Walla Walla","2015–2025 (11 yrs)","4","134","12"
   "BLALOCK IRRIGATION DISTRICT NO. 3","Walla Walla","2015–2025 (11 yrs)","20","2,262","206"
   "BLALOCK ORCHARDS IRRIGATION DISTRICT NO. 12","Walla Walla","2015–2025 (11 yrs)","13","500","45"
   "BRADEN IRRIGATION DISTRICT NO. 20","Walla Walla","2015–2025 (11 yrs)","11","481","44"
   "CONSOLIDATED IRRIGATION DISTRICT NO. 14","Walla Walla","2015–2025 (11 yrs)","11","552","50"
   "EAST SIDE IRRIGATION DISTRICT NO. 6","Walla Walla","2015–2025 (11 yrs)","23","10,114","919"
   "GARDENA FARMS DISTRICT NO. 13","Walla Walla","2015–2025 (11 yrs)","34","70,485","6,408"
   "GREEN TANK IRRIGATION DISTRICT NO. 11","Walla Walla","2015–2025 (11 yrs)","4","22","2"
   "HUDSON BAY IRRIGATION DISTRICT NO.","Walla Walla","2015–2025 (11 yrs)","12","831","76"
   "HYDRO-IRRIGATION DISTRICT NO. 9","Walla Walla","2015–2025 (11 yrs)","11","968","88"
   "Irrigated area outside irrigation districts","Walla Walla","2015–2025 (11 yrs)","89","490,285","44,571"
   "LOWDEN IRRIGATION DISTRICT NO. 2","Walla Walla","2015–2025 (11 yrs)","12","3,458","314"
   "MUD CREEK IRRIGATION DISTRICT NO. 7","Walla Walla","2015–2025 (11 yrs)","10","2,976","271"
   "ORCHARD IRRIGATION DISTRICT NO. 10","Walla Walla","2015–2025 (11 yrs)","9","124","11"
   "TOUCHET IRRIGATION DISTRICT NO. 16","Walla Walla","2015–2025 (11 yrs)","36","27,738","2,522"
   "TWO RIVERS IRRIGATION DISTRICT NO. 19","Walla Walla","2015–2025 (11 yrs)","17","39,844","3,622"
   "WALLA WALLA WATER & POWER DISTRICT NO. 18","Walla Walla","2015–2025 (11 yrs)","10","16,948","1,541"
   "WATER DISTRIBUTION DISTRICT NO. 1","Walla Walla","2015–2025 (11 yrs)","5","117","11"
   "WEST SIDE IRRIGATION DISTRICT NO. 5","Walla Walla","2015–2025 (11 yrs)","26","18,219","1,656"
   "Ahtanum","Yakima","2015–2025 (11 yrs)","25","44,619","4,056"
   "Buena","Yakima","2015–2025 (11 yrs)","17","5,419","493"
   "Bull Ditch","Yakima","2015–2025 (11 yrs)","14","12,194","1,109"
   "Cascade","Yakima","2015–2025 (11 yrs)","34","97,692","8,881"
   "Ellensburg Wat","Yakima","2015–2025 (11 yrs)","34","100,172","9,107"
   "FGP","Yakima","2015–2025 (11 yrs)","9","5,065","460"
   "Fowler Ditch","Yakima","2015–2025 (11 yrs)","9","9,087","826"
   "Home","Yakima","2015–2025 (11 yrs)","1","271","25"
   "Irrigated area outside irrigation districts","Yakima","2015–2025 (11 yrs)","63","615,451","55,950"
   "KID","Yakima","2015–2025 (11 yrs)","39","138,092","12,554"
   "KRD","Yakima","2015–2025 (11 yrs)","51","564,886","51,353"
   "Moxee-Selah","Yakima","2015–2025 (11 yrs)","24","47,041","4,276"
   "Naches-Selah","Yakima","2015–2025 (11 yrs)","27","75,776","6,889"
   "Not In I.D.","Yakima","2015–2025 (11 yrs)","32","68,945","6,268"
   "Olsen","Yakima","2015–2025 (11 yrs)","11","5,136","467"
   "Packwood","Yakima","2015–2025 (11 yrs)","9","6,515","592"
   "Roza","Yakima","2015–2025 (11 yrs)","59","755,216","68,656"
   "SVID","Yakima","2015–2025 (11 yrs)","73","688,812","62,619"
   "Terrace Heights","Yakima","2015–2025 (11 yrs)","11","1,029","94"
   "Throp Mill","Yakima","2015–2025 (11 yrs)","3","736","67"
   "Union Gap","Yakima","2015–2025 (11 yrs)","21","22,388","2,035"
   "Wenas","Yakima","2015–2025 (11 yrs)","15","19,123","1,738"
   "West Side","Yakima","2015–2025 (11 yrs)","21","45,532","4,139"
   "Yakima-Tieton","Yakima","2015–2025 (11 yrs)","39","216,126","19,648"
   "Yakima-Wapato","Yakima","2015–2025 (11 yrs)","78","1,192,470","108,406"

.. note::
   "Total Acreage" sums every ``Area_acres`` value reported for that
   region across all 11 years and all crop types — it is a cumulative
   figure, not a single-year snapshot. "Avg. Annual Acreage" divides
   that sum by the number of years reported (11 for every region) as a
   rough per-year scale indicator.

Acreage by Crop Group and Year
=================================

Total acreage per ``CropGroup``, summed across all regions in the
basin, for each reported year. Figures are rounded to the nearest
acre.

.. csv-table:: Walla Walla – Total Acreage by Crop Group and Year (all regions summed)
   :header-rows: 1
   :widths: 16, 8, 8, 8, 8, 8, 8, 8, 8, 8, 8, 8

   "Crop Group","2015","2016","2017","2018","2019","2020","2021","2022","2023","2024","2025"
   "Berry","31","31","31","25","25","25","29","29","36","38","45"
   "Cereal Grain","17,858","17,858","18,411","19,663","21,389","21,479","17,293","17,293","17,412","16,419","35,486"
   "Commercial Tree","52","52","52","52","52","52","0","0","0","28","32"
   "Developed","0","0","0","33","33","33","43","43","44","68","799"
   "Green Manure","0","0","0","2","2","2","127","127","127","36","36"
   "Hay/Silage","9,802","9,806","9,299","9,192","9,311","9,311","9,147","9,146","9,020","7,519","7,878"
   "Herb","711","711","332","444","444","444","120","127","127","10","10"
   "Melon","1","1","1","1","1","1","0","0","0","1","1"
   "Nursery","27","22","17","11","11","11","14","14","14","13","11"
   "Oilseed","165","165","365","467","318","318","738","738","795","830","1,044"
   "Orchard","1,750","1,750","1,819","1,832","1,818","1,858","1,816","1,816","1,816","1,495","1,496"
   "Other","5,769","5,745","6,026","896","1,096","1,096","1,178","1,178","1,259","2,140","8,613"
   "Pasture","0","0","0","5,219","5,379","5,379","5,601","5,601","5,536","5,396","5,804"
   "Seed","14,560","14,624","15,581","12,806","12,189","12,189","12,893","12,885","12,781","14,174","14,258"
   "Turfgrass","436","436","436","425","425","425","398","398","397","402","402"
   "Vegetable","6,279","6,279","5,362","7,578","6,568","6,517","7,951","7,951","8,438","8,963","9,490"
   "Vineyard","1,783","1,798","1,868","1,812","1,823","1,823","1,816","1,816","2,260","2,149","2,176"

.. csv-table:: Yakima – Total Acreage by Crop Group and Year (all regions summed)
   :header-rows: 1
   :widths: 16, 8, 8, 8, 8, 8, 8, 8, 8, 8, 8, 8

   "Crop Group","2015","2016","2017","2018","2019","2020","2021","2022","2023","2024","2025"
   "Berry","1,366","1,376","1,376","1,387","1,532","1,538","1,717","1,717","1,695","1,546","1,546"
   "Cereal Grain","67,255","66,480","66,785","62,120","60,541","61,071","63,091","63,237","64,140","69,312","69,322"
   "Commercial Tree","26","30","30","29","51","51","41","41","41","89","89"
   "Developed","0","0","0","1,411","1,460","1,483","1,782","1,783","1,770","1,593","1,573"
   "Flower Bulb","5","5","17","0","12","11","11","11","11","16","16"
   "Green Manure","121","273","273","173","173","173","115","115","21","47","47"
   "Hay/Silage","97,216","95,572","94,875","91,643","93,800","93,942","92,829","92,814","92,900","84,367","84,392"
   "Herb","44,590","46,246","47,350","50,112","50,373","50,195","50,912","51,048","50,788","40,961","40,960"
   "Melon","125","71","71","71","182","182","567","567","561","624","624"
   "Nursery","914","1,039","1,033","1,004","1,070","1,064","977","978","1,004","740","740"
   "Oilseed","1,112","1,122","1,122","1,275","1,234","1,234","1,238","1,238","1,238","1,383","1,386"
   "Orchard","85,397","85,116","85,390","85,630","85,651","85,163","80,910","80,954","80,766","79,735","79,758"
   "Other","77,793","80,114","80,002","17,559","17,920","17,488","11,210","11,062","11,127","22,995","23,004"
   "Pasture","0","0","0","68,487","69,244","69,752","70,401","70,404","70,225","69,070","69,131"
   "Seed","1,097","1,611","1,611","2,438","1,723","1,723","771","696","696","880","880"
   "Turfgrass","1,719","1,725","1,725","1,710","1,705","1,700","1,697","1,697","1,679","1,671","1,679"
   "Unknown","89","0","0","0","0","0","0","0","0","0","0"
   "Vegetable","13,119","12,884","12,906","13,640","12,454","12,000","12,733","12,619","11,419","12,907","12,911"
   "Vineyard","39,595","40,065","40,007","38,786","38,534","38,340","35,474","35,412","35,689","35,535","35,543"