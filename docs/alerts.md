# Displaying Alerts

Alerts are used to present important information to the user or prompt the user about an important choice.

Alerts and action sheets interrupt your app’s normal flow to display a message to the user.

!!! caution "Using alerts"
    Because alerts and action sheets are an interruption, use them sparingly and only when absolutely needed.

## Display an alert

You can present different types of alerts. To display an alert you need to do the following:

1. Create an an object of type ` UIAlertController` and choose the preferred style
2. Actions actions of type ` UIAlertController `
3. Present the controller

### Create alert view controller

Create an object that is an instance of the `UIAlertController` and choose the preferred style. There are two styles:

- `UIAlertControllerStyle.Alert` - Creates an alert dialog that appears in the middle of the screen 
- `UIAlertControllerStyle.ActionSheet` - Creates an action sheet that appears from the bottom with the different options

The following code creates an alert style with a tile and a message:

```csharp
var alertController = UIAlertController.Create("Terms and Conditions", 
    "Click Agree to accept the terms and conditions.", 
    UIAlertControllerStyle.Alert);
```

## Create the actions

The different button options are created as actions. The following code creates two actions, a default and cancel action.

The default action

```csharp
var defaultAction = UIAlertAction.Create("Agree", UIAlertActionStyle.Default, (UIAlertAction action) =>
{
    // Perform action action on default action
});
```

and the cancel option:

```csharp
var cancelAction = UIAlertAction.Create("Disagree", UIAlertActionStyle.Cancel, (UIAlertAction obj) =>
{
    // Perform action for cancel
});
```

### Add the actions to the alert controller

You need to add the actions to the alert controller object as the following code shows:

```csharp
// Add actions
alertController.AddAction(defaultAction);
alertController.AddAction(cancelAction);
```

### Present the alert

Finally we can present the alert as follows:

```csharp
PresentViewController(alertController, true, null);
```

The above code will show the following figure when run:

![Alert view][1]

## Action Sheet

An action sheet is a specific style of alert that appears in response to a control or action, and presents a set of two or more choices related to the current context. Use an action sheet to let people initiate tasks, or to request confirmation before performing a potentially destructive operation.

On smaller screens, an action sheet slides up from the bottom of the screen. On larger screens, an action sheet appears all at once as a popover.

![Action Sheet][2]

You can change the code above by changing the style to `ActionSheet`. You will also need to add more actions. 

### Dsiplaying action sheet on iPad

On devices with a larger screen, the action sheet is displayed as a pop over. To display the action as a pop over, you need to set the view for which the pop over will anchor to when displayed.

```csharp
var presentationPopOver = alertController.PopoverPresentationController;
// Check if the action sheet is displayed ona larger screen
if(presentationPopOver != null) {
    // Set the cource view
    presentationPopOver.SourceView = sender;

    // Choose the direction to anchor
    presentationPopOver.PermittedArrowDirections = UIPopoverArrowDirection.Down;
}
```

The action sheet will display as the figure below on the ipad:

![Action sheet on iPad][3]

[1]: /images/alert-view.png
[2]: /images/action-sheet.png
[3]: /images/action-sheet-ipad.png