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

        npx react-native run-android

    sudo npm install @react-native-community/geolocation --save

    - Login with facebook:
    npm install --save react-native-fbsdk

#Rename package
    npm install react-native-rename
    react-native-rename "MyApp" -b com.mycompany.myapp

# Map react

    ./android/app/ser/main/AndroidManifest.xml
    <meta-data
      android:name="com.google.android.geo.API_KEY"
      android:value="Your Google maps API Key Here"/>

    npx react-native run-android
    npm start --reset-cache


#Geolocalization
    ./android/app/ser/main/AndroidManifest.xml
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />

    npx react-native run-android
    npm start --reset-cache


#Facebook login :: https://github.com/facebook/react-native-fbsdk
    - Create App in:
    https://developers.facebook.com/

    ...
    3:
        Package: com.dev.food
        Name predetermi: .MainApplication  <== AndroidManifest <application android:name=".MainApplication" ...>

    - Generate a key for this app (copy generated key):

        keytool -exportcert -alias androiddebugkey -keystore ~/.android/debug.keystore | openssl sha1 -binary | openssl base64
        
            pass keys: android

    - Generate other in:

        cd android/app/
        keytool -exportcert -alias androiddebugkey -keystore debug.keystore | openssl sha1 -binary | openssl base64

            pass keys: android

    - Before, both keys paste in , Hashes de clave , and Save.

    - Abre el archivo /app/res/values/strings.xml.
        <string name="facebook_app_id">################</string> <string name="fb_login_protocol_scheme">################</string>

    - Abre el archivo /app/manifest/AndroidManifest.xml.

        <uses-permission android:name="android.permission.INTERNET"/>

        <meta-data android:name="com.facebook.sdk.ApplicationId" android:value="@string/    facebook_app_id"/> <activity android:name="com.facebook.FacebookActivity" android:configChanges= "keyboard|keyboardHidden|screenLayout|screenSize|orientation" android:label="@string/app_name" /> <activity android:name="com.facebook.CustomTabActivity" android:exported="true"> <intent-filter> <action android:name="android.intent.action.VIEW" /> <category android:name="android.intent.category.DEFAULT" /> <category android:name="android.intent.category.BROWSABLE" /> <data android:scheme="@string/fb_login_protocol_scheme" /> </intent-filter> </activity>



        