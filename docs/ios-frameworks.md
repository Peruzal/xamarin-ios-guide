# iOS Frameworks

iOS comes with a lot of frameworks that enables developers to perform complex tasks easily. You have already been using the UIKit framework. 

![iOS Frameworks][1]

For more information on how to use the framework, check the documentation on the [developer website][2].

We going to see how to use the Contacts framework.

## Picking a contact

To pick a contact, you create `CNContactPickerViewController`, and then provide a delegate to handle events. The `CNContactPickerViewController` comes from the `ContactsUI`.

```csharp
var contactPicker = new CNContactPickerViewController();
// Make the current class the delegate
contactPicker.Delegate = this;

// Present the controller
PresentViewController(contactPicker, true, null);
```

Since we made the delegate the current class, we will need to implement an interface, `ICNContactPickerDelegate` as follows:

```csharp
public partial class ViewController : UIViewController, ICNContactPickerDelegate {

}
```

## Handle selected contact

To get the contact, we implement the method `DidSelectContact()` as follows:

```csharp
[Export("contactPicker:didSelectContact:")]
public void DidSelectContact(CNContactPickerViewController picker, Contacts.CNContact contact)
{
    Debug.WriteLine($"Selected contact {contact.GivenName} {contact.PhoneNumbers[0].Value.StringValue}");
}
```

![Contacts picker][3]


[1]: images/frameworks.png
[2]: https://docs.microsoft.com/en-us/xamarin/ios/platform/
[3]: images/contacts-picker.png