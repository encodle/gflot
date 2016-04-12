# Injection of flot javascript files #

GFlot can automatically inject required flot javascript files inside the html page. By default, jquery, flot and all the flot plugins managed by GFlot are injected.

The current javascript files loaded are :
  * [JQuery 1.7.2](http://jquery.com/) (required)
  * [Flot 0.7](http://code.google.com/p/flot/) (required)
  * [excanvas 0.3](http://code.google.com/p/explorercanvas/) : only for IE < 9, it simulates the canvas tag
  * Flot selection plugin
  * Flot symbol plugin : add symbols for points
  * Flot image plugin : allows to add images inside a chart
  * Flot resize plugin : the chart automatically resize with its placeholder
  * Flot pie plugin : allows to create pie charts
  * Flot stack plugin : allows to stack series
  * [Flot text plugin](http://lessaworld.com/projects/flotCanvasText/) : render the text with canvas. Useful to export chart as an image
  * [Flot axis labels plugin](https://github.com/markrcote/flot-axislabels) : allows to add label to the axis
  * Flot threshold plugin
  * Flot navigate plugin

You can retrieve the javascript files from flot website :
http://code.google.com/p/flot/downloads/list
or directly in the source of this project. Some of the plugins have been modified to fix bugs, you can find them here : http://code.google.com/p/gflot/source/browse/#svn%2Ftrunk%2Fflot

It is possible to customize this injection.

## Since version 2.4.0 ##
GWT properties have been added to customize the injection. You can find them all in the file [GFlot.gwt.xml](http://code.google.com/p/gflot/source/browse/trunk/gflot/src/main/resources/ca/nanometrics/gflot/GFlot.gwt.xml).

### Disable a plugin ###
To disable a plugin, you just have to mark it as disabled in your .gwt.xml file. For the pie plugin for example, add the following line :
Add the following line to your .gwt.xml file :
```
<set-property name="gflot.load.flot.pie" value="DISABLED" />
```

### Disable all the injection ###
Add the following line to your .gwt.xml file :
```
<set-property name="gflot.load" value="EXTERNAL" />
```
With this option, you will have to load yourself the javascript files.

## Prior to 2.4.0 ##
Prior to 2.4.0, there are 2 options to customize the injection.

### Custom FlotJavaScriptLoader ###
Create your own implementation of FlotJavaScriptLoader.Impl and tell GFlot to use it by adding the following lines to your .gwt.xml :
```
  <replace-with class="YourOwnFlotJavaScriptLoader">
    <when-type-is class="ca.nanometrics.gflot.client.resources.FlotJavaScriptLoader.Impl" />
  </replace-with>
```

### Disable injection ###
To disable the injection, add the following lines to your .gwt.xml :
```
  <replace-with class="ca.nanometrics.gflot.client.resources.FlotJavaScriptLoader.NoInjectionImpl">
    <when-type-is class="ca.nanometrics.gflot.client.resources.FlotJavaScriptLoader.Impl" />
  </replace-with>
```

You can then add the javascript files you want to use into the header of your html page. For example :
```
    <!-- flot library -->
    <!--[if lte IE 8]><script language="javascript" type="text/javascript" src="gflotsample/js/excanvas.min.js"></script><![endif]-->
    <script language="javascript" type="text/javascript" src="gflotsample/js/jquery.min.js"></script>
    <script language="javascript" type="text/javascript" src="gflotsample/js/jquery.flot.min.js"></script>
    <script language="javascript" type="text/javascript" src="gflotsample/js/jquery.flot.selection.min.js"></script>
```

# Flot Image plugin #

Since version 2.2.2, gflot partially supports the image plugin.

To use it, add ImageDataPoint instead of DataPoint to the model. The first parameter is the url of the image.

You also have to set the image "show" option to true on the global series options or directly on the series options.

Finally, call the method `plot.setLoadDataImages( true );` on your SimplePlot. It will load the images before creating the plot.

The flot plugin has been modified to prevent NullPointerException when the loadDataImages function is called and no image options have been set. If you use the automatic injection, it is transparent. If not, you can download the modified scripts in the download pages. The plugin is still usable without the modification but you have to define the image options on global series options and specific series options.