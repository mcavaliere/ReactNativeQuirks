# ReactNativeQuirks
A list of React Native nuances I've been discovering. 

### App Store Rejections

Tl;DR: Don't use any plugins that use JSPatch. 

References
* [The reason why React Native apps may fail App Store review process](https://www.monterail.com/blog/2017/react-native-app-store)
* [JSPatch | Technology Radar | ThoughtWorks](https://www.thoughtworks.com/radar/languages-and-frameworks/jspatch)

### Invisible Images

Sometimes you'll use an `<Image />` element and RN will allocate visual space for it, but the image itself will not be visible. 

There are often 2 things wrong: 

* The image needs `width` and `height` values. 
* The image has a `http` URI instead of `https`.

The latter is a result of Apple enforcing https uris. 

References: 
* [SO Thread](https://stackoverflow.com/questions/38153335/react-native-loading-image-over-https-works-while-http-does-not-work)
* [TechRepublic Article](http://www.techrepublic.com/article/wwdc-2016-apple-to-require-https-encryption-on-all-ios-apps-by-2017/)


### `this` returns `DedicatedWorkerGlobalScope`

This is sometimes related to ES6 arrow functions. Since they always bind in the scope of their containing function, this isn't always what you expect. One workaround is to use normal functions to bind explicitly. 

References: 
* [react native - Getting DedicatedWorkerGlobalScope instead of Constructor - Stack Overflow](https://stackoverflow.com/questions/38070268/getting-dedicatedworkerglobalscope-instead-of-constructor)



## Plugin Quirks

### react-native-svg

Sometimes setting up this plugin doesn't edit the `project.pbxproj` file correctly, resulting in build failures. 

1. Look at a diff of the `project.pbxproj` file, and make sure the added lines aren't joined together. Some path settings may to be formatted as separate lines. 
1. You can remove all references to `libRNSVG` in the file if needs be, to remove the plugin completely. 

References: 
* https://github.com/react-native-community/react-native-svg/issues/366

