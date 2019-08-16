# Switch

A switch is a visual toggle between two mutually exclusive states—on and off. The switch is an instance of the `UISwitch` class.

![Switch][1]

## Configuring switch properties

The following figure show the properties of the switch that can be configured from the story board:

![Switch properties][2]

## Handle changed event

We can wire up the `ValueChanged` event from the story board as show below:

![SwitchValue Changed Event][3]

and add the method in the view controller file as follows:

```csharp
partial void HandleRingChanged(UISwitch sender)
{
    Debug.WriteLine(sender.On);
}
```

The `On` property will be `true` or `false` as you toggle the switch.

The event could also be wired in code as follows:

```csharp
ringSwitch.ValueChanged += (sender, e) => {
    Debug.WriteLine(ringSwitch.On);
};
```

`ringSwitch` variable name is setup in the story board **Properties** window.

[1]: images/switch.png
[2]: images/switch-properties.png
[3]: images/switch-changed-event.png