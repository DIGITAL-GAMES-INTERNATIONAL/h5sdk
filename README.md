# Storms H5SDK

Storms H5SDK its lightweight library that supposed to seamlessly bind [Storms Web App](https://play.storms.com/) and [Storms Android App](https://play.google.com/store/apps/details?id=com.storms.h5) with hosted games via postMessage protocol.

Current API CDN [https://storms.com/lib/h5Sdk/v1/h5Sdk.js](https://storms.com/lib/h5Sdk/v1/h5Sdk.js)

Recommended way using it to your game is to simply add it as third party script. 

```html
<head>
<!-- ... -->
<script type="text/javascript" src="https://storms.com/lib/h5Sdk/v1/h5Sdk.js"></script>
  <!-- ... -->
</head>
```

When added, it creates `window.H5SDK` global object that contains methods to call. 

# APIs

- `H5SDK.init()`

    On game start, send the message that game has been initialised. For now this call is optional.
    
    For example:
    ```js
    constructor() {
      // ...
      H5SDK.init();
      // ...
    }
    ```

- `H5SDK.submit({ SCORE: <value> })`

    On every game level end or when game is over. Sends message about user's current game score. 
    Where `<value>` - numeric integer value of current game score. If string or float numeric value is sent, there will be an attempt to convert to integer using `parseInt`

    For example:
    ```js
    // random method name that calls game score sreen logic 
    showGameScore() {
      // ...
      H5SDK.submit({ SCORE: 128 });
      // ...
    }
    ```
