# View Controller

A view controller manages a single root view, which may itself contain any number of subviews. The view controller is the **VC** in the **MVC(Model View Controller)** design pattern.

- User interactions within a view are handled by the view controller.
- Every app has at least one view controller whose content fills the main window. 
- If your app has more content than can fit onscreen at once, use multiple view controllers to manage different parts of that content.

The view controller is an instance of `UIViewController`. UIKit provides several view controllers and you derive from an instance:

- `UIViewController`: An object that manages a view hierarchy for your UIKit app
- `UITableViewController`: A view controller that specializes in managing a table view.
- `UICollectionViewController`: A view controller that specializes in managing a collection view.
- `UINavigationController`: A container view controller that defines a stack-based scheme for navigating hierarchical content.
- `UIPageViewController`: A container view controller that manages navigation between pages of content, where each page is managed by a child view controller.
- `UITabBarController`: A container view controller that manages a radio-style selection interface, where the selection determines which child view controller to display.
- `UISearchController`: A view controller that manages the display of search results based on interactions with a search bar.
`UIImagePickerController`- A view controller that manages the system interfaces for taking pictures, recording movies, and choosing items from the user's media library.
`UIVideoEditorController`: A view controller that manages the system interface for trimming video frames and encoding a previously recorded movie.
- `UIActivityViewController`: A view controller that you use to offer standard services from your app.
- `UIPresentationController`: An object that manages the transition animations and the presentation of view controllers onscreen.

and they are many more

## UIViewController

An object that manages a view hierarchy for your UIKit app. The UIViewController class defines the shared behavior that is common to all view controllers. 

You rarely create instances of the UIViewController class directly. Instead, you subclass UIViewController and add the methods and properties needed to manage the view controller's view hierarchy.

A view controller is tightly bound to the views it manages and takes part in handling events in its view hierarchy. 

View controllers are rarely used in isolation. Instead, you often use multiple view controllers, each of which owns a portion of your app’s user interface. For example, one view controller might display a table of items while a different view controller displays the selected item from that table.

```csharp
public partial class ViewController : UIViewController
{
    public ViewController (IntPtr handle) : base (handle)
    {

    }
}
```

## View Management

Each view manages a view hierachy, the view controller have the `View` property, which is the root view. The root view is the parent view for the rest of the hierarchy.

## Creating View Controller

View controllers can be created in the story board. Within the story board, the app views and connections to other view controller is specified.

### Creating a view controller from the storyboard

You can use code to instantiate a view controller using the `InstantiateViewController()` method of the story board as follows:

```csharp
// Instantiate a view controller with StoryBoardID ControlsTableViewController
var controlsTVC = Storyboard.InstantiateViewController("ControlsTableViewController") as ControlsTableViewController;

// Present the view controller
PresentViewController(controlsTVC, true, null);
```

The above view controller have the properties set as show in the figure below:

![Instantiate View Controller][2]


## View transitions

When the visibility of its views changes, a view controller automatically calls its own methods so that subclasses can respond to the change.

![View controller notifications][1]


- `ViewDidLoad` - Called once the first time the view controller loads its Content View Hierarchy into memory. This is a good place to do initial setup because it is when Subviews first become available in code.
- `ViewWillAppear` - Called every time a view controller's View is about to be added to a Content View Hierarchy and appear on the screen.
- `ViewWillDisappear` - Called every time a view controller's View is about to be removed from a Content View Hierarchy and disappear from the screen. This lifecycle event is used for cleanup and saving state.
- `ViewDidAppear` and `ViewDidDisappear` - Called when a View gets added or removed from the Content View Hierarchy, respectively.

## Responding to user interaction

The most important role of the view controller is responding to user interaction, such as button presses, navigation, and more.

[1]: /images/viewcontroller-notifications.png
[2]: /images/storyboard-id.png