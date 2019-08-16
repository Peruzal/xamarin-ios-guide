# Slider

A slider is a horizontal track with a control called a thumb, which you can slide with your finger to move between a minimum and maximum value, such as screen brightness level or position during media playback. 

The slider is an instance of the `UISlider` class.

![Slider][1]

!!! info "Slider"
    A slider can optionally display left and right icons that illustrate the meaning of the minimum and maximum values. ![Slider][2]

## Configuring properties in the story board

The following properties shown on the figure below can be customized:

![Slider properties][3]

## Setting slider values

You can change the slider value in code as follows:

```csharp
// Sets the value to 80% and animates the change
slider.SetValue(0.8f, true);
```

## Slider events

You can set the `ValueChanged` event to get the values as the slider is moved as follows:

```csharp
slider.ValueChanged += (object sender, EventArgs e) => {
    Debug.WriteLine(slider.Value);
};
```

The event can also be hooked in the storyboard on the **Properties** window **Events** section.

![Slider value changed event][4]

and wire up the method in the view controller as follows :

```csharp
partial void HandleValueChanged(UISlider sender)
{
   // Implement to handle the changes on the slider
}
```

[1]: images/slider.png
[2]: images/sliders_2x.png
[3]: images/slider-properties.png
[4]: images/slider-value-changed-event.png