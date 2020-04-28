# Run

    npm start
    npx react-native run-android
    ... OK


# To build , We use:
    
    npm i --save react-native-swiper@nightly        
    npm install --save react-native-vector-icons
    npm install --save @react-native-community/async-storage
    npm install react-native-maps@0.26.1 --save
        - solution fixed
        android/build.gradle
        buildscript {
            ext {
                buildToolsVersion = "28.0.3"
                minSdkVersion = 16
                compileSdkVersion = 28
                targetSdkVersion = 28
                supportLibVersion = "28.0.0"  // <=== add this line
            }
            ...
        }

    sudo npm install @react-native-community/geolocation --save


# Map react

    ./android/app/ser/main/AndroidManifest.xml
    <meta-data
      android:name="com.google.android.geo.API_KEY"
      android:value="Your Google maps API Key Here"/>

    npm start --reset-cache


#Geolocalization
    ./android/app/ser/main/AndroidManifest.xml
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
