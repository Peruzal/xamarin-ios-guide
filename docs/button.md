# Button


Buttons initiate app-specific actions, have customizable backgrounds, and can include a title or an icon. The system provides a number of predefined button styles for most use cases. You can also design fully custom buttons. The button derives from the `UIButton` class.

![Button][1]

## System Buttons

System buttons often appear in navigation bars and toolbars, but may be used anywhere.

- **System**: A general-purpose button
- **DetailDisclosure**: Indicates the availability of detailed information, usually about a specific item in a table
- **InfoDark**: Indicates the availability of configuration information; dark-colored
- **InfoLight**: Indicates the availability of configuration information; light-colored
- **AddContact**: Indicates that a contact can be added
- **Custom**: Customizable button


## Configuring the button

![Button properties][2]

## Button events

To handle the button click event, use the `Touch Up Inside` event. The event can be added from the Properties window or in code.

### Add event in code

1. Select the button from interface builder
2. From the Properties window, under the Identity section, assign a `Name` to the button
![Button assign name][3]
2. From the backing `ViewController` file wire up the event as follows

```csharp hl_lines="4"
public override void ViewDidLoad()
{
    base.ViewDidLoad();
    btnLogin.TouchUpInside += (sender, e) => { 
        // Handle the button click here
    };
}
```

### Add event from interface builder

You can also add the event from within interface builder.

1. Select the button from interface builder
2. Open the **Properties** window
3. Choose the **Events** section
4. Add the name of the method to handle the event
5. Visual Studio code editor will open and let you choose where to place the event handler method

<video width="100%" controls>
    <source src="/videos/add-button-event.mp4">
</video>

## Custom button types

You can create custom button types by using images. Set the Image property from interface builder. You can also use code ot change the button image as below:

```csharp
btnSignUp.SetImage(UIImage.FromBundle("logo"), UIControlState.Normal);
```

Using the `UIImage.FromBundle` finds the iamge already defined in the asset catalog.

![Asset catalog image][4]

[1]: /images/button.png
[2]: /images/button-properties.png
[3]: /images/button-name.png
[4]: /images/asset-catalog-image.png