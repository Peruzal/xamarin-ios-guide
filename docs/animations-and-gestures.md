# Animations and Gestures

iOS was built from the ground up to support animations. It is absolutely required to maintain the illusion of a touch-based interface.

## Simple Animation with UIKit

The `UIView` class provides an `Animate()` method to perform simple animations on views. 

### Move animation

Most of the time, you will perform animation by working directly with `UIKit`. You can animate any property of the view, e.g the following changes the position of the view change its frame:


```csharp
UIView.Animate(0.5, () =>
{
    logoImageView.Frame = new CGRect(View.Center.X, View.Center.Y, logoImageView.Frame.Width, logoImageView.Frame.Height);
});
```

## Fade in animation

To fade in, we can change the alpha of the view as follows:

```csharp
logoImageView.Alpha = 0;
UIView.Animate(0.5, () =>
{
    logoImageView.Alpha = 1;
});
```

### Scale animation

We can animate the `Transform` property of the view by scaling it up or down as follows:

```csharp
// Scale by 2
var scaleTransform = CGAffineTransform.MakeScale(2, 2);
var originalTransform = CGAffineTransform.MakeScale(1, 1);

UIView.Animate(0.5, () =>
{
    logoImageView.Transform = scaleTransform;
},

    () =>
    {
        logoImageView.Transform = originalTransform;
    });
```

You can find more animation recipes [here][1].


## Gestures

iOS supports several gestures. You can add the gestures from the Toolbox.

![Gestures][2]

[1]: https://gist.github.com/josephkandi/51f51802ce2e633be5dd99f1fc8787f6
[2]: /images/gestures.png