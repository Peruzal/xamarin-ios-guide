# Passing data between view controller

We are going to discuss two things in this section:

- Pass data to the view controller
- Get data from a called view controller

## Pass data to the view controller

You can pass data to a view controller by overriding the `PrepareForSegue()` method, getting the `DestinationViewController` property of the segue and assigning the public properties on it.

In the figure below, we want to share the first name of the logged in with the courses view controller.

![Pass data between view controller][1]

We have two view controllers, `LoginViewController` and `CoursesViewController`. In the `CoursesViewController` we have a public `FirstName` property define.

### Give the segue a name

1. From the story board, click and drag whilst holding the <kbd>Ctrl</kbd> control from the login button to the navigation controller that have the `CourseViewController` as root. Choose the `Show` segue.

2. Give a name to the segue. You will use the name to check if we are navigating to the `CoursesViewController`.

### Pass data in the `PrepareForSegue()` method

In the `LoginViewController` implement the `PrepareForSegue()` method and assign the the property of the first name as follows:

```csharp
public override void PrepareForSegue(UIStoryboardSegue segue, NSObject sender)
{
    base.PrepareForSegue(segue, sender);

    // check if we are segeuing to the LoginViewController
    if (segue.Identifier.Equals("login")) {
        // Get the destination view controller
        // The destination is navigation controller with the root controller CoursesViewController
        var navVC = segue.DestinationViewController as UINavigationController;

        // Get the top view controller from the navigation controller
        var dvc = navVC.TopViewController as CoursesViewController;

        // Get the data from the login and assign to property
        // Hard coded here for simplicity
        dvc.FirstName = "Joseph";
    }
}
```

When you run, you should now be able to see the message _Welcome Joseph_ on the course view controller.

!!! caution "Using PrepareForSegue()"
    The `PrepareForSegue()` method is called for any segue to another view controller. You should check the identifier and also the destination view controller. If you don't properly check, the app will crash.


## Get data from a called view controller

They are cases where you need to segue to a view controller and get back the data back to the calling view controller. View controller A calls B view controller. We need to pass data back from view controller B to A when B is dismissed.

We are going to use the fire below for our demo. We want to get the email address used once the user finishes registration.

![Pass Data Back][2]

To pass the data back, we need to do the following:

1. Create the unwind segue in the first view controller
2. Wire up the segue from the second view controller
3. Pass data when we dismiss the segue

### Create the unwind segue




[1]: /images/pass-data.png
[2]: /images/pass-data-back.png