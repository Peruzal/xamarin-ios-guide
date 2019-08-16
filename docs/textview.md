# Text View

A text view displays multiline, styled text content. Text views can be any height and enable scrolling when the content extends outside of the view. By default, content within a text view is left-aligned and uses the system font in black. If a text view is editable, a keyboard appears when you tap inside the view.

The text field is an instance of the `UITextView` class which inherits from `UIScrollView`.

![TextView][1]

## Configuring the properties

The following properties can be configured from the story board:

![Text field properties][2]

In addition to those properties, the textfield inherits from the `UIScrollView` so you can also configure the `UIScrollView` properties as shown below:

![TextView scroll view properties][3]


- Specific properties include:

- **Behavior** – Whether the text is editable or read-only.
- **Detection** – Detects and converts the inputted data into clickable elements such as phone numbers that can trigger a call, addresses that become links to Maps, URLs that open in Safari or dates and times that become events in Calendar.

## Handling text view events

The `UITextView` have similar events as the `UITextField`.

[1]: images/textview.png
[2]: images/textview-properties.png
[3]: images/textview-scrollview-properties.png