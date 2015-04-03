---
title: Events
page_title: Events | UI for ASP.NET AJAX Documentation
description: Events
slug: diagram/client-side-programming/events
tags: events
published: True
position: 1
---

# Events



## 

__RadDiagram__ provides a rich set of Client-Side events which allow easy and flexible use in a wide range of application scenarios.	Many of the events are cancelable giving you the possibility to cancel any operation performed on the image:

* __OnLoad__—raised when the control is initialized. You can use it to store object references.You can get the underlying Kendo widget from the RadDiagram object via the get_kendoWidget() method.

* [OnAdd](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-add)—raised when the user adds a new shape or a new connection.

* [OnChange](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-change)—raised when an item is added or removed to/from the diagram.

* [OnClick](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-click)—raised when the user clicks on a shape or a connection.

* [OnDataBound](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-dataBound)—raised when the widget is bound to data from a dataDource and a connectionsDataSource.

* [OnItemBoundsChange](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-itemBoundsChange)—raised when the location or size of an item are changed.

* [OnItemRotate](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-itemRotate)—raised when an item is rotated.

* [OnMouseEnter](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-mouseEnter)—raised when the mouse enters a shape or a connection. Will not fire for disabled items.

* [OnMouseLeave](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-mouseLeave)—raised when the mouse leaves a shape or a connection. Will not fire for disabled items.

* [OnPan](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-pan)—raised when the user pans the diagram.

* [OnRemove](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-remove)—raised when the user deletes a shape or a connection.

* [OnSelect](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-select)—raised when the user selects one or more items.

* [OnZoomStart](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-zoomStart)—raised when the user starts changing the diagram zoom level.

* [OnZoomEnd](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events-zoomEnd)—raised when the user changes the diagram zoom level.

To use these events, simply write a JavaScript function that can be called when the event occurs. Then assign the name of this function as the value of the the	corresponding property in the __ClientEvents__ RadDiagram subtag.

````ASPNET
	      	<telerik:RadDiagram ID="RadDiagram1" runat="server">
				<ClientEvents OnLoad="OnLoad" />
				<ShapesCollection>
					<telerik:DiagramShape Id="s1"></telerik:DiagramShape>
				</ShapesCollection>
			</telerik:RadDiagram>
			<script type="text/javascript">
				function OnLoad(diagram) {
					alert("OnLoad event fired by RadDiagram with ID: " + diagram.get_id());
				}
			</script>
````



All Client-Side events, except __OnLoad__, are references to their corresponding events of the Kendo UI diagram object. You can get familiar will the full setof arguments coming with each event in the[Kendo UI diagram API reference](http://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/diagram#events). For example:

````ASPNET
			<telerik:RadDiagram ID="RadDiagram2" runat="server">
				<ClientEvents OnClick="OnClick" />
				<ShapesCollection>
					<telerik:DiagramShape Id="DiagramShape1"></telerik:DiagramShape>
				</ShapesCollection>
			</telerik:RadDiagram>
			<script type="text/javascript">
				function OnClick(args) {
					var kendoWidget = args.sender;
					var itemId = args.item.id;
					var point = args.point;
					alert("You have just clicked on an item with ID: " + itemId + " at position: {x=" + point.x + ", y=" + point.y + "}");
				}
			</script>
````



# See Also

 * [Client-Side API]({%slug diagram/client-side-programming/overview%})