<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128626635/16.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E900)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->

# Data Grid for Windows Forms - How to create a GridView descendant and register it for design-time use

In v16.1 and higher, you can use the [Template Gallery](https://docs.devexpress.com/WindowsForms/16492/whats-installed/template-gallery) to create a [GridView](https://docs.devexpress.com/WindowsForms/DevExpress.XtraGrid.Views.Grid.GridView) descendant with all required infrastructure classes. Use the `Custom Data Grid` template for this purpose.

The current example shows how to create a `GridView` descendant without using this template. This descendant allows users to delete records when they press the `Delete` key. Build the project prior to opening the `Form1` form in the Visual Studio designer. 

## View Descendant Concepts
This section describes basic concepts to create a descendant of the `GridView`, demonstrated in the attached project.

You typically need to create descendants of the following classes to implement custom functionality for a `GridView`:

- `GridView` - The component that exposes customization settings and references all infrastructure classes.
- `GridControl` - The control that you place on the form. This is a container for your View descendant.
- `GridInfoRegistrator` - Contains the View's registration information.
- `GridHandler` - Processes mouse and keyboard actions.
- `GridViewInfo` - Calculates display information used to draw the View's elements.
- `GridViewPrintInfo` - Calculates the information necessary to print the View.

Override the `ViewName` property for the `GridView` descendant. This property should return a unique View name.

Do the following to register the `GridView` descendant for design-time use:

- Create a `GridInfoRegistrator` class descendant. This class's `ViewName` property must return the same value as your View's `ViewName` property.
- Override the `RegisterAvailableViewsCore` method in your `GridControl` descendant.
- If you want the custom `GridControl` to create an instance of the `GridView` descendant on the control's initialization, override the `GridControl.CreateDefaultView` method.
- To display the custom `GridControl` in the Visual Studio Toolbox, mark the control with the `[ToolboxItem(true)]` attribute and rebuild the solution.


<!-- default file list -->
## Files to Look At

* [Customer.cs](./CS/MyXtraGrid/Customer.cs) (VB: [Customer.vb](./VB/MyXtraGrid/Customer.vb))
* [Form1.cs](./CS/MyXtraGrid/Form1.cs) (VB: [Form1.vb](./VB/MyXtraGrid/Form1.vb))
* [MyGridControl.cs](./CS/MyXtraGrid/MyGridControl.cs) (VB: [MyGridControl.vb](./VB/MyXtraGrid/MyGridControl.vb))
* [MyGridHandler.cs](./CS/MyXtraGrid/MyGridHandler.cs) (VB: [MyGridHandler.vb](./VB/MyXtraGrid/MyGridHandler.vb))
* [MyGridRegistration.cs](./CS/MyXtraGrid/MyGridRegistration.cs) (VB: [MyGridRegistration.vb](./VB/MyXtraGrid/MyGridRegistration.vb))
* [MyGridView.cs](./CS/MyXtraGrid/MyGridView.cs) (VB: [MyGridViewInfo.vb](./VB/MyXtraGrid/MyGridViewInfo.vb))
* [MyGridViewInfo.cs](./CS/MyXtraGrid/MyGridViewInfo.cs) (VB: [MyGridViewInfo.vb](./VB/MyXtraGrid/MyGridViewInfo.vb))
* [Program.cs](./CS/MyXtraGrid/Program.cs) (VB: [Program.vb](./VB/MyXtraGrid/Program.vb))
<!-- default file list end -->

## See Also
- [Create GridView descendants](https://www.devexpress.com/Support/Center/p/A859)
- [DevExpress WinForms Troubleshooting - Grid Control](https://go.devexpress.com/CheatSheets_WinForms_Examples_T934742.aspx)
- [How to create a WinExplorerView descendant class and register it for design-time use](https://www.devexpress.com/Support/Center/p/T122347)
- [How to create a LayoutView descendant class and register it for design-time use](https://www.devexpress.com/Support/Center/p/T122335)
- [How to create a CardView descendant class and register it for design-time use](https://www.devexpress.com/Support/Center/p/T122333)
- [How to create an AdvBandedGridView descendant class and register it for design-time use](https://www.devexpress.com/Support/Center/p/T122322)
- [How to create a BandedGridView descendant class and register it for design-time use](https://www.devexpress.com/Support/Center/p/T122275)
- [How to create a TileView descendant class and register it for design-time use](https://www.devexpress.com/Support/Center/p/T233168)


