# LEGO® Spike Hub and the Motion Sensor

A Python snippet utilizing the LEGO Spike motion sensor, [MicroPython](https://lego.github.io/MINDSTORMS-Robot-Inventor-hub-API/), and the `get_roll_angle()` and `get_gesture()` commands.

## Sample Code

```py
from mindstorms import MSHub

hub = MSHub()

while True:

    roll = hub.motion_sensor.get_roll_angle()
    
    if roll > 45:

        pixels = '00009:00009:00009:00009:00009'

    elif roll > 10: 

        pixels = '00090:00090:00090:00090:00090'

    elif roll < -45:

        pixels = '90000:90000:90000:90000:90000'

    elif roll < -10:

        pixels = '09000:09000:09000:09000:09000'

    else:

        pixels = '00900:00900:00900:00900:00900'
    
    hub.light_matrix.show(pixels)

    if hub.left_button.is_pressed() and hub.right_button.is_pressed():

        break


hub.speaker.beep()
```

***

## Repo Resources

* [Visual Studio Code](https://code.visualstudio.com/)
* [MicroPython for LEGO Robot Inventor](https://www.lego.com/en-ca/themes/mindstorms/downloads)
* [LEGO Mindstorms](https://www.lego.com/en-ca/themes/mindstorms)
* [LEGO Mindstorms App for Mac](https://apps.apple.com/us/app/lego-mindstorms-inventor/id1515448947)
* [LEGO Mindstorms App for Android](https://play.google.com/store/apps/details?id=com.lego.retail.mindstorms)
* [LEGO Mindstorms App for Windows](https://www.microsoft.com/store/apps/9N7GN3KC2GK6)

<br>
<a href="https://codeadam.ca">
<img src="https://cdn.codeadam.ca/images@1.0.0/codeadam-logo-coloured-horizontal.png" width="200">
</a>
