# Version 3.2.1 #
  * Upgraded to flot 0.8.2
  * Fixed [Issue #16 PlotWithOverviewModel ignores width setting](https://github.com/nmorel/gflot/issues/16)

# Version 3.2.0 #
  * Fixed the redraw method that was not working correctly ([issue 10](https://github.com/nmorel/gflot/issues/10) and [issue 12](https://github.com/nmorel/gflot/issues/12)). Be careful, for this to work, the PlotOptions returned by getPlotOptions now always return the instance you give to the constructor of SimplePlot. It is no longer overriden by the internal plot options used by flot. If you still want to read internal options, use SimplePlot.getPlot().getOptions().
  * Removed the ability to set PieOptions to specific series ([issue 11](https://github.com/nmorel/gflot/issues/11))

# Version 3.1.2 #
  * Fixed an issue on TickGenerator [issue 9](https://github.com/nmorel/gflot/issues/9)
  * [Added support for font options on axis label](https://github.com/nmorel/gflot/commit/3c7be55624146461e739682e804692ee0ec56d15)

# Version 3.1.1 #
  * Upgraded to flot 0.8.1

# Version 3.1.0 #
  * Upgraded to flot 0.8
  * Upgraded to JQuery 1.8.3
  * Upgraded to GWT 2.2.0
  * Dropped support of MultipleBar plugin in favour of [Side-by-side bars plugin](https://github.com/pkoltermann/SideBySideImproved)
  * Added the new options available in flot 0.8
  * Added Categories plugin support
  * Added Error Bars plugin support

# Version 3.0.3 #
  * Added missing methods on Plot ([issue 6](https://github.com/nmorel/gflot/issues/6))
  * Fixed bug on slice method used by PlotWithOverview ([issue 5](https://github.com/nmorel/gflot/issues/5))

# Version 3.0.2 #
  * Support for fillArea plugin ([issue 59](https://code.google.com/p/gflot/issues/detail?id=59)).
  * New redraw method allowing to recreate the plot instead of just redrawing
  * Added some special characters to the canvas-text plugin ([issue 60](https://code.google.com/p/gflot/issues/detail?id=60))
  * Fixed a bug on PlotWithInteractiveLegend [issue 4](https://github.com/nmorel/gflot/issues/4)

# Version 3.0.1 #
  * Fixed a regression on PlotWithInteractiveLegend ([commit](https://github.com/nmorel/gflot/commit/16f183ada35b25c5ebe9c971e9b03b085ba3a8cb))

# Version 3.0.0 #
  * Changed core api to use [Javascript Overlay Types](https://developers.google.com/web-toolkit/doc/latest/DevGuideCodingBasicsOverlay)
  * Moved codebase to Github
  * Changed package from ca.nanometrics to com.googlecode.gflot

# Version 2.4.3 #
  * Added methods to clear options ([issue 54](https://code.google.com/p/gflot/issues/detail?id=54)) ([r195](https://code.google.com/p/gflot/source/detail?r=195))
  * Added methods to remove series in PlotModel ([issue 20](https://code.google.com/p/gflot/issues/detail?id=20)) ([r194](https://code.google.com/p/gflot/source/detail?r=194))
  * Support for fillBetween plugin. Thanks to Ana Rita Loureiro for the patch (again!) ([r190](https://code.google.com/p/gflot/source/detail?r=190))

# Version 2.4.2 #
  * Support for crosshair plugin ([r175](https://code.google.com/p/gflot/source/detail?r=175) [r176](https://code.google.com/p/gflot/source/detail?r=176))
  * Support for multiple bars plugin ([r183](https://code.google.com/p/gflot/source/detail?r=183) [r184](https://code.google.com/p/gflot/source/detail?r=184)) ([issue 48](https://code.google.com/p/gflot/issues/detail?id=48))
  * fixed bug in PlotWithOverview ([r178](https://code.google.com/p/gflot/source/detail?r=178)). Thanks to camerojo for the patch.

# Version 2.4.1 #
  * Support for axis label plugin : https://github.com/markrcote/flot-axislabels ([r154](https://code.google.com/p/gflot/source/detail?r=154))
  * Support for threshold plugin ([r158](https://code.google.com/p/gflot/source/detail?r=158))
  * Support for navigate plugin ([r166](https://code.google.com/p/gflot/source/detail?r=166) [r169](https://code.google.com/p/gflot/source/detail?r=169) [r170](https://code.google.com/p/gflot/source/detail?r=170)) ([issue 22](https://code.google.com/p/gflot/issues/detail?id=22)). Thanks to Ana Rita Loureiro for the patch
  * jQuery version from 1.7.1 to 1.7.2
  * [issue 47](https://code.google.com/p/gflot/issues/detail?id=47) : conflicts between jQuery and other javascript libraries

# Version 2.4.0 #
  * released on Maven Central!
    * use the groupId : com.googlecode.gflot
    * the old releases will remain in the gflot repository
  * rewrote the samples
  * jquery version from 1.5.1 to 1.7.1 ([issue 40](https://code.google.com/p/gflot/issues/detail?id=40) ?)
  * fixed bug on Pie charts (redraw wasn't working) [issue 41](https://code.google.com/p/gflot/issues/detail?id=41)
  * fixed bugs on PlotWithOverview [issue 42](https://code.google.com/p/gflot/issues/detail?id=42) and [issue 43](https://code.google.com/p/gflot/issues/detail?id=43)
  * new mechanism to load plugins. It is now possible to choose which flot plugin to load. ([r136](https://code.google.com/p/gflot/source/detail?r=136))
  * added resize plugin ([r136](https://code.google.com/p/gflot/source/detail?r=136))
  * added canvas text plugin + canvas2image. It is now possible to export a chart to an image ([example](http://gflot2.appspot.com/#export))

# Version 2.3.2 #
  * support for stack plugin

# Version 2.3.1 #
  * support for pie plugin

# Version 2.3.0 #
  * support for multiple axes
  * /!\ Breaking changes /!\ Lots of change around the selection API have been made for the multiple axes support. GFlot was using deprecated method since flot 0.5. All the methods from selection API are now supported (unselected and selecting event, clear selection...)
  * fix : couldn't define specific series options

# Version 2.2.3 #
  * modifying axis options without recreating plot wasn't working

# Version 2.2.2 #
  * fix two bugs on PlotWithOverview :
    * the method clear() on PlotWithOverviewSeriesHandler was not resetting all the attributes
    * redraw was called for each series
  * add support for flot image plugin

# Version 2.2.1 #
  * Just forgot to add getter for options on PlotWithOverview

# Version 2.2 #

  * fixed the method setContainer on LegendOptions
  * you can now pass the Element used as container in SimplePlot and PlotWithOverview constructors.
  * added getter methods for options and on plot. It allows to modify the options after the plot has been loaded and without recreating it (just call redraw())
  * added new methods to set linewidth and colors on markings
  * /!\ Breaking change : PlotOptions.setDefaultPointsOptions, Lines and Bars have been removed. Now use the setGlobalSeriesOptions.

# Version 2.1 #

2.1 is adding most of the flot options that wasn't wrap into gflot. There is also javadocs added to the different options and some assert to insure the user don't set wrong an option.

  * added automatic injection of flot javascript files. See [Usage](Usage.md) for more informations.
  * added some javadocs to the differents options
  * updated the PlotWithInteractiveLegendExample to use TimeSeriesAxisOptions
  * Series
    * added methods setColor(int), setClickable(boolean) and setHoverable(boolean)
    * it is now possible to retrieve Series from SeriesHandler and pass a Series object to PlotModel.addSeries()
  * SeriesOptions => AbstractSeriesOptions
    * added methods to set the option fill with opacity and fillColor with a gradient
  * BarSeriesOptions : added setHorizontal(boolean)
  * LineSeriesOptions : added setSteps(boolean)
  * GridOptions
    * can now set background color with a gradient
    * added setMinBorderMargin(int), setBorderColor(String), setAboveData(boolean)
  * PointsSeriesOptions : added new symbol with the symbol plugin
  * AxisOptions
    * added methods for the following flot options : "color", "position", "tickColor", "show", "reserveSpace", "tickLength" and "alignTicksWithAxis"
    * added methods on TimeSeriesAxisOptions for the flot options : "twelveHourClock", "tickSize" and "minTickSize"
    * added support for "transform" and "inverseTransform" options
    * added support for tick generator
  * LegendOptions : changed setPosition to use an enum


# Version 2.0 #

  * gwt 2.4.0
  * flot 0.7
  * samples updated and hosted on appengine