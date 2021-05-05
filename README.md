# vue-cordova-typescript-template

## Project setup
```
From root folder:
$npm install
$cd ./src-cordova/
$cordova platform add browser
$cordova platform add android
```

### Compiles and hot-reloads for development
```
From root folder:
$npm run cordova-serve-browser
$npm run cordova-serve-android
```

### Compiles and minifies for production
```
From root folder:
$npm run cordova-build-browser => build output: ./src-cordova/www
$npm run cordova-build-android => build output: ./src-cordova/platforms/android/app/build/outputs/apk/release
```

### After build
#### Sign application
Generated android apk must be signed to be installed on android device:
```
from jdk dir: keytool -genkey -v -keystore my-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias my-alias
from AndroidSDK/build-tools/version: apksigner.bat sign --ks my-key.jks --in my-app.apk
```

### Other
#### Read files from www on android device
Public files from www\ can be accessed only with http request, for exemple:
```
            var url: string = 'file:///android_asset/www/MY_FILE.txt';
            axios.get(url, { responseType: 'text' }).then(function (resp) {
                console.log("Loaded:" + resp.data);
            });
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
