# Change Log
All notable changes to this project will be documented in this file.

## [Unreleased]

### Changed
- Made legends open for extension (#644)
- Added Oxyplot.Legends namespace
- Added abstract base class LegendBase
- Added default implementation Legend and Legend.Rendering
- Added Legends ElementCollection to PlotModel
- PlotModel now accommodate multiple Legends, although same positions as before. Legends sharing position are placed on top of eachother
- Made Legend Items clickable to toggle series visibility
- Added properties LegendKey and SeriesGroupName to Series, allowing grouping series between multiple legends and/or within same legend
- Remove PlotModel.Legends
- Default behaviour is now plot without Legend.

### Added
- OxyPlot.ImageSharp (#1188)
- WPF ExampleBrowser can display transposed versions of examples (#1402)

### Changed
- Moved reporting functionality to separate projects (#1403)
- Moved reporting functionality to oxyplot-reporting repository (#1403)
- Moved WPF Plot component to Oxyplot.Contrib.Wpf (#1399)
- ErrorColumnSeries changed to ErrorBarSeries, also works in transposed mode (#1402)

### Removed
- Copy to text report Ctrl+Alt+R (#1403)
- ColumnSeries - functionality is replaced by transposed BarSeries (#1402)

### Fixed
- Legend font size is not affected by DefaultFontSize (#1396)
- Exception when rendering polygon with no points (#1410)
- ErrorBarSeries, IntervalBarSeries and TornadoBarSeries work correctly in transposed mode (#1402)

## [2.0.0] - 2019-10-19
### Added 
- WindowsForms and Wpf support .NET Core 3.0 (#1331)
- PngExporter based on System.Common.Drawing (.NET Core) (#1263)
- New polar plot axes filling the full plot area (#1056)
- Support for three colors in histogram series (#1305)
- Command to copy plot to the clipboard in Windows Forms (Ctrl-C) (#1297)
- New `InterpolationAlgorithm` property in LineSeries and PolylineAnnotation (#494)
- Catmull-Rom spline interpolation algorithms (#494)
- FontSize, FontWeight and FontFamily on Wpf.TextAnnotation (#1023)
- RectangleSeries (#1060)
- InvalidNumberColor on Wpf.LinearColorAxis (#1087)
- ContinuousHistogramSeries (#1145)
- Multiline text support for PortableDocumentFont (#1146)
- Workaround for text vertical alignment in SVG Export to accomodate viewers which don't support dominant-baseline (#459, #1198)
- Support for transposed (X and Y axis switched) plots with XYAxisSeries (#1334)
- Color property on HistogramItem (#1347)
- Count property on HistogramSeries (#1347)

### Changed
- OxyPlot.Core changed to target netstandard 1.0 and net45 (#946, #1147)
- OxyPlot.ExampleLibrary changed to target netstandard 1.0 and net45 (#946, #1147)
- OxyPlot.Wpf, OxyPlot.WindowsForms, OxyPlot.Pdf changed to target net45 (#946)
- Place label below negative ColumnSeries (#1119)
- Use PackageReference instead of packages.config
- Migrated NUnit v2 to v3 and added test adapter
- TrackerControl reuses existing ContentControl when a new hit tracker result uses the same template as the currently shown tracker (#1281)
- Overhaul HistogramHelpers (#1345)
- OxyPlot.Windows (UWP) moved to oxyplot-uwp repository (#1378)
- Make the PngExporters consistent (#1390)
- Silverlight project moved to separate repository (#1049)
- WP8 project moved to separate repository (#1050)
- Windows8 project moved to separate repository (#1103)
- Avalonia project moved to separate repository
- Xamarin projects moved to separate repository
- Xwt project moved to separate repository
- GTK# projects moved to separate repository
- SharpDX project moved to separate repository

### Deprecated
- OxyPlot.WP8 package. Use OxyPlot.Windows (UWP) instead (#996)

### Removed
- LabelFontSize property from HistogramSeries (#1309)
- Smooth property from LineSeries and PolylineAnnotation (#494)
- Support for net40 (#960)

### Fixed
- Manipulation when using touch is not working in Windows (#1011)
- Ensure a suitable folder is used when creating a temporary file for PNG export in Oxyplot.GtkSharp (#1034)
- RangeColorAxis is not rendered correctly if the axis is reversed (#1035)
- OxyMouseEvents not caught due to InvalidatePlot() in WPF (#382)
- When Color Property of LineSeries is set Markers are not shown (#937)
- Change from linear to logarithmic axis does not work (#1067)
- OxyPalette.Interpolate() throws exception when paletteSize = 1 (#1068)
- Infinite loop in LineAnnotation (#1029)
- OverflowException when zoomed in on logarithmic axis (#1090)
- ScatterSeries with DateTimeAxis/TimeSpanAxis (#1132)
- Exporting TextAnnotation with TextColor having 255 alpha to SVG produces opaque text (#1160)
- Chart is not updated when top and bottom are not visible (#1219)
- Candle overlap each candle (#623)
- CandleStick is overlapped when item.Open == item.Close in the CandleStickAndVolumeSeries (#1245)
- Out of memory exception and performance issue with Catmull-Rom Spline (#1237)
- Cache and Dispose Brush and Pen objects used by GraphicsRenderContext (#1230)
- Add checks for non-positive StrokeThickess and LineStyle.None in various places (#1312)
- Fixed references to RectangleItem in HistogramSeries
- Fix AxisChangedEventArgs.DeltaMaximum in Axes.Reset (#1306)
- Fixed Tracker for RectangleBarSeries (#1171)
- RectangleSeries doesn't render Labels (related to #1334)
- LineSeries line legend placement with reversed X axis (related to #1334)
- HistogramSeries label placement inconsistent (related to #1334)
- TwoColorLineSeries and ThreeColorLineSeries don't work with reversed Y axis (related to #1334)
- Issue with SVG always containing the xml headers (#1212)
- In WPF, make sure the axes are initalized when the Model is set before the PlotView has been loaded (#1303)
- MinimumSegmentLength not working for LineSeries (#1044)
- rendering issues with MagnitudeAxisFullPlotArea (#1364)
- OxyPlot.Core.Drawing PngExporter background when exporting to stream (#1382)
- Windows Forms clipping last line of rendered text (#1124, #1385)
- Dispose background brush in OxyPlot.Core.Drawing PngExporter (#1392)

## [1.0.0] - 2016-09-11
### Added
- Added OxyPlot.SharpDX.Wpf NuGet package
- Added DirectX 9.1-10.1 feature level support for SharpDX renderer
- Added SharpDX based renderer and WPF control with SharpDX render (#124)
- Added MinimumMajorStep and MinimumMinorStep to Axes.Axis (#816)
- Added support for vertical X axis to HeatMapSeries (#535)
- Added fall-back rectangle rendering to HeatMapSeries (#801)
- Added logarithmic HeatMapSeries support (#802) and example
- Axis.MaximumRange to limit the zoom (#401)
- Added OxyPlot.Mobile NuGet package to combine the mobile platforms into a single package (#362)
- Support for XWT (#295)
- TwoColorAreaSeries (#299)
- Delta values in AxisChangedEventArgs (#276)
- Git source server (added GitLink build step) (#267,#266)
- iOS PlotView ZoomThreshold/AllowPinchPastZero for use with KeepAspectRatioWhenPinching=false (#359)
- CandleStickAndVolumeSeries and VolumeSeries (#377)
- Axis.DesiredSize property (#383)
- WPF wrapper for BoxPlotSeries (#434)
- Capability to display mean value to BoxPlotSeries (#440)
- LinearBarSeries for WPF (#506)
- TitleToolTip in PlotModel (#508)
- TextColor property on WPF Axis (#452)
- ThreeColorLineSeries (#378)
- CI of the Xamarin.Android, Xamarin.iOS and Xamarin.Forms packages (#274)
- PlotModel.LegendLineSpacing (#622)
- Legend rendering for LinearBarSeries (#663)
- LegendMaxHeight property in PlotModel and Wpf.Plot (#668)
- Support for a Xamarin Forms UWP project with sample app (#697)
- ListBuilder for building lists by reflection (#705)
- F# example (#699)
- Support for discontinuities in AreaSeries (#215)
- Support for Windows Universal 10.0 apps (#615)
- Support Unicode in OxyPlot.Pdf (#789)
- TouchTrackerManipulator (#787)
- Extracted visible window search code from CandleStickSeries and made a generic version in XYSeries. Used it to optimize AreaSeries performance. (#834)
- Optimized rendering performance of RectangleBarSeries (#834).
- PdfExporter implementing IExporter (#845)
- Color minor and major ticks differently (#417)
- Support for PieSeries in OxyPlot.Wpf (#878)
- Filter in example browser (#118)
- Support for tooltips on WPF annotations
- Support for tracker in OxyPlot.GtkSharp
- Improve tracker style (Windows Forms) (#106)
- Font rendering in OxyPlot.GtkSharp improved by using Pango (#972)
- Improved LineSeries performance (#834)
- Fixed bug causing axes titles to not display in OxyPlot.GtkSharp (#989)

### Changed
- Fixed closing file stream for PdfReportWriter when PdfReportWriter is closed or disposed of. (#892)
- Renamed OxyPlot.WindowsUniversal to OxyPlot.Windows (#242)
- Changed OxyPlot.Xamarin.Forms to require OxyPlot.Mobile dependency instead of each separate NuGet. (#362)
- Renamed OxyPlot.XamarinIOS to OxyPlot.MonoTouch (#327)
- Renamed OxyPlot.XamarinAndroid to OxyPlot.Xamarin.Android (#327)
- Renamed OxyPlot.XamarinForms to OxyPlot.Xamarin.Forms (#327)
- Renamed OxyPlot.XamarinForms.iOS to OxyPlot.Xamarin.Forms.Platform.iOS (#327)
- Renamed OxyPlot.XamarinFormsIOS to OxyPlot.Xamarin.Forms.Platform.iOS.Classic (#327)
- Renamed OxyPlot.XamarinFormsAndroid to OxyPlot.Xamarin.Forms.Platform.Android (#327)
- Renamed OxyPlot.XamarinFormsWinPhone to OxyPlot.Xamarin.Forms.Platform.WP8 (#327)
- Changed OxyPlot.Xamarin.Android target to Android level 10 (#223)
- Separated WPF Plot and PlotView (#252, #239)
- Current CandleStickSeries renamed to OldCandleStickSeries, replaced by a faster implementation (#369)
- Invalidate plot when ItemsSource contents change (INotifyCollectionChanged) on WPF only (#406)
- Xamarin.Forms references updated to 1.5.0.6447 (#293, #439)
- Change OxyPlot.Xamarin.Forms.Platform.Android target to Android level 15 (#439)
- Changed OxyPlot.Xamarin.Forms to portable Profile259 (#439)
- PlotController should not intercept input per default (#446)
- Changed DefaultTrackerFormatString for BoxPlotSeries (to include Mean) (#440)
- Changed Constructor of BoxPlotItem (to include Mean) (#440)
- Changed Axis, Annotation and Series Render() method (removed model parameter)
- Changed PCL project to profile 259, SL5 is separate now (#115)
- Extracted CreateReport() and CreateTextReport() from PlotModel (#517)
- Renamed GetLastUpdateException to GetLastPlotException and added the ability to see render exceptions(#543)
- Move TileMapAnnotation class to example library (#567)
- Change to semantic versioning (#595)
- Change GTKSharp3 project to x86 (#599)
- Change OxyPlot.Xamarin.Android to API Level 15 (#614)
- Add Xamarin.Forms renderer initialization to PlotViewRenderer (#632)
- Marked OxyPlot.Xamarin.Forms.Platform.*.Forms.Init() obsolete (#632)
- Throw exception if Xamarin.Forms renderer is not 'initialized' (#492)
- Make numeric values of DateTimeAxis compatible with ToOADate (#660)
- Make struct types immutable (#692)
- Implement IEquatable<T> for struct types (#692)
- BoxPlotItem changed to reference type (#692)
- Move Xamarin projects to new repository (#777)
- Remove CandleStickSeries.Append (#826)
- Change MinorInterval calculation, add unit test (#133)
- Rewrite LogarithmicAxis tick calculation (#820)
- Change Axis methods to protected virtual (#837)
- Move CalculateMinorInterval and CreateTickValues to AxisUtilities (#837)
- Change default number format to "g6" in Axis base class (#841)
- Push packages to myget.org (#847)
- Change the default format string to `null` for TimeSpanAxis and DateTimeAxis (#951)

### Removed
- StyleCop tasks (#556)
- OxyPlot.Metro project (superseded by OxyPlot.WindowsUniversal) (#241)
- PlotModel.ToSvg method. Use the SvgExporter instead. (#347)
- Constructors with parameters, use default constructors instead. (#347)
- Axis.ShowMinorTicks property, use MinorTickSize = 0 instead (#347)
- ManipulatorBase.GetCursorType method (#447)
- Model.GetElements() method
- Remove SL4 support (#115)
- Remove NET35 support (#115)
- PlotElement.Format method, use StringHelper.Format instead
- EnumerableExtensions.Reverse removed (#677)
- ListFiller (#705)

### Fixed
- Added check to LineAnnotation.GetScreenPoints to check if ActualMaximumX==ActualMinimumX for non-curved lines. (#1029)
- Incorrect placment of axis title of axes with AxisDistance (#1065)
- SharpDX control not being rendered when loaded
- SharpDX out of viewport scrolling.
- Multiple mouse clicks not being reported in OxyPlot.GtkSharp (#854)
- StemSeries Tracking to allow tracking on tiny stems (#809)
- Fixed PDFRenderContext text alignment issues for rotated text (#723)
- HeatMapSeries.GetValue returns NaN instead of calculating a wrong value in proximity to NaN (#256)
- Tracker position is wrong when PlotView is offset from origin (#455)
- CategoryAxis should use StringFormat (#415)
- Fixed the dependency of OxyPlot.Xamarin.Forms NuGet (#370)
- Add default ctor for Xamarin.Forms iOS renderer (#348)
- Windows Phone cursor exception (#345)
- Bar/ColumSeries tracker format string bug (#333)
- Fix exception for default tracker format strings (#265)
- Fix center-aligned legends (#79)
- Fix Markdown links to tag comparison URL with footnote-style links
- WPF dispatcher issue (#311, #309)
- Custom colors for scatters (#307)
- Rotated axis labels (#303,#301)
- Floating point error on axis labels (#289, #227)
- Performance of CandleStickSeries (#290)
- Tracker text for StairStepSeries (#263)
- XamarinForms/iOS view not updating when model is changed (#262)
- Improved WPF rendering performance (#260, #259)
- Null reference with MVVM binding (#255)
- WPF PngExporter background (#234)
- XamlExporter background (#233)
- .NET 3.5 build (#229)
- Support WinPhone 8.1 in core NuGet package (#161)
- Draw legend line with custom pattern (#356)
- iOS pan/zoom stability (#336)
- Xamarin.Forms iOS PlotViewRenderer crash (#458)
- Inaccurate tracker when using LogarithmicAxis (#443)
- Fix reset of transforms in WinForms render context (#489)
- Fix StringFormat for TimeSpanAxis not recognizing f, ff, fff, etc (#330)
- Fix  LineSeries SMOOTH=True will crash WinForms on right click (#499)
- Fix PlotView leak on iOS (#503)
- This PlotModel is already in use by some other PlotView control (#497)
- LegendTextColor not synchronized between wpf.Plot and InternalModel (#548)
- Legend in CandleStickSeries does not scale correctly (#554)
- Fix CodeGenerator exception for types without parameterless ctor (#573)
- Migrate automatic package restore (#557)
- Fix rendering of rotated 'math' text (#569, #448)
- WPF export demo (#568)
- Fixing a double comparison issue causing infinite loop (#587)
- Fix null reference exception when ActualPoints was null rendering a StairStepSeries (#582)
- Background color in the Xamarin.Forms views (#546)
- IsVisible change in Xamarin.Forms.Platform.iOS (#546)
- Rendering math text with syntax error gets stuck in an endless loop (#624)
- Fix issue with MinimumRange not taking Minimum and Maximum values into account (#550)
- Do not set default Controller in PlotView ctor (#436)
- Corrected owner type of Wpf.PathAnnotation dependency properties (#645)
- Fixed partial plot rendering on Xamarin.Android (#649)
- Default controller should not be shared in WPF PlotViews (#682)
- PositionAtZeroCrossing adds zero crossing line at wrong position (#635)
- Implement AreaSeries.ConstantY2 (#662)
- Null reference exception in ScatterSeries{T} actual points (#636)
- Code generation for HighLowItem (#634)
- Axis.MinimumRange did not work correctly (#711)
- FillColor in ErrorColumnSeries (#736)
- XAxisKey and YAxisKey added to Wpf.Annotations (#743)
- Fix HeatMapSeries cannot plot on Universal Windows (#745)
- Set Resolution in WinForms PngExporter (#754)
- Axis should never go into infinite loop (#758)
- Exception in BarSeriesBase (#790)
- Vertical Axes Title Font Bug (#474)
- Support string[] as ItemsSource in CategoryAxis (#825)
- Horizontal RangeColorAxis (#767)
- LogarithmicAxis sometimes places major ticks outside of the axis range (#850)
- LineSeries with smoothing raises exception (#72)
- Exception when legend is outside and plot area is small (#880)
- Axis alignment with MinimumRange (#794)
- Fixed strange number formatting when using LogarithmicAxis with very large or very small Series (#589)
- Fixed LogarithmicAxis to no longer freeze when the axis is reversed (#925)
- Prevent endless loop in LogarithmicAxis (#957)
- Fixed WPF series data not refreshed when not visible (included WPF LiveDemo)
- Fixed bug in selection of plot to display in OxyPlot.GtkSharp ExampleBrowser (#979)
- Fixed non-interpolation of HeatMapSeries in OxyPlot.GtkSharp (#980)
- Fixed axis min/max calc and axis assignment for CandleStick + VolumeSeries (#389)
- Fixed drawing of plot backgrounds in OxyPlot.GtkSharp (#990)

## [0.2014.1.546] - 2014-10-22
### Added
- Support data binding paths ("Point.X") (#210)
- Support for Xamarin.Forms (#204)
- Support for Windows Universal apps (#190)
- Improve TrackerFormatString consistency (#214)
- Support LineColor.BrokenLineColor
- LabelFormatString for ScatterSeries (#12)

### Changed
- Changed tracker format strings arguments (#214)
- Rename OxyPenLineJoin to LineJoin
- Rename LineStyle.Undefined to LineStyle.Automatic

### Fixed
- Improved text rendering for Android and iOS (#209)
- Custom shape outline for PointAnnotation (#174)
- Synchronize Wpf.Axis.MinimumRange (#205)
- TrackerHitResult bug (#198)
- Position of axis when PositionAtZeroCrossing = true (#189)
- Expose ScatterSeries.ActualPoints (#201)
- Add overridable Axis.FormatValueOverride (#181)
- PngExporter text formatting (#170)

[Unreleased]: https://github.com/oxyplot/oxyplot/compare/v2.0.0...HEAD
[2.0.0]: https://github.com/oxyplot/oxyplot/compare/v1.0.0...v2.0.0
[1.0.0]: https://github.com/oxyplot/oxyplot/compare/v0.2014.1.546...v1.0.0
[0.2014.1.546]: https://github.com/oxyplot/oxyplot/compare/v0.0.1...v0.2014.1.546
