# Segmented Button

A segmented control is a linear set of two or more segments, each of which functions as a mutually exclusive button. Within the control, all segments are equal in width. 

![Segmented Control][1]

Like buttons, segments can contain text or images. Segmented controls are often used to display different views. In Maps, for example, a segmented control lets you switch between Map, Transit, and Satellite views.

The segmented button is an instance of the ` UISegmentedControl` class.

## Configuring segmented control

The following properties can be configured in the story board:

![Segmented control properties][2]

## Handle value changed event

You can also wire up the `ValueChanged` event from the story board as follows:

![Segmented Control Valued Changed Event][3]

and adding the method in the view controller code as follows:

```csharp
partial void HandleSegmentedChanged(UISegmentedControl sender)
{
    var title = sender.TitleAt(sender.SelectedSegment);
    Debug.WriteLine(title);
}
```

or you can wire up the event in code as follows :

```csharp hl_lines="4"
public override void ViewDidLoad()
{
    base.ViewDidLoad();
    mapOptions.ValueChanged += (sender, e) => {
        var title = mapOptions.TitleAt(mapOptions.SelectedSegment);
    };

}
```

[1]: images/segmented-control.png
[2]: images/segmented-control-properties.png
[3]: images/segmented-handle-event.png