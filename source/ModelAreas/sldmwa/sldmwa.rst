.. index::
    double: model area; sldmwa




==============================================================
San Luis Delta Mendota Water Authority
==============================================================
Written by Wendy Haw


Model Region and Spatial Coverage
=================================

The databases encompass the San Luis Delta Mendota Water Authority
(SLDMWA) regions. There are 29 distinct regions within this boundary.



.. table:: Table 1: Modeling regions utilized in the database

   ===================================  =================
   WDNAME                               HR NAME
   ===================================  =================
   BANTA-CARBONA I.D.                   San Joaquin River
   BROADVIEW W.D.                       San Joaquin River
   Byron Bethany (CVP)                  San Joaquin River
   CENTRAL CALIFORNIA I.D.              San Joaquin River
   CITY OF TRACY                        San Joaquin River
   COLUMBIA CANAL CO.                   San Joaquin River
   DEL PUERTO WATER DISTRICT            San Joaquin River
   EAGLE FIELD W.D.                     San Joaquin River
   FIREBAUGH CANAL W.D.                 San Joaquin River
   FRESNO SLOUGH W.D.                   Tulare Lake
   GRASSLANDS W.D.                      San Joaquin River
   HENRY MILLER RECLAMATION DIST. 2131  San Joaquin River
   JAMES I.D.                           Tulare Lake
   LAGUNA W.D.                          San Joaquin River
   MERCY SPRINGS W.D.                   San Joaquin River
   ORO LOMA W.D.                        San Joaquin River
   PACHECO W.D.                         San Joaquin River
   PANOCHE W.D.                         San Joaquin River
   PATTERSON W.D.                       San Joaquin River
   PLEASANT VALLEY W.D.                 Tulare Lake
   RECLAMATION DISTRICT 1606            Tulare Lake
   SAN BENITO CO. W.D.                  Central Coast
   SAN LUIS W.D.                        San Joaquin River
   SANTA CLARA VALLEY W.D.              San Francisco Bay
   THE WEST SIDE I.D.                   San Joaquin River
   TRANQUILLITY I.D.                    Tulare Lake
   Turner Island Water District         San Joaquin River
   WEST STANISLAUS I.D.                 San Joaquin River
   WESTLANDS W.D.                       Tulare Lake
   ===================================  =================


Crop Categories and Assignments
===============================

A key challenge in assembling these databases is how crops are
classified across different data sources. California agriculture
includes over 400 commodities, and it is not feasible to model each crop
individually. As a result, crops must be grouped into broader
categories.

Individual commodities in the land cover datasets from LandIQ grouped
into 23 crop categories to reduce quantities of data required for
modeling. Categories were based on existing DWR crop groups and were
revised to improve resolution of important commodities such as almonds,
pistachios, and walnuts. More information on this is given in the "Land
Cover" section. Each combination of crop category and hydrologic region
was assigned a proxy commodity which was used to bridge between the land
cover in the model and the economic data from the USDA NASS dataset.
Economic proxies were chosen following analysis of acreage and revenue
trends for NASS commodities within each hydrologic region to reflect
both the prevalence of individual crops and total economic value.
Relationships for category development and proxies are given in Table 2.



.. table:: Table 2. Model crop categories, commodities, and economic proxies

   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | **Crop Group**    | **LandIQ Commodities**                                                                 | **Economic Proxy Commodities** |
   +===================+========================================================================================+================================+
   | Alfalfa           | Alfalfa and alfalfa mixtures                                                           | HAY ALFALFA                    |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Almonds           | Almonds                                                                                | ALMONDS ALL                    |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Beans Dry         | Beans (dry)                                                                            | - BEANS DRY EDIBLE UNSPEC.     |
   |                   |                                                                                        | - BEANS LIMA LG. DRY           |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Berries           | - Bushberries                                                                          | - BERRIES STRAWBERRIES F MKT   |
   |                   | - Strawberries                                                                         | - BERRIES BLUEBERRIES          |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Subtropical       | - Citrus and Subtropical - No Subclass                                                 | - OLIVES                       |
   |                   | - Subtropical Fruits Misc.                                                             | - ORANGES NAVEL                |
   |                   | - Olives                                                                               |                                |
   |                   | - Kiwis                                                                                |                                |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Corn              | Corn, Sorghum or Sudan (grouped for remote sensing classification only)                | - CORN GRAIN                   |
   |                   |                                                                                        | - CORN SILAGE                  |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Cotton            | Cotton                                                                                 | - COTTN LINT UPLAND            |
   |                   |                                                                                        | - COTTN LINT PIMA              |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Cucurbits         | Melons, Squash, and Cucumbers                                                          | - SQUASH                       |
   |                   |                                                                                        | - MELONS CANTALOUPE            |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Field and Grain   | - Wheat                                                                                | WHEAT ALL                      |
   |                   | - Field Misc.                                                                          |                                |
   |                   | - Grain and Hay - Misc.                                                                |                                |
   |                   | - Grain and Hay - No Subclass                                                          |                                |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Grapes            | Vineyards - No Subclass                                                                | - GRAPE WINE                   |
   |                   |                                                                                        | - GRAPE TABLE                  |
   |                   |                                                                                        | - GRAPE RAISIN                 |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Lettuce           | - Cole crops (mixture of T22-T25)                                                      | LETTUCE HEAD                   |
   |                   | - Lettuce or Leafy Greens (grouped for remote sensing classification only)             |                                |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Onions and Garlic | Onions and Garlic                                                                      | ONIONS                         |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Orchards          | - Apples                                                                               | - PLUMS DRIED                  |
   |                   | - Avocados                                                                             | - CHERRIES SWEET               |
   |                   | - Cherries                                                                             | - PEACHES FREESTONE            |
   |                   | - Dates                                                                                |                                |
   |                   | - Deciduous - Misc.                                                                    |                                |
   |                   | - Deciduous - Mixed                                                                    |                                |
   |                   | - Peaches and Nectarines                                                               |                                |
   |                   | - Pears                                                                                |                                |
   |                   | - Plums, Prunes or Apricots (grouped for remote sensing classification only)           |                                |
   |                   | - Pomegranates                                                                         |                                |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Pasture           | - Pasture - Miscellaneous Grasses                                                      | N/A                            |
   |                   | - Pasture - Mixed                                                                      |                                |
   |                   | - Pasture - Native Improved                                                            |                                |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Pistachios        | Pistachios                                                                             | PISTACHIOS                     |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Potatoes          | - Potato or Sweet potato (grouped for remote sensing classification only)              | - POTATOES SWEET               |
   |                   | - Potatoes                                                                             | - POTATOES IRISH ALL           |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Rice              | - Rice                                                                                 | RICE MILLING                   |
   |                   | - Rice - Wild                                                                          |                                |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Safflower         | Safflower                                                                              | SAFFLOWER                      |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Sunflowers        | Sunflowers                                                                             | SUNFLOWER SEED PLANTING        |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Tomatoes          | Tomatoes (Processing)                                                                  | - TOMATES FRESH MARKET         |
   |                   |                                                                                        | - TOMATES PROCESING            |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Truck             | - Carrots                                                                              | PEPPERS BELL                   |
   |                   | - Peppers (Chili, Bell, etc.)                                                          |                                |
   |                   | - Truck Crops - Misc.                                                                  |                                |
   |                   | - Truck Crops - No Subclass                                                            |                                |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Walnuts           | Walnuts                                                                                | WALNUTS ENGISH                 |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+
   | Young Perennial   | Young Perennial (grouped for remote sensing or when CLASS C, D or V is not determined) | N/A                            |
   +-------------------+----------------------------------------------------------------------------------------+--------------------------------+


Table 3 shows the 2 crop classification schemes that are used: OpenAg
and DWR. DWR uses a more aggregated system with 19 crop groups while
OpenAg uses more detailed and expanded classifications with 23 crop
groups. Either classification system may be used in the database
assembly process depending on the context and the intended application.



.. table:: Table 3. Crop classification schemes

   =================  ====================
   OpenAg             DWR
   =================  ====================
   Alfalfa            Alfalfa
   Almonds            Almonds & Pistachios
   Beans Dry          Citrus & Subtropical
   Berries            Corn
   Corn               Cotton
   Cotton             Cucurbits
   Cucurbits          Dry Beans
   Field and Grain    Grain
   Grapes             Onions & Garlic
   Lettuce            Other Deciduous
   Onions and Garlic  Other Field Crops
   Orchards           Pasture
   Pasture            Potatoes
   Pistachios         Rice
   Potatoes           Safflower
   Rice               Sugar Beets
   Safflower          Tomato Processing
   Subtropical        Truck Crops
   Sunflowers         Vineyard
   Tomatoes
   Truck
   =================  ====================


Land Cover
==========

Field-level parcels for 2014, 2016, and 2018-2024 was provided by LandIQ
through the California Open Data portal. These geospatial layers were
intersected with the modeling region in Python using the GeoPandas
library and crop acreages were then calculated for each model region and
hydrologic region. When computing the land use acreage, there were
parcels that overlapped with multiple hydrologic regions. To remedy
this, the hydrologic region associated with the overlapped water
district (SLDMWA) was used.

In the LandIQ datasets, young perennials are reported as an unspecified
category without identifying the specific crop type. To allocate this
acreage, the young perennial acreage was distributed across
standing-bearing perennial crops (Almonds, Grapes, Orchards, Pistachios,
Subtropical, and Walnuts) based on each crop's share of total
standing-bearing acreage within a modeling region. For example, if a
region's standing-bearing acreage consists of 50 percent almonds, 20
percent walnuts, and 30 percent grapes, then the young perennial acreage
is assigned to these crops in the same proportions.

Price and Yield
===============

Price and yield data were obtained from the USDA National Agricultural
Statistics Service (NASS) County Agricultural Commissioner Reports,
which provide information on crop prices, yields, and acreage in
California. Values were averaged over the 2018-2020 period, and prices
were adjusted to 2024 dollars using the Consumer Price Index (CPI).
After compiling these data, representative price and yield values were
assigned to each aggregated crop category through a proxy-crop selection
process. When a single crop clearly dominates a category -- defined as
having an acreage share more than 10 percent higher than any other
crop -- that crop is designated as the proxy. If multiple crops have
similar acreage shares, an acreage-weighted average is computed, and the
crop whose price and yield are closest to that average is selected as
the representative proxy.

Some price and yield values were missing in the NASS reports. To address
these gaps, a hierarchical imputation procedure was applied, using
progressively broader spatial aggregates. Missing values were first
filled using averages for the same crop in neighboring counties. If
unavailable, averages within the same hydrologic region were used.
Remaining gaps were filled using averages from neighboring hydrologic
regions, and finally, statewide averages were applied as a last resort.

Several crop-specific adjustments were also required. For tomatoes,
fresh and processing types were distinguished based on regional
production patterns: coastal hydrologic regions were assigned fresh
tomatoes, while non-coastal regions were assigned processing tomatoes.
For grapes, multiple types (wine, table, raisin) were aggregated using
revenue-weighted averages at the hydrologic region level to reflect
their economic composition. For lettuce, consistent regional data were
unavailable, so values from the 2017 UC Davis Iceberg Lettuce cost and
return study were applied across all regions. Finally, when converting
from OpenAg to DWR crop classifications, multiple crops were combined
into broader groups. Acreage-weighted averages were used to ensure that
aggregated price and yield values reflect the relative land shares of
the underlying crops.

Applied Water
=============

Water use data was obtained from the California Department of Water
Resources (DWR) Agricultural Land and Water Use Estimates dataset for
the years 2018-2020. This dataset provides annual estimates of applied
water, irrigated crop acreages, crop evapotranspiration, and
evapotranspiration of applied water for 20 crop categories. A Python
script was used to extract the irrigated crop area (ICA; acre) and
applied water (AW; acre-ft/acre) data, aggregate them at the hydrologic
region scale, and compute the average applied water per acre-ft for each
crop, restricting the analysis to entries where AW values were greater
than zero.



.. math::

   Avg\ AW = \frac{AW}{ICA} \qquad (1)

While DWR uses a 20 crop classification system, the OpenAg database
expands a few of these crop classifications into separate categories.
For instance, DWR groups almonds and pistachios together while OpenAg
considers them as separate crop classifications. Additionally, lettuce
and berries are singled out of the truck crop group as individual
categories. To account for crop level water use disaggregation, an
additional Python script was employed to compute the average applied
water for these expanded crop categories using data from the previously
mentioned dataset for the years 2016-2019. The DWR applied water values
were scaled using crop-specific ratios to estimate crop-level applied
water:



.. math::

   {Final\ AW}_{c} = s_{c} * g \qquad (2)

where :math:`s` represents the split factor, which is the ratio of the
recent (2016-2019) average applied water from crop :math:`c` to the
baseline (2011-2013) applied water for the crop group. The term
:math:`g` represents the DWR crop group average applied water value. The
split factor is essentially a scaling ratio used to disaggregate applied
water values when converting between the DWR crop groups to the OpenAg
classifications. The following table presents the split factors applied
to derive individual crop-level applied water values. These per-crop
averages serve as the coefficients used to allocate water use across
individual crops.



.. table:: Table 4. Individual Crop Split Factors

   +------------------------+------------------------------------+----------------------+-------------------------------+--------------+
   | Crop Group (DWR)       | Crop Group Baseline AW (2011-2013) | Single Crop (OpenAg) | Individual Avg AW (2016-2019) | Split Factor |
   +========================+====================================+======================+===============================+==============+
   | Almonds and Pistachios | 3.9427                             | Almonds              | 4.3333                        | 1.10         |
   +                        +                                    +----------------------+-------------------------------+--------------+
   |                        |                                    | Pistachios           | 3.997528567                   | 1.01         |
   +------------------------+------------------------------------+----------------------+-------------------------------+--------------+
   | Truck                  | 2.063                              | Berries              | 2.676115961                   | 1.30         |
   +                        +                                    +----------------------+-------------------------------+--------------+
   |                        |                                    | Walnuts              | 3.829978110                   | 1.86         |
   +------------------------+------------------------------------+----------------------+-------------------------------+--------------+


A key limitation of the Agricultural Land and Water Use Estimates
dataset is that it does not report applied water values for fresh
tomatoes; therefore, processing tomato data was used as a proxy. The
dataset also does not report applied water values for certain crops in
specific hydrologic regions. To address these gaps, non-zero
crop-specific applied water values from neighboring hydrologic regions
were averaged and used as proxies. Applied water for sugar beets is not
reported in any hydrologic region, so values for "Other Field Crops"
within each region were used as a substitute. Omegawater for Pasture was
reduced to $10/acre-ft and for Field and Grain to $25/acre-ft to
maintain positive net revenues.

Costs
=====

The cost and return data are sourced from the UC Davis Agricultural and
Resource Economics Cost and Return Studies, which provide detailed
per-acre production cost information for a wide range of commodities,
including labor, land, supplies, and other inputs. The dataset includes
both current studies, which are preferred, and archived studies that are
used when more recent data are unavailable. A key challenge is that
these studies do not offer complete coverage across all crops and
hydrologic regions, making additional supplementation and harmonization
necessary to ensure consistent cost structures throughout the dataset.

To create a consistent cost dataset, production costs are expressed as
shares of total revenue rather than absolute dollar values. This
standardization allows meaningful comparison across crops with very
different price levels or production scales. Each cost component --
such as land, labor, or supplies -- is divided by total commodity
revenue to obtain its proportional share. Equation 3 provides the
formula used to calculate the cost shares:



.. math::

   cs_{x} = \frac{c_{x}}{c_{total}} \qquad (3)

where :math:`cs_x` represents the cost structure of the individual cost
component :math:`c_x` and :math:`c_{total}` is the total commodity
revenue.

Several crop-specific adjustments were required to achieve full
coverage. Some adjustments are similar to those implemented with the
price and yield data to ensure consistency. Cost data for pasture were
unavailable, so the cost structure from the 'Field and Grain' category
was used as a proxy. For tomatoes, fresh and processing types were
distinguished based on regional production patterns, with coastal
hydrologic regions assigned fresh tomatoes and non-coastal regions
assigned processing tomatoes. For grapes, multiple types -- wine, table,
and raisin -- were aggregated using revenue-weighted averages at the
hydrologic region level to reflect their economic composition. For
lettuce, consistent cost data were not available across regions, so
values from the 2017 UC Davis Iceberg Lettuce cost and return study were
applied statewide. Additional assumptions were made for water costs: a
standard value of $50 per acre-foot was applied to most crops, with
lower values for pasture and field crops and a higher value for lettuce.
When converting from OpenAg to DWR crop classifications, acreage-weighted
averages were used to ensure that aggregated cost shares reflect the
relative land contributions of each crop.

Addressing gaps in spatial and crop coverage was another crucial step.
Because cost and return studies do not cover all crops or all hydrologic
regions, missing values were supplemented using data from nearby
hydrologic regions or from the same crop in other regions when
available. In some cases, additional adjustments were required to
maintain consistency. For example, cost values for certain crops in the
Sacramento River region -- such as grapes, cucurbits, and safflower --
were replaced with values from the San Joaquin River region to ensure
alignment in cost structures across regions.

Supply Elasticities
===================

Elasticity of supply values were adapted from previous work by Jose
Manuel Rodriguez Flores for other agricultural economics modeling
projects focusing on the southern San Joaquin Valley and Westlands Water
District.

Crop supply elasticities were computed through the use of panel data
analysis and the partial adjustment framework for counties belonging to
the San Joaquin Valley. Proposed by Nerlove 1956, the framework relies
on the assumption that farmers use crop price information from the
previous year to determine the production size of the same crop in the
present year. Panel data estimations were computed via single-equation
estimation. The approaches used were Feasible Generalized Least Squares
(FGLS), Pooled Ordinary Least Squares (OLS), Fixed Effects Models (FE),
and Random Effects Models (RE). Model selection for crop type was
dependent on the characteristics of the panels and data. The dataset has
a small number of panels (N = counties) and a large number of time
periods (T = years).

The following single equation formulation was used:



.. math::

   {lnA}_{t} = \beta_{0} + \beta_{1}{lnA}_{t-1} + \beta_{2}{lnP}_{t-1} \qquad (4)

where :math:`\ln A_t` represents the natural logarithm of harvested
acres in year :math:`t`. This value is modeled as a function of
:math:`\ln A_{t-1}` and :math:`\ln P_{t-1}`, the previous year's
harvested acres and price, respectively. These two values serve as a
proxy for farmers' price expectation in year :math:`t`. Both
:math:`\beta_1 \geq 0` and :math:`\beta_2 \geq 0` are expected, in
which the number of acres increases due to an increase in anticipated
prices. The coefficient :math:`\beta_2` represents the short-term
supply price elasticity while the ratio
:math:`\frac{\beta_2}{(1-\beta_1)}` is the long-term supply response.

The data used was obtained from USDA Agricultural Commissioner reports,
which provides annual data on harvested acres, price, yield, production,
and value of each crop for all counties in California. To have balanced
panels, counties for each crop were selected only if they had a complete
time series from 1980-2016. Proxy crops were derived from those utilized
in the Statewide Agricultural Production Model (SWAP). These crop supply
elasticity values were then expanded for the OpenAg crop classifications
where certain groups were separated into individual categories.

The original elasticity values are defined using the OpenAg crop
classification. To align these values with the DWR classification,
certain crops in the OpenAg scheme are aggregated together. The
following table summarizes the crop groupings used. For each DWR crop
group, the aggregated elasticity value is computed as the simple average
of the individual elasticities of the corresponding OpenAg crops.



.. table:: Table 5. DWR Crop Group Conversion to OpenAg Single Crop

   +------------------------+----------------------+
   | Crop Group (DWR)       | Single Crop (OpenAg) |
   +========================+======================+
   | Almonds and Pistachios | Almonds              |
   +                        +----------------------+
   |                        | Pistachios           |
   +------------------------+----------------------+
   | Truck                  | Berries              |
   +                        +----------------------+
   |                        | Lettuce              |
   +                        +----------------------+
   |                        | Walnuts              |
   +------------------------+----------------------+
   | Other Deciduous        | Orchards             |
   +                        +----------------------+
   |                        | Walnuts              |
   +------------------------+----------------------+

Getting Access
----------------
To get access for additional staff, please `contact the WSM Lab <https://wsm.ucmerced.edu/contact-us/>`_.