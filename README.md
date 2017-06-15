# ReactNativeQuirks
A list of React Native nuances I've been discovering. 

### Invisible Images

Sometimes you'll use an `<Image />` element and RN will allocate visual space for it, but the image itself will not be visible. 

There are often 2 things wrong: 

* The image needs `width` and `height` values. 
