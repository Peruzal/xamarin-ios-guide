# Progress Bar

A progress bar includes a track that fills from left to right to show the progression of a task with a known duration. Progress bars are noninteractive, although they are often accompanied by a button for canceling the corresponding operation.

The progress bar is an instance of the `UIProgressView`.

## Configuring in the story board

The properties shown on the figure nelow can be configured for the progress view:

![Progress view properties][1]

The following video show the progress view:

<video src="https://developer.apple.com/design/human-interface-guidelines/ios/images/Progress_Bar.mp4" class="device-iphonex-image-half device-iphonex-image-top" width="50%" controls></video>


## Configuring in code

You can move the progress bar by initially setting a value for the `Progress` property and then increment it as follows:

```csharp
// Move the progress to 90% and animate the move
// The progress is between 0 and 1
progressView.SetProgress(0.8f, true);
```

[1]: images/progress-properties.png