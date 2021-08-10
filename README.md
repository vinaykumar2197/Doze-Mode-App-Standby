# Hi, I'm Vinay! 👋 

  
# Doze-Mode-App-Standby

Here we will learn about Doze Mode and App Standby in android.

# Doze-Mode
if a user leaves a device unplugged & stationary for a period of time 
with screen off. It entres into Doze Mode.

# Testing Doze Mode

Make sure your device is connected with usb.
Go to android studio open any android demo project ( or create new if you don't have one ).

Install the application on your phone and leave it active. 

Now to test doze mode we will use ADB commands. 

you need to instruct the device not to pull any power from the cable connecting it to your computer.

**adb shell dumpsys battery unplug**  

above command means you are not using your usb for charging anymore.

To exit the doze mode, run the following command :

**adb shell dumpsys deviceidle unforce**

Use below command to reactivate the device by performing the following command ( i.e. usb will again start behaving as charging point for your mobile)

**adb shell dumpsys battery reset**

| adb commands |   Description   |
| :-------- | :------- |
| `adb shell dumpsys battery unplug` | `device will not pull any power from usb cable` |
| `adb shell dumpsys deviceidle unforce` | `enters into idle mode` |
| `adb shell dumpsys battery reset` | `device will start pulling power from usb cable` |




# App Standby 
if a user has not launched or used app in long time.
app has no active foreground services/ activities and there are no pending notifications.
It entres into Doze Mode.

# Testing App Standby

Make sure your device is connected with usb.
Go to android studio open any android demo project ( or create new if you don't have one ).

Install the application on your phone and leave it active. 

Now to test App Standby mode we will use ADB commands. 

you need to instruct the device not to pull any power from the cable connecting it to your computer.

Run below commands step by step : 

| adb commands |   Description   |
| :-------- | :------- |
| `adb shell dumpsys battery unplug` | `device will not pull any power from usb cable` |
| `adb shell am set-inactive <packageName> true` | `Force the app into App Standby mode by running the following commands` |
| `adb shell am set-inactive <packageName> false` | `Simulate waking your app using the following commands` |
| `adb shell am get-inactive <packageName>` | `returns the status` |
| `adb shell dumpsys battery reset` | `device will start pulling power from usb cable` |

