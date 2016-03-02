# CrisisMap mobile application

**to build:**

1. build crisismap project (`app` directory)
1. `cordova platform add browser`
1. `cordova platform add ios`
1. `cordova plugin add cordova-plugin-device`
1. `cordova plugin add cordova-plugin-geolocation`
1. patch `platforms/ios/CrisisMap/Classes/MainViewController.m` with following code to prevent web view bouncing
    ```objective-c
    - (void)viewDidLoad
    {
        [super viewDidLoad];
        UIScrollView* sv = nil;
        for (UIView* v in self.webView.subviews){
            if ([v isKindOfClass:[UIScrollView class] ]){
                sv = (UIScrollView*) v;
                sv.bounces = NO;
            }
        }
    }
    ```
1. build project with XCode
