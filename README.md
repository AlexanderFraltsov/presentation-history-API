# presentation-history-API

`(Slide HTML5 History API)`  
Hello, I'm **Alexander Fraltsov** and it's my presentation HTML5 History API.  
`(Slide What is it?)`  
What is it?  
`(Slide The HTML5 history API...?)`  
The HTML5 history API is a standardized way to manipulate the browser history via script. If you type in your console **window.history**, you'll saw following object.  
`(Slide Part of this API...)`  
Part of this API — navigating the history — has been available in previous versions of HTML.  
The new parts in HTML5 include a way to add entries to the browser history, to visibly change the URL in the browser location bar (without triggering a page refresh), and an event that fires when those entries are removed from the stack by the user pressing the browser’s back button.  
`(Slide This means that...)`  
This means that the URL in the browser location bar can continue to do its job as a unique identifier for the current resource, even in script-heavy applications that don’t ever perform a full page refresh.  
`(Slide Moving)`  
History API. Moving.  
`(Slide Backward)`  
To move backward through history you can use following method: **window.history.back()**.  
This acts exactly as if the user clicked on the Back button in the browser toolbar.  
`(Slide Forward)`  
Similarly, you can move forward (as if the user clicked the Forward button), like this: **window.history.forward()**.  
`(Slide Go)`  
Moving to a specific point in history.  
You can use the **go()** method to load a specific page from session history, identified by its relative position to the current page (the current page's relative position is 0).  
`(Slide Go minus one plus one)`  
For example, to move back one page (the equivalent of calling **back()**): **window.history.go(-1)**.  
To move forward a page, just like calling forward() method you can use: **window.history.go(1)**.  
`(Slide Reload)`  
And, finally either of the following statements will reload the current page: **window.history.go** from zero and **window.history.go** from empty.  
`(Slide Properties)`  
History API. Properties.  
`(Slide Length)`  
You can determine the number of pages in the history stack by looking at the value of the **length** property.  
`(Slide State)`  
And **window.history.state**.  
Returns an any value representing the state at the top of the history stack. This is a way to look at the state without having to wait for a **popstate** event.  
The value of the **state** property is **null** until you call **pushState()** or **replaceState()**.  
`(Slide Scroll Restoration)`  
The **scrollRestoration** property of History interface allows web applications to explicitly set default scroll restoration behavior on history navigation.  
Values:  
+ **"auto"** - The location on the page to which the user has scrolled will be restored.  
+ **"manual"** - The location on the page is not restored. The user will have to scroll to the location manually.  

`(Slide Methods)`  
History API. Methods.  
`(Slide Push State)`  
**pushState()**. In an HTML document, the **history.pushState()** method adds a state to the browser's session history stack.  
`(Slide Replace State)`  
**replaceState()**  
The **replaceState()** method modifies the current history entry, replacing it with the state objects, title, and URL passed in the method parameters.  
This method is particularly useful when you want to update the state object or URL of the current history entry in response to some user action.  
`(Slide Parameter: state)`  
Parameter: **state**  
The **state** object is a JavaScript object which is associated with the new history entry created by **pushState()**. And we can subsequently pass this object to the **replaceState()** method. Whenever the user navigates to the new state, a **popstate** event is fired, and the **state** property of the event contains a copy of the history entry's **state** object.  
`(Slide Parameter: title)`  
Parameter: **title**.  
Most browsers currently ignores this parameter, although they may use it in the future.Passing the empty string here should be safe against future changes to the method.  
`(Slide Parameter: url)`  
And third parameter is **url**  
The new history entry's URL is given by this parameter. The browser won't attempt to load this URL after a call to **pushState()**, but it might attempt to load the URL later, for instance after the user restarts the browser. This parameter is optional; if it isn't specified, it's set to the document's current URL. The new URL does not need to be absolute; if it's relative, it's resolved relative to the current URL.  
`(Slide The popstate event)`  
History API. The popstate event.  
`(Slide Popstate)`  
A **popstate** event is dispatched to the window every time the active history entry changes. If the history entry being activated was created by a call to **pushState()** or affected by a call to **replaceState()**, the **popstate** event's **state** property contains a copy of the history entry's **state** object.  
For example, looked the following expression, where funcRef is a handler function.  
`(Slide Note)`  
Note that just calling **history.pushState()** or **history.replaceState()** won't trigger a **popstate** event. The **popstate** event will be triggered by doing a browser action such as a click on the **back** or **forward** button (or calling **history.back()** or **history.forward()** in JavaScript).  
`(Slide Sources)`  
And sources... Thank you for attention, and good evening, and bye.  
