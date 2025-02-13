# Godot Android Adjust Plugin
This is Android Adjust plugin for Godot 3.2.2 or higher.

(self checked Godot 4.1.1)

## Adjust SDK Version

4.30.0

## How to use
* On your Godot project install android build template. You can follow the [official documentation](https://docs.godotengine.org/en/latest/getting_started/workflow/export/android_custom_build.html)
* Go to Releases (on the right of this repository page) and download a released version. It is a ZIP file containing 2 files: "aar" of the plugin and "gdap" file describing it,
* Extract the contents of the released ZIP file to res://android/plugins directory of your Godot project
* On Godot platform choose: Project -> Export -> Options and make sure turn on the "Use Custom Build" and "Godot Adjust" on the "Plugins" section:
![Annotation 2020-07-24 213436](https://user-images.githubusercontent.com/3739222/88424072-9644e300-cdf5-11ea-9a1d-9d282b70550e.png)

### Permissions
```
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="com.google.android.gms.permission.AD_ID"/>
```

Maybe you need to check the permission yourself on the Export Window.

![access_network_state](https://github.com/takumifukasawa/godot-android-adjust-plugin/assets/947953/71bdbeac-7972-4993-af35-c65c1b507183)

![internet](https://github.com/takumifukasawa/godot-android-adjust-plugin/assets/947953/5bf6753d-55dd-49e4-99c3-992d83bcdd6d)


## Basic Example in Godot (GDScript)
```
    const adjust_app_token = "12345.."
    var adjust
    if (Engine.has_singleton("GodotAdjust")):
        print("Adjust was detected")
        adjust = Engine.get_singleton("GodotAdjust")
        adjust.init(adjust_app_token)
    else:
        print("Adjust was not detected")
```

## Api Reference

**Functions:**
```
init(app_token, is_production)
```
