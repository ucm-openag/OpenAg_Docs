.. _CropModificationsDoc:

Crop Modifications Details
============================
..
    This document should be about the details of a specific crop modification including parameters, options, and
    interactions - it's not about general application processes for creating the modifications - that goes in
    Make Model Run

.. contents::
    :local:

.. _CropModificationsDocOverview:

Overview
----------

.. todo:: Add Crop Modifications Screenshot

Crop modifications are the second step in :ref:`creating an OpenAg model run <MakeModelRunsDoc>` and allow for adjustment
of crop-specific parameters. By default, crop modification :ref:`cards <CardsConceptSection>` apply to data for the crop within every
:ref:`region <RegionConceptSection>` where the crop is present, though it is possible to specify crop parameters
per-region (see :ref:`RegionLinkedCropsSection`)

.. _CropModificationParametersSection:

Parameters
-------------
.. figure:: crop_modification_example.png

    A crop modification card, showing the three primary adjustments to crop data in OpenAg

Crop Cards support three parameters:

#. Price:
    OpenAg stores calibrated prices for each crop and region in dollars per ton ($/ton). You can use the controls on
    crop modification cards to increase or decrease the price of any or all crops by up to 20 percent relative to their
    calibrated values. For example, if we have crop A that sells for $1000/ton and crop B that sells for $5000/ton and
    you use the All Crops card to adjust prices up 20%, then crop A's price will be set to $1200 and crop B's price will
    be set to $6000.
#. Yield:
    Yield values, representing tons per acre of a crop, behave similarly to price values - you may adjust them up or down by
    as much as 20% relative to each individual crop's calibrated value for the model area. The yield slider does not
    apply to the :ref:`nonirrigated lands model <NonIrrigatedDoc>` because yield is an output of that model rather than an input.
#. Crop Area Restrictions:
    Crop area restrictions (or constraints) behave differently than the previous two items. Where the previous two are
    numerical inputs to the optimization model, crop area restrictions are hard constraints that *must* be satisfied
    for the model to successfully run. Crop area restrictions allow you to place limits on how much of any crop it takes
    out of production to exchange for another crop in any region. Additionally, you may place an upper limit on the
    potential growth of a crop or even force a reduction by setting an upper limit that is below 100%. Crop area restrictions
    are useful in scenarios where a low value crop and a high value crop are grown in the same region and the model run
    reduces resource availability. In most cases, the model will be willing to take significant amounts of the low
    value crop out of production in order to keep the high value crop in production. If you know that limited amounts
    of the low value crop will go out of production, or want to test the impact of a smaller reduction in the low value
    crop to free up resources for the higher value crop, then setting a low-end limit on that crop's crop area restriction
    limits the model's ability to remove it from production. Crop area restrictions are not used in the :ref:`nonirrigated lands model <NonIrrigatedDoc>`.

.. warning::
	Crop area restrictions should be used with care. Since they create a hard constraint in the model, misconfiguration of
	these constraints can lead to infeasible model runs. For example, setting all crops to a minimum crop area restriction
	of 100% while reducing resource availability such as water or land is likely to result in an infeasible model run since
	the model will not be able to take crops out of production to satisfy model conditions.

For a table showing which parameters apply in the irrigated and the nonirrigated models, please see :ref:`ModelsAvailableDoc`.

.. seealso::

    * :ref:`See how price and yield values are used in the irrigated land model <CropPriceYieldSection>`
    * :ref:`DiagnosingInfeasibleRunsSection`

.. _AutomaticAdditionCropModificationsSection:

Automatic Addition of Crop Modification Cards
------------------------------------------------

.. figure:: automatically_added_crops.png

    Some crop cards may be automatically added, as shown here with the blue banner that says "Automatically Added"

While adjusting values for the :ref:`All Crops <AllRegionsAllCropsSection>` card, OpenAg will sometimes automatically add cards for specific crops for you.
It adds the cards because the settings on the All Crops card would make growing some crops economically infeasible - they
would lose money growing the crops in at least one region in the model. You may intend for that as an input, but in some cases you may not, so in order to
alert you to that condition and give you an explicit choice, the web application adds cards for crops before the settings
change to push the crop into losing money. You may further adjust the crop-specific settings if you wish, however.

Once created automatically, cards will not be removed automatically, even if you change the All Crops card so that the
crop-specific card is no longer needed. Instead, any time the All Crops setting would mean the crop loses money, the
crop-specific card will be unremovable in the application. Where the :code:`X` would be in the corner of the card it will
show a help tooltip explaining that the card cannot be removed. If you remove the card from the crop-selection dropdown,
it will be added back. If you adjust the All Crops card settings such that the card is no longer required, the card will
again be removable.

Automatically added crops can be identified by their blue banner at the top that says "Automatically added" and has a help
tooltip that is accessible by hovering over the icon to further explain what happened". If you make adjustments to a card
that was automatically added, the banner will disappear since you have now customized its settings, allowing you to at a
glance see which cards have been added without adjustment and which cards you have changed.

.. _RegionLinkedCropsSection:

Region-Linked Crops
----------------------

.. figure:: region_linked_crop.png

    Crop information can be specified per-region by "Region-linking" individual crop cards so that the parameters
    on the card apply only to the crop when grown in that region.

Typically, adding crop modification cards for specific crops results in changes to the values for that crop in every
region the crop is grown in. Crop cards can be limited so that the card's parameters only apply in a single region through
a process called "region linking". In the "Advanced" section of a crop card, you may choose the region the crop card
should apply to under the "Link to Region" selection item. After choosing a region, the card will include a blue
banner on the left to signify that it is a region-linked card, and the title will change to include the crop name as
well as the region name.

Once created, all parameters on the card will only apply in the specific region. If you wish to create separate settings
for other regions for the same crop, add the original crop card again and specify another region on it. If you wish
to specify separate settings for the crop in all other regions the crop is grown in after creating region-linked cards,
simply add the main crop card again. Take care that the list of cards is sorted after every card is added, so when
region-linking a card, double check that the crop card you change next is the one you intend to adjust.

For example,
if you wish to provide separate settings for All Crops, Apples statewide, and Apples in region A and region B, you would
add the Apples card, link it to region A and change the settings for that card. Then, add the Apples card again and link
it to region B, then change the settings on that card to apply to region B. Finally, add the Apples card a third time
and change the settings to apply to all regions in the model area that grow Apples *except* for regions A and B.

If you change your mind and wish to remove the region-link, simply remove the entire card. You may still add the main
crop commodity's card both before and after removal of a region-linked card.


.. index::
    single: modifications; crop area restrictions
    single: crop area restrictions

.. _AdjustingCropAreaRestrictions:

Adjusting Crop Area Restrictions
-----------------------------------
Crop area restrictions allow you to provide hard constraints (rules that must be followed by the model) on the amount
of land area a crop can be grown on in the model run, relative to its calibrated value. By default, the model's only
area constraint is that total land area in the region cannot expand, but you may add crop-specific or region and crop-specific
constraints on land area using the :code:`Crop Area Restrictions` input parameter.

.. image:: crop_area_restrictions_parameter.png

1. By default, there is no lower limit on the amount of area a crop can occupy - it can go to zero, though in the Full PMP-modeled formulation of the model, it is unlikely it will reduce acreage of any crop in a region to zero. To adjust the lower limit, modify the left side of the slider or the value in the box to its left, similar to other parameters
2. If you wish to put an upper limit, either to restrict how much a crop may grow in area in response to other changing economic factors (such as if another water-intensive crop loses water), then click the `Add Upper Limit` option on the right side of the slider
3. The slider will become double ended, with the option on the left side representing the minimum crop area and the option on the right side the maximum crop area - you can adjust each independently. When the upper limit is activated, the area in blue on the slider between the two dots represents the available range of land area for the crop.
4. To remove the upper limit after adding it, click the trash icon to the right of the upper limit. It will then revert to having no upper limit.

Uses of crop area restrictions
__________________________________
Crop area restrictions provide a safety net for the operator of the model. For example, imagine a region with a low value,
but high acreage crop such as Hay and a high value crop such as Apples. In a scenario where you lower the available water,
the model may reduce significant acreage of Hay in order to keep water available for apples. You may know that the
amount of acreage reduced of Hay is unrealistic relative to the amount of water trading seen on the ground. Crop area restrictions let you
limit the model's ability to take water from Hay to support Apples in this scenario. Setting a lower limit on Hay (e.g. 80%)
would mean that the model can only utilize 20% of the water that normally goes to Hay to support another crop. Alternatively,
setting an upper limit on the Apples crop would prevent it from growing while allowing the model to reallocate water from
lower value crops as needed. The choice to use upper or lower limits will depend on the total set of restrictions you are
adding and what you are attempting to model.

.. warning::
    Care should be exercised with crop area restrictions - in the example above with only two crops, if both crops
    had a minimum restriction of 90% set on them, but the water in the region was reduced to 80%, the model run will
    come back :ref:`"infeasible" <InfeasibilitiesSection>` - that is, the model could not find a set of values that satisfies the requirements. Infeasible
    models should not be compared to other models and instead you should create a new model run to resolve the infeasibilities.

.. seealso::
    See :ref:`AdjustModificationParametersSection` for information on adjust prices and yield parameters.

.. _AdditionalReadingCropModificationsSection:

Additional Reading on Modifications
-------------------------------------------
* :ref:`ModificationsOverviewSection`
* :ref:`ModelInputHierarchyDoc`
* :ref:`RegionModificationsDoc`