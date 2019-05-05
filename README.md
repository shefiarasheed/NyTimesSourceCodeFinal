# NYTimes
NyTimes Popular

Completedfollowing 
Create API key from https://developer.nytimes.com/get-started 
and replace the key in the URL http://api.nytimes.com/svc/mostpopular/v2/viewed/{period}.json?api-key=sample-key.
This API return json response.

Done bellow things

1.Created an Android project
2.Created a recycleView with adapter to list the NY times polular
3.Set the duration as 7 in the URL
5.Created the Model class for the json response.
6.Call the API using retrofit to parse the result. 
7.Parse the Json result and display in recycleview as per requirement 
8.Used MVC pattern to develop this app.(Model view and controller strategy)
9.Implemeted Junittest. The testing implemented for checking the API key is valid or not
10.Used good Java coding pattern to implemet this app.


11.Implemented Espresso UI testing.The testing is implemeted  for validating matching the textview text values with constant String values.For testing this, 
Turn off animation on your test device, go to Settings > Developer Options and turn off all the following options under the "Drawing" section: 
Window animation scale
Transition animation scale
Animator duration scale


12.Scripts for Gradle,
Gradle Script 
######## To Build the project#####
android {
    signingConfigs {
        nytimes {
            storeFile file('C:\\Users\\admin\\Downloads\\NYTimes-master (1)\\nytimes.jks')
            storePassword 'Shefi@890'
            keyAlias = 'nytimes'
            keyPassword 'Shefi@890'
        }
    }
    compileSdkVersion 28
    buildToolsVersion "28.0.3"

    defaultConfig {
        applicationId "xebia.nytimes.popular"
        minSdkVersion 15
        targetSdkVersion 28
        versionCode 1
        versionName "1.0"

    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }

    testOptions {
        unitTests.includeAndroidResources = true
    }
    lintOptions {
        // Turns off checks for the issue IDs you specify.
        disable 'TypographyFractions','TypographyQuotes'
        enable 'RtlHardcoded','RtlCompat', 'RtlEnabled'
        check 'NewApi', 'InlinedApi'
        // If set to true, turns off analysis progress reporting by lint.
        quiet true
        // if set to true (default), stops the build if errors are found.
        abortOnError false
        // if true, only report errors.
        ignoreWarnings true
        baseline file("lint-baseline.xml")
    }
}

 To build from command line --- To run a Gradle command, you can simply use the gradlew script found in the root of your project (or gradlew.bat on Windows) followed by the name of the task you want to run. For instance, to build a debug version of your Android application, you can run ./gradlew assembleDebug from the root of your repositor & for release ./gradlew assembleRelease. In a default project setup, the resulting apk can then be found in app/build/outputs/apk/app-debug.apk

######### For Linting #########
--- lintOptions {
        // Turns off checks for the issue IDs you specify.
        disable 'TypographyFractions','TypographyQuotes'
        // Turns on checks for the issue IDs you specify. These checks are in
        enable 'RtlHardcoded','RtlCompat', 'RtlEnabled'
        check 'NewApi', 'InlinedApi'
        // If set to true, turns off analysis progress reporting by lint.
        quiet true
        // if set to true (default), stops the build if errors are found.
        abortOnError false
        // if true, only report errors.
        ignoreWarnings true
        baseline file("lint-baseline.xml")
    }----
    
To lint from command line --- gradlew lint

####### To run Instrumented unit test & code coverage ########

---apply plugin: 'java'
 
testOptions {
        unitTests.includeAndroidResources = true
    }....
 
dependencies {
     // Optional -- Mockito framework
    // Required -- JUnit 4 framework
    testImplementation 'junit:junit:4.12'
    // Optional -- Robolectric environment
    testImplementation 'androidx.test:core:1.0.0'
    testImplementation 'org.mockito:mockito-core:1.10.19'
} -----

To test from command line ---gradlew test

13.Scripts forFastline Script 

######## To Build the project#####

-----lane :slackbuild do
  gradle(task: "assembleRelease")
  slack(message: "Build Successful!")
  upload_to_slack()
end-----


command to build from commndline --- fastlane slackbuild


######### For Linting #########

-----# Allow output detail in console
pod_lib_lint(verbose: true)
// Allow warnings during pod lint
pod_lib_lint(allow_warnings: true)

command to lint from commndline  --- fastlane run pod_lib_lint------

####### To run Instrumented unit test & code coverage ########

-----lane :tests do
  gradle(task: "test")
end

command to test app from commndline  --- fastlane tests ------

14.Attached screen shot of the Application in the github repository

15.Tried to implemet the SonarQuebe library.Downloaded the library in the laptop & run the localhost by executing Startsonat.bat but unfortunatly i am getting the error.Screen shot(sunqueeeroor.png) is attached

16.Installed the Sonarqube plugin the Android studio from file -> settings->plugin(sonarplugin_studio.png).But apply plugin: 'org.sonarqube' is not working in android studio(sonarqube_plugin.png).Feel it only work in IntelliJ IDEA. I am using Android studio for development. 
