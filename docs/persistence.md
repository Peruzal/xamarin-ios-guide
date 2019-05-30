# Persistence

In iOS we can keep arbitrarily user data using the `NSUserDefaults` class. For complex data we can use the SQLite library. The `NSUserDefaults` uses a plist to store the users preferences

## Save data

To save data use the `NSUserDefaults.StandardUserDefaults` and use one of the `Set` methods, providing the key and the value as follows:

```csharp
NSUserDefaults.StandardUserDefaults.SetString("joseph", "NICKNAME");
```

The first argument is the value, and the second argument is the key.

## Reading the preference

To read the value stored in the `NSUserDefaults` we can one of the methods that start with the type and provide the key as follows:

```csharp
var nickname = NSUserDefaults.StandardUserDefaults.StringForKey("NICKNAME");
```