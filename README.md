# MongooseDaemonBySwift
Make an Http local server in ios device by swift




# MongooseDaemon

MongooseDaemon is an objective C wrapper around the embedable mongoose http server for iPhone development. It is offered under a BSD style license.

MongooseDaemon is ideal for both embedded http services as well as simply debugging your iPhone applications file structure.

Mongoose is a lightweight embedable http server written by Sergey Lyubka and offered under a BSD style license. More information on mongoose can be found at the project's site here: https://code.google.com/p/mongoose/

NOTE: The mongoose.h and mongoose.c are taken directly from mongoose-2.6 and are unmodified. They are simply forked in this package for convenience and stability.

Usage

Clone the mongoose directory and add it to your X-Code project.

Then you can start it within one of you classes to provide http access to your iPhone application.

For example, to start MongooseDaemon when your application starts on port 8080:
create Bridge for objectiveC code to swift
Add Import To Bridge File

```objectiveC
#import "MongooseDeamon.h"
```

Add the following to AppDelegate.swift:

```swift
@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
 ...
 let mongooseDeamon  = MongooseDaemon()
    
...
}
```


for start when running:
```swift
 func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
...
        mongooseDeamon.startMongooseDaemon("8080")
....   
 }

```

And For Stop

```swift
    func applicationWillTerminate(application: UIApplication) {
...
        mongooseDeamon.stopMongooseDaemon()
 ...
   }
```
And that's it…an embeded http server with only about 9 lines of code!

TODO

1) Add a helper method to return the server's URL for convience

2) Add support for some of mongoose's rich feature set.

3) Investigate if there is anyway to server files over endge/3g instead of just WiFi.

For More Information https://github.com/face/MongooseDaemon
