# Setting up Development Environment

You can develop with Xamarin.iOS from Windows or a Mac.

!!! info "You need access to a Mac from Windows"
    Although you can develop iOS applications from Windows, you will need access to a Mac running XCode to build the application.

## Install on a Mac

To create iOS app you will need:

- XCode
- Xamarin.iOS

### Installing XCode

XCode can be installed from the Mac App Store. Search for XCode, install the latest one.

![App Store XCode][1]

### Install Visual Studio

You will need to setup Xamarin.iOS during the Visual Studio installation. Download Visual Studio and run the setup, make sure to select Xamarin.iOS during the setup.

![Xamarin.iOS Installation][2]

For a step by step installation check out the [Microsoft documentation][3].

## Install on Windows

There's nothing to install on Windows as you will access everything from the Mac. Visual Studio will make a connection to a Mac through SSH, you can use a mac machine on the local network or use a remote one e.g [Mac In Cloud][4].

### Pair Windows to Mac

You will need to pair your Windows machine to a Mac.

1. Enable remote connection on the Mac
2. Connect to the Mac from Visual Studio

#### Enable remote connection

To set up the Mac build host, first enable remote login:

- On the Mac, open **System Preferences**(Click the Apple logo at the top left corner) and go to the **Sharing** pane.
- Check **Remote Login** in the **Service** list.

![Remote Login][5]

Make sure that it is configured to allow access for **All users**, or that your Mac username or group is included in the list of allowed users.

### Connect from Visual Studio

Now that remote login is enabled, connect Visual Studio 2019 to the Mac.

- In Visual Studio 2019, open an existing iOS project or create a new one by choosing File > New > Project and then selecting an iOS project template.

- Open the Pair to Mac dialog.

![Pair Mac][6]

The **Pair to Mac** dialog displays a list of all previously-connected and currently-available Mac build hosts:

![Pair to Mac][7]

Connect to the Mac and enter your username and password when prompted.


If you have successfully paired to a Mac build host, you are ready to build Xamarin.iOS apps in Visual Studio 2019. 


[1]: images/app-store-xcode.png
[2]: images/xamarin-ios-install.png
[3]: https://docs.microsoft.com/en-gb/visualstudio/mac/installation?view=vsmac-2019
[4]: https://www.macincloud.com/
[5]: images/mac-remote-login.png
[6]: images/mkdocs.png
[7]: images/pairtomac.png
[6]: images/auth.png