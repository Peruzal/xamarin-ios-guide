# Maps and Location

iOS comes with two frameworks for working with maps and location. The MapKit frameworks provides the classes to work with maps and the CoreLocation library provides classes to work with location.

## Add a map

To add a map, add the map view from the toolbox. You can change the various properties as shown below:

![Add map view][1]

## Change map style

You can change the style on the map view using the `MapType` property on the map view as follows:

```csharp
partial void DidChangeMapType(UISegmentedControl sender)
{
    switch (sender.SelectedSegment) {
        case 0:
            MapView.MapType = MKMapType.Standard;
            break;
        case 1:
            MapView.MapType = MKMapType.Satellite;
            break;
        case 2:
            MapView.MapType = MKMapType.Hybrid;
            break;
    }
}
```

## Show user location

To show the user location, check the **User Location** on the map properties on the story board. You can also change in code as follows:

```csharp
MapView.ShowsUserLocation = true;
```

## Request permission for location

To access the user's location, you need to request the permission. You the `CLLocationManager` class to request location. You will need to add a value in the `Info.plist` value with the reason for requesting the user's location.

You can set one of the following based on how your app uses the use location:

- NSLocationWhenInUseUsageDescription
- NSLocationAlwaysAndWhenInUseUsageDescription 

!!! caution "Requesting location"
    Don't request authorization at launch time unless you need the user's location immediately or were launched in the background to receive a location update.

Use the location manager to request permission:

```csharp
var locationManager = new CLLocationManager();

switch (CLLocationManager.Status) {
    case CLAuthorizationStatus.NotDetermined:
        locationManager.RequestWhenInUseAuthorization();
        break;
}
```

The above have been simplified, you will need to handle the different states for your app to work properly.

## Subscribe to user location changes

You can subscribe to `DidUpdateUserLocation` event to be notified when the user location changes as follows:

```csharp
MapView.DidUpdateUserLocation += MapView_DidUpdateUserLocation;
```

and center the map on the user's location as follows:

```csharp
void MapView_DidUpdateUserLocation(object sender, MapKit.MKUserLocationEventArgs e)
{
    var span = new MKCoordinateSpan(0.2, 0.2);
    var region = new MKCoordinateRegion(e.UserLocation.Coordinate, span);
    MapView.SetRegion(region, true);

}
```



[1]: /images/mapview-properties.png