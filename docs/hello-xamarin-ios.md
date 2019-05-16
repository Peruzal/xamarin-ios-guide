# Creating your first Xamarin.iOS project

To make sure you development environment is properly setup, we are going to create the traditional Hello World app for iOS.

## Create a new project from template

Using the template, choose **iOS** and then select the **Single View App** template.

![Create new project ios][1]

From the figure above: 

1. Choose **iOS** -> App
2. Select the S**ingle View App**

!!! info "Templates"
    Visual Studio provides various starter templates. In development your app, you can select other templates based on your app requirements.

### Configure project

![Configure new project][1]

1. **App Name**: This is the name of your app
2. **Organization Identifier**: Is used to created a unique name for you app on the App Store. Each app should have a unique name. You can use the reverse DNS of your organization since its guaranteed to be unqiue.
3. **Team**: You can sign in if you have an Apple Developer account. Visual Studio will automatically manage the certificates for you.
4: **Devices**: The devices to target with your app
5. **Target**: The iOS versions the app should run on. Choose a lower version to target older iOS versions.

## Exploring the project

Once the project is created, you should have the project as the figure below.

![Visual Studio][3]

### Run the app

By default, Visual Studio will select the latest iPhone emulator, you can change which emulator to run your app on.

- Click the **Play** button to run the app on the emulator. 

![Run app on emulator][4]

!!! info "No view displayed"
    Unfortunately the default template for Visual Studio 2019 on a Mac does not contain any views, so when you run, you will see a blank white screen.

![Blank emulator][5]

### Adding views

We are going to add a label using the Storyboard. You create your UI in iOS using storyboards.

1. Open the **Main.storyboard**
2. From the **Toolbox** drag the **Label**
3. Use the guides and align the **Label** at the center
![Add Label][6]
4. Add the text "Hello World"
5. Resize the label
6. Align the text using the **Properties** inspector window
![Align label center][7]
7. Run again, and you should see the emulator with the _Hello World_ text displayed on the center

<video width="100%" controls>
    <source src="/videos/add-label.mp4" type="video/mp4">
</video>

## Exploring the project

On the left is the solution Pad, which contains the directory structure and all the files associated with the solution:

![Project Structure][8]

The items in the project include:

- **References** - Contains the assemblies required to build and run the application.
- **Packages** - The packages directory contains ready-made NuGet packages.
- **Assets.xcassets** - The asset catalog contains image file for the different resolutions.
- **Resources** - The resources folder stores other media.
- **Main.cs** – This contains the main entry point of the application. To start the application, the name of the main application class, the AppDelegate, is passed in.
- **AppDelegate.cs** – This file contains the main application class and is responsible for creating the Window, building the user interface, and listening to events from the operating system.
- **Main.storyboard** - The Storyboard contains the visual design of the application’s user interface. Storyboard files open in a graphical editor called the iOS Designer.
- **LaunchScreen.storyboard** - The storyboard used to create the splash screen. This is automatically displayed when the app starts.
- **ViewController.cs** – The view controller powers the screen (View) that a user sees and touches. The view controller is responsible for handling interactions between the user and the View.
- **ViewController.designer.cs** – The designer.cs is an auto-generated file that serves as the glue between controls in the View and their code representations in the view controller. 
- **Info.plist** – The Info.plist is where application properties such as the application name, icons, launch images, and more are set.
- **Entitlements.plist** - The entitlements property list lets us specify application capabilities (also called App Store Technologies) such as iCloud, PassKit, and more. 

The figure below shows the **Assets.xcassets** showing the AppIcon with the different images for the different devices.

![Image Asset Catalog][9]

The figure below show the Visual Studio editor with the various window panes open:

![Visual Studio Editor Window][10]

1. **Solution** pane: Show the files in th eproject
2. **Main editor area**: Shows the code editor or the storyboard
3. **Toolbox**: You drag the various controls from here onto the storyboard
4. **Properties pane**: used to change the properties of the views on the storyboard
5. The controls used to switch the editor to between edit mode and constraints mode. Constraints are used to position the views correctly on the different device resolutions.

## Application fundamentals

Let's explore how an iOS application is loaded.

1. The entry point into an iOS application is defined in `Main.cs` in the `Main()` method
```csharp
public class Application
{
    // This is the main entry point of the application.
    static void Main(string[] args)
    {
        // if you want to use a different Application Delegate class from "AppDelegate"
        // you can specify it here.
        UIApplication.Main(args, null, "AppDelegate");
    }
}
```
- The `Main.cs` uses a class that derives from the `UIApplicationDelegate` to handle system wide events. The `Main.cs` hands over control to the `AppDelegate` class

- The `ApplicationDelegate` implements various methods to handle system wide events. In the `FinishedLaunching` it loads the storyboard file. The main story board file is defined in the `Info.plist` file.
![Main Storyboad startup][11]

The code below shows the `UIApplicationDelegate` derived class that loads the story board
```csharp
// The UIApplicationDelegate for the application. This class is responsible for launching the
// User Interface of the application, as well as listening (and optionally responding) to application events from iOS.
[Register("AppDelegate")]
public class AppDelegate : UIApplicationDelegate
{
    // class-level declarations

    public override UIWindow Window
    {
        get;
        set;
    }

    public override bool FinishedLaunching(UIApplication application, NSDictionary launchOptions)
    {
        // Override point for customization after application launch.
        // If not required for your application you can safely delete this method

        return true;
    }
    ...
}
```

- When the `Main.storyboard` loads, it defines the `Initial Root View Controller`

![Initial Root View Controller][12]

The figure below summarises how the app is loaded and the different files involved:

![Application loading cycle][13]

[1]: images/vs-create-new-project-step-1.png
[2]: images/vs-create-new-project-step-2.png
[3]: images/vs-editor.png
[4]: images/run-app.png
[5]: images/blank-emulator.png
[6]: images/add-label.png
[7]: images/label-change-alignment.png
[8]: images/project-structure.png
[9]: images/asset-catalog.png
[10]: images/visual-studio-editor.png
[11]: images/main-storyboard.png
[12]: images/initial-root-view-controller.png
[13]: images/app-architecture.png