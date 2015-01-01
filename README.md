SharedData
==========

Share data between iPhone App and Apple Watch Extension with this singleton class

### Code Usage ###

If you follow the Setup instructions below you'll be able to access the SharedData.sharedInstance singleton from both the Watch Extension and in the App project files and be able to access the same data stored in Core Data and NSUserDefaults from the App and the Extension.

#### Core Data ####

```swift
let moc = SharedData.sharedInstance.managedObjectContext
SharedData.sharedInstance.saveContext()
```

#### NSUserDefaults ####
```swift
var defaults = SharedData.sharedInstance.defaults
defaults.setObject("myValue", forKey: "myKey")
```
### Setup instructions ###

1) Add Apple Watch Extension Target to the project

2) Make sure Core Data Model is included in project and set-up with necessary entities

3) Remove any Core Data code in the App Delegate

4) Include SharedData.swift into the project

5) Enable App Groups in Project Capabilities Settings for both the Extension and the App

6) In SharedData.swift change appName and appDomain values repective values.

7) Make sure the following files are members of both the App target and the Extension target:
* SharedData.swift
* AppName.xcdatamodeld
* Any generated NSManagedObject subclasses
