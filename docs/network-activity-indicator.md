# Network Activity Indicators

On devices without edge-to-edge displays, a network activity indicator spins in the status bar at the top of the screen as networking occurs. It disappears when networking is complete. This indicator looks just like an activity indicator and is noninteractive.

<video controls width="312" height="278" src="https://developer.apple.com/design/human-interface-guidelines/ios/images/network_activity.mp4" type="video/mp4" style="display: block;"></video>

## Showing the indicator

The network activity indicator is not available in the Toolbox. To show it, use the `UIApplication.SharedApplication.NetworkActivityIndicatorVisible` and toggle it between `true` and false as follows:

```csharp
// Display the activity indicator
UIApplication.SharedApplication.NetworkActivityIndicatorVisible = true;

// Hide the activity indicator
UIApplication.SharedApplication.NetworkActivityIndicatorVisible = false;
```