# ReactNativeQuirks
A list of React Native nuances I've been discovering. 

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
* 

