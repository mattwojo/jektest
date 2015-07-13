# Microsoft Edge F12 Tools for Designers

The Microsoft Edge browser F12 Tools are not just for web developers. Several F12 tool features invite designers to get in on the action -- test your designs, make changes, view responsive sizes, and update those page elements that just don't look right. A basic understanding of the F12 tools can help you to more accurately demonstrate the user experience (with transitions, states, or other interactions), better communicate your design goals with developers, repeat less work, and become a better designer for responsive web environments. 
  
![Edge DOM Explorer Computed](/jekylltests/media/Edge_WebNotes.gif) 

## Design in a responsive environment

Responsive design aims to provide optimal viewing and interaction experience--easy reading and navigation with a minimum of resizing, panning, and scrolling--across a wide range of devices (from large desktop computer monitors to tablets or mobile phone screens, and soon to include Halolens viewers!). Many of the excellent design software available simply does not provide the ability to test designs in a responsive environment. The Microsoft Edge F12 DevTools offer designers help with making wise responsive design choices through the ability to experiment with changes to page elements while adjusting viewport sizes, assigning relative size values, and exploring box-model layouts... all directly from the browser window.  

### Making changes to page elements with the DOM Explorer 

With F12 tools, all you need to do is right-click on a page element, select "Inspect element," and the tools will open revealing where that page element is coded into the DOM (Document Object Model) using HTML (left panel) and the styles associated with that element using CSS (right panel). 

#### Moving an element on the page

In the example below, we want to reorder the side navigation so that the **Dom explorer** menu item is at the top of the list. We right-click the **Dom explorer** menu item and select "Inspect element" to open this element in the F12 tools. The selected element is highlighted in blue. To move it, we click and drag it's parent list item `<li>` to the top of the unordered list `<ul>`. You can see the order of the navigation menu list items on the page automatically update to represent this change. 

![Edge DOM Explorer Computed](/jekylltests/media/Edge_DomExplorer_dragdrop.gif) 

### Relative sizes
On the web, size is no longer only measured in absolute sizes with [pixels(px), picas(pc), millimeters(mm), centimeters(cm), or inches(in)](http://www.w3.org/TR/css3-values/#absolute-lengths). While all of those measurements will work in a browser, designs will now often need to dynamically respond to the size of their environment. [**Relative sizes**](http://www.w3.org/TR/css3-values/#relative-lengths), which specify a size relative to another size, are far more common. 

F12 tools enable you to experiment with: 

  - **ems**: relative to parent `font-size`;
  - **rems**: relative to root `font-size`; 
  - **%**: percentage relative to another value (usually the parent element);
  - **vh**: 1% of the viewport height; 
  - **vw**: 1% of the viewport width; 
  - **vmin**: 1% of viewport's smaller dimension;
  - **vmax**: 1% of viewport's larger dimension;
  - **keywords**: xx-small, x-small, small, medium, large, x-large, xx-large;
  - **calc()**: allows mathematical expressions with addition (‘+’), subtraction (‘-’), multiplication (‘*’), and division (‘/’), for example: calc(100vw / 40) or (1rem - 2px).

The **DOM Explorer** tool enables you to [select an element on the page containing text](https://github.com/MicrosoftEdge/MicrosoftEdge-Documentation/tree/master/f12-devtools-guide/dom-explorer#selecting-an-element) and view it's current `font-size` in the "Computed" tab.

![Edge DOM Explorer Computed](/media/jekylltests/Edge_DomExplorer_computed.gif) 

Click the drop-down arrow next to the `font-size` to see how the `font-size` is determined, including the .css file path and line #. 

![Edge DOM Explorer Computed Changes](../media/Edge_DomExplorer_computed_changes.gif) 

Make more informed `font-size` choices by clicking on the active `font-size` path and experimenting with different relative values. The absolute `font-size` for the given environment (screen width, etc) will be shown in pixels. Try entering a relative size, like view-width(vw), and resizing your browser window width. The computed `font-size` will update to represent the new value. *(You may have to click between tabs and back to the computed tab to see this update).*   

### Track your style changes

After making style changes to the page using the F12 tools, select the **Changes** tab to see all of your changes reflected in one place. Copy-paste these changes, or take a [screenshot]() to share with your site's developer explaining the design changes that you would like to make to the page. 

![Edge DOM Explorer Track Changes](../media/Edge_DomExplorer_changes.gif)

*(Show style changes being copied and a shot of the Edge web notes tool offering additional instructions)*

![Edge DOM Explorer Track Changes Web Notes](../media/Edge_DomExplorer_changes_webnotes.gif)

### Exploring box-model layouts

Every element in web design is a rectangular box. The size of this box is calculated using width, height, padding, and border, with margin, and offset affecting other content interacting with the box. 

![Edge DOM Explorer Layout](../media/Edge_DomExplorer_layout.png)

Box-sizing has four [possible values](https://msdn.microsoft.com/en-us/library/dd183522(v=vs.85).aspx) (content-box, padding-box, border-box, and inherit). Microsoft Edge defaults to border-box (width or height + padding + border = actual width or height). 

The F12 tools "Layout" feature allows you to see the current values of the[ box-model properties](https://msdn.microsoft.com/en-us/library/hh772047(v=vs.85).aspx) and change them to see how the page is affected in real-time.   

![Edge DOM Explorer Layout](../media/Edge_DomExplorer_layout_changes.gif)

*In Microsoft Edge, if padding or border size is undeclared, the default value is zero. 
