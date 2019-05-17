# Stepper

A control used to increment or decrement a value. The stepper is an instance of the `UIStepper`.

![Stepper][1]

## Configuring properties

The following figure shows the stepper properties that can be configured from the story board:

![Stepper Properties][2]

## Handle value changed event

You can wire up the `ValueChanged` event for the stepper from the story board as the following figure shows:

![Stepper value changed event][3]

and add the method in the view controller as follows:

```csharp
partial void HandlePrintCopies(UIStepper sender)
{
    labelCopies.Text = $"{sender.Value} Copies";
}
```

The `ValueChanged` event can also be wired up directly from code as follows:

```csharp
stepper.ValueChanged += (sender, e) => {
    Debug.WriteLine(stepper.Value);
};
```

The `stepper` variable have been defined from the story board.

[1]: /images/stepper.png
[2]: /images/stepper-properties.png
[3]: /images/stepper-value-changed-event.png
