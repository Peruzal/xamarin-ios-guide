# View Controller

```csharp
public partial class ViewController : UIViewController
{
    public ViewController (IntPtr handle) : base (handle)
    {

    }
}
```

## View Controller life cycle

These are the basic lifecycle methods and their function:

- `ViewDidLoad` - Called once the first time the view controller loads its Content View Hierarchy into memory. This is a good place to do initial setup because it is when Subviews first become available in code.
- `ViewWillAppear` - Called every time a view controller's View is about to be added to a Content View Hierarchy and appear on the screen.
- `ViewWillDisappear` - Called every time a view controller's View is about to be removed from a Content View Hierarchy and disappear from the screen. This lifecycle event is used for cleanup and saving state.
- `ViewDidAppear` and `ViewDidDisappear` - Called when a View gets added or removed from the Content View Hierarchy, respectively.

## Responding to user interaction

The most important role of the view controller is responding to user interaction, such as button presses, navigation, and more.