# Lamah
This Repository fork from DroidsOnRoids

## To use or update this package
- add github.properties file in root folder.
- add username & token in file.
  username=lamah
  token=[generate_access_token](https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

## build new version from package
in root project folder:
- update version variable in build.gradle under publications.
- run.
    ```
    ./gradlew publish
    ```
some times you face error with
```
Invalid publication 'gpr': artifact file does not exist : build/libs/navigation-android.jar'
```
you can fix it rename the navigation-android$version.jar to navigation-android.jar


# Navigation SDK

When your users want to get from one location to another, don’t push them out of your application into a generic map application.
Instead, keep them engaged with your application 100% of the time with in-app turn-by-turn navigation.

The Navigation SDK for Android contains logic needed to get timed navigation instructions.

It plays well with the open source [GraphHopper server](https://github.com/graphhopper/graphhopper/tree/master/navigation) as well as the [GraphHopper Directions API](https://www.graphhopper.com/products/).

## License

[MIT License](./LICENSE)

It is 100% open source and was forked 2018 from Mapbox due to [licensing issues](https://github.com/mapbox/mapbox-navigation-android/issues/1391).

## Getting Started

If you are looking to include this inside your project, please also have a look into the
[Android example](https://github.com/graphhopper/graphhopper-navigation-example).

Add this snippet to your `build.gradle` file to use this SDK (`libandroid-navigation`):

```
implementation 'com.graphhopper.navigation:navigation-android:0.1.0'
```
