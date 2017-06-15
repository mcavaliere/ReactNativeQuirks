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
