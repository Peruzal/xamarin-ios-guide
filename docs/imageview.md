# Image Views 

An image view displays a single image or an animated sequence of images over a transparent or opaque background. The image view is an instance of the `UIImageView` class. It displays ab object of type `UIImage`.

You can configure image views programmatically or in your storyboard file and change the images they display at runtime.

## Configuring image view from storyboard

![Imageview][1]

To add the image, do the following:

1. Open the asset catalog file, Assets.xcassets, if its not there, you can create one
2. Create a New Image Set
![Create Image Set][2]
3. Add the different resolutions of the image
4. On the storyboard, select the image view, select the image from the drop down list on the **Properties** window -> **Image View** -> **Image**.

![Select image][3]

## Loading the image in code

To load the image in code from the asset catalog, we can use the following code:

```csharp
logoImageView.Image = UIImage.FromBundle("logo");
```

!!! info "Creating images"
    We can create images from resource, bundle, data or from another image. We can also create animated images using multiple image file names.

[1]: /images/imageview.png
[2]: /images/new-image-set.png
[3]: /images/select-image.png