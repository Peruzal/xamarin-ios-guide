# TextField

Text fields allows the user to input a single line of text into an app. The text field is a subclass of the `UITextField` class.


### Purpose

- Gather small amounts of text from the user.
- Perform some immediate action on the text, such as a search operation

### Configuring TextField properties

You can configure the properties of the `TextField` in interface builder. Some properties of the `TextField` can not be changed with the properties window, they can only be changed in code.

The following figure shows the fields that can be changed in the **Properties** window:

![Textfield Properties][1]

- **Placeholder** – This is optional. If set, it is displayed when the text field is empty, usually to explain to the user what input is expected.
- **Clear Button** – This controls when the standard clear button (the grey circle with <kbd>X</kbd>) appears in the text field, as a way for the user to clear text quickly. It can be permanently hidden, permanently visible, or shown, depending on whether or not the field is being edited.
- **Min Font Size** and **Adjust to Fit** – Allows the font size to be adjusted automatically to fit longer text and prevent truncation, but limited to no smaller than the specified size.
- **Capitalization** – Whether to automatically capitalize words, sentences or all input.
- Correction – Whether spell checking and suggestions are enabled.
- **Keyboard** – Controls the keyboard style displayed for the input, and therefore what keys are available on the keyboard. This includes `Number Pad`, `Phone Pad`, `Email`, `URL` along with other options.
- **Appearance** – Controls the appearance style of the keyboard and will be either dark or light themed.
- **Return Key** – Change the label on the <kbd>Return</kbd> key to better reflect what action will be taken. Supported values include <kbd>Go</kbd>, <kbd>Join</kbd>, <kbd>Next</kbd>, <kbd>Route</kbd>, <kbd>Done</kbd>, and <kbd>Search</kbd>.
- **Secure** – Identifies whether the input is masked (such as for a `Password` input).

### Handling text filed events

iOS uses the delegation pattern to handle events. In Xamarin.iOS the delegates are handled using events. You handle the events by creating them from the Properties window:

![Text field events][2]

The figure below shows the `ValueChanged` event wired up in the Properties window:

![Textfield value changed][3]

and the code in the `ViewController`

```csharp
partial void ValidatePassword(UITextField sender)
{
    // Handle the changes character by character for the text field
}
```

[1]: /images/textfiled-properties.png
[2]: /images/textfield-events.png
[3]: /images/textfield-changed-event.png