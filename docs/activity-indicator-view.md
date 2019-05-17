# Activity Indicator View

A view that shows that a task is in progress. It is an instance of the ` UIActivityIndictorView`. It has two method method used to control the animation, `StartAnimating()` and `StopAnimating()`;

![Activity Indicator View][1]

## Purpose

- Activity Indicators should be shown when your app is running a long process, but you don't know the exact length of time the task will require.

<video src="https://developer.apple.com/design/human-interface-guidelines/ios/images/Activity_Indicators.mp4" width="50%" controls></video>

## Configuring through the story board

Add the activity indicator view from the Toolbox. You can change the Behavior:

- Animating: The view will automatically start to animate when its visible
- Hides When Stop: The view will hide when you call its stop by calling the `StopAnimating()` method

![Activity indicator properties][2]

## Start and stopping the animation

The following shows how you start and stop the animation from code:

```csharp hl_lines="4 9"
partial void HandleLogin(UIButton sender)
{
    // Start the animation
    loadingView.StartAnimating();
    // Perform some long operation here

    // Stop the animation
    // Will also hide when "Hides When Stop is true"
    loadingView.StopAnimating();
}
```

[1]: /images/activity-indicator-view.png
[2]: /images/activity-indicator-properties.png