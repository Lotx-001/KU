0. This fork is for all people who love Comma's Openpilot. Thanks to xx979xx, tk211x, xps-genesis, atom, hoya, moksatang, mamul, neokii, oricialworks and everyone helping me or contributing for HKGs.

1. How to Install
 - Use fork installer : Type https://opkr.tk/fork/opkr on custom URL window(Short URL. This will install OPKR branch directly.) or you can use Shane's fork installer(https://smiskol.com/fork)
 - Use a command : cd /data; mv openpilot openpilot_bak; git clone https://github.com/openpilotkr/openpilot.git -b OPKR; reboot

2. How to use(functions)
 - Device(Function Name: Explanation)
   - Driving Camera: You can preview/unview Openpilot Driving Camera.
 - Network(Function Name: Explanation)
   - HotSpot on Boot: Turned Hotspot on when boot. (reboot required)
   - Use Legacy SSH Key: Use old ssh key access(below 0.8.2). (no reboot required)
 - Toggles(Function Name: Explanation)
   - Enable Lane selector Mode: Show a button on driving screen including LaneMode/LaneLess/AUTO. AUTO mode is automatically switched by a condition of lane recongnition. (no reboot required)
   - Enable Driver Monitoring: On/Off driver monitoring for the EON without filterless IR camera or Someone cannot use front cam due to uncertain reasons.(reboot required)
   - Enable Driving Log Record: Record driving logs to Local, not happen upload to server(reboot required)
   - Enable Sending Log to Server: Enable uploader to upload to server(reboot required)
   - Use Comma Stock UI: this use original Comma's UI. Also this can be applied on driving screen in realtime(click MaxSpeed box at top-left corner). (no reboot required)
 - Software(Function Name: Explanation)
   - Check for Updates: You can confirm new commits of your fork and also you can update it.
   - Commit(Local/Remote): Commit name of local(EON) and Remote.(run once when boot in manager.py, search gitcommit.sh at the file, internet connection required)
   - Git Pull On Boot: run 'git pull' command when boot.
   - Load Preset/Save Preset: Load your Parameters or Save Your Parameters. located /data/preset1 or /data/preset2. This function can save/load your settings of Menu)
   - Parameter Init: Retrieve you Changes of Menu to initial values.
   - Git Reset: Remove your local changes and inintalize to the first status of the branch.
   - Cancel Git Pull: Move one step back if git pull is not satisfied.
   - Panda Flashing: Run Panda flashing command manually. Basically this is not necessary on normal operation.
   - Change Repo/Branch: You can install others fork/branch thru typing Git ID, Git Repository, Git Branch.
 - UserMenu(Function Name: Explanation)
   - EON AutoShutdown: At Car ignition off, the device will be shutdown after the time.
   - EON ForceShutdown: The device will be shutdown by force at offroad status anyway in the time.
   - EON Volume Control(%): set device volume manually.
   - EON Brightness Control(%): set device brightness automatically/manually.
   - EON SCR Off Timer: The screen brigntess will be dark or blank after that time on driving.
   - Brightness at SCR Off(%): If you use the function(EON SCR Off Timer), you can choose a level of the brightness.
   - EON Detach Alert Sound: None/KOR/ENG, Turn this on to notify when your car ignition off. Purpose of this, to protect your device away from Sun when you forgot.
   - Enable Battery Charging Control: battery charging control btw min and max of your setting
   - Use Auto Screen Record: Screen Record works automatically. at stop, the screen record off, at departure, the screen record on
   - Number of Recorded Files: Count of files you want to record.
   - Recording Quality: Low/Mid/High/U-High, changed the resolution and bitrate.
   - Delete All Recorded Files: /sdcard/videos
   - Delete All Driving Logs: /sdcard/realdata
   - Driver Monitoring Mode: Defalut/Unsleep, Default is Comma's. If you choose Unsleep, this will alert warning faster than Comma's one.
   - E2E EYE Threshold: I'm not sure this factor is being used at code actually.
   - Normal EYE Threshold: set the value below threshold of your face recognition.
   - Blink Threshold: I think this is important in the Driver Monitoring. Set the value below the threshold of your eyes blink recognition. Driver Monitoring camera shows the values of your face recognition, eyes and the other things. Preview 'Driver Camera' and then check the recognition value of your eye out and modify the value on Menu.
   - Navigation Select: Mappy(for Korea), Waze(for Global)
   - RUN Navigation on Boot: Run Navigation on Boot. If it runs well, will go to background after few seconds.
   - Display Date on Screen: shows the Device date
   - Display Time on Screen: shows the Device time
   - API Server: You can choose 3 servers, Retropilot, Comma, User's
   - User's API: Set this when you use own
   - Mapbox Style: Choose three styles of the Mapbox, Comma, opkr(locallized in Korea), User's, if you want to your own, Edit the file with yours(/data/params/d/MapboxStyleCustom). Make your mapbox style at https://studio.mapbox.com/. If you publish the style you can use it.

![](https://user-images.githubusercontent.com/37757984/127420744-89ca219c-8f8e-46d3-bccf-c1cb53b81bb1.png)

Table of Contents
=======================

* [What is openpilot?](#what-is-openpilot)
* [Running in a car](#running-in-a-car)
* [Running on PC](#running-on-pc)
* [Community and Contributing](#community-and-contributing)
* [User Data and comma Account](#user-data-and-comma-account)
* [Safety and Testing](#safety-and-testing)
* [Directory Structure](#directory-structure)
* [Licensing](#licensing)

---

What is openpilot?
------

[openpilot](http://github.com/commaai/openpilot) is an open source driver assistance system. Currently, openpilot performs the functions of Adaptive Cruise Control (ACC), Automated Lane Centering (ALC), Forward Collision Warning (FCW) and Lane Departure Warning (LDW) for a growing variety of [supported car makes, models and model years](docs/CARS.md). In addition, while openpilot is engaged, a camera based Driver Monitoring (DM) feature alerts distracted and asleep drivers. See more about [the vehicle integration](docs/INTEGRATION.md) and [limitations](docs/LIMITATIONS.md).

<table>
  <tr>
    <td><a href="https://www.youtube.com/watch?v=mgAbfr42oI8" title="YouTube" rel="noopener"><img src="https://i.imgur.com/kAtT6Ei.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=394rJKeh76k" title="YouTube" rel="noopener"><img src="https://i.imgur.com/lTt8cS2.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=1iNOc3cq8cs" title="YouTube" rel="noopener"><img src="https://i.imgur.com/ANnuSpe.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=Vr6NgrB-zHw" title="YouTube" rel="noopener"><img src="https://i.imgur.com/Qypanuq.png"></a></td>
  </tr>
  <tr>
    <td><a href="https://www.youtube.com/watch?v=Ug41KIKF0oo" title="YouTube" rel="noopener"><img src="https://i.imgur.com/3caZ7xM.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=NVR_CdG1FRg" title="YouTube" rel="noopener"><img src="https://i.imgur.com/bAZOwql.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=tkEvIdzdfUE" title="YouTube" rel="noopener"><img src="https://i.imgur.com/EFINEzG.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=_P-N1ewNne4" title="YouTube" rel="noopener"><img src="https://i.imgur.com/gAyAq22.png"></a></td>
  </tr>
</table>


Running in a car
------

To use openpilot in a car, you need four things
* This software. It's free and available right here.
* One of [the 140+ supported cars](docs/CARS.md). We support Honda, Toyota, Hyundai, Nissan, Kia, Chrysler, Lexus, Acura, Audi, VW, and more. If your car is not supported, but has adaptive cruise control and lane keeping assist, it's likely able to run openpilot.
* A supported device to run this software. This can be a [comma two](https://comma.ai/shop/products/two), [comma three](https://comma.ai/shop/products/three), or if you like to experiment, a [Ubuntu computer with webcams](https://github.com/commaai/openpilot/tree/master/tools/webcam).
* A way to connect to your car. With a comma two or three, you need only a [car harness](https://comma.ai/shop/products/car-harness). With an EON Gold or PC, you also need a [black panda](https://comma.ai/shop/products/panda).

We have detailed instructions for [how to install the device in a car](https://comma.ai/setup).

Running on PC
------

All of openpilot's services can run as normal on a PC, even without special hardware or a car. To develop or experiment with openpilot you can run openpilot on recorded or simulated data.

With openpilot's tools you can plot logs, replay drives and watch the full-res camera streams. See [the tools README](tools/README.md) for more information.

You can also run openpilot in simulation [with the CARLA simulator](tools/sim/README.md). This allows openpilot to drive around a virtual car on your Ubuntu machine. The whole setup should only take a few minutes, but does require a decent GPU.


Community and Contributing
------

openpilot is developed by [comma](https://comma.ai/) and by users like you. We welcome both pull requests and issues on [GitHub](http://github.com/commaai/openpilot). Bug fixes and new car ports are encouraged. Check out [the contributing docs](docs/CONTRIBUTING.md).

Documentation related to openpilot development can be found on [docs.comma.ai](https://docs.comma.ai). Information about running openpilot (e.g. FAQ, fingerprinting, troubleshooting, custom forks, community hardware) should go on the [wiki](https://github.com/commaai/openpilot/wiki).

You can add support for your car by following guides we have written for [Brand](https://blog.comma.ai/how-to-write-a-car-port-for-openpilot/) and [Model](https://blog.comma.ai/openpilot-port-guide-for-toyota-models/) ports. Generally, a car with adaptive cruise control and lane keep assist is a good candidate. [Join our Discord](https://discord.comma.ai) to discuss car ports: most car makes have a dedicated channel.

Want to get paid to work on openpilot? [comma is hiring](https://comma.ai/jobs/).

And [follow us on Twitter](https://twitter.com/comma_ai).

User Data and comma Account
------

By default, openpilot uploads the driving data to our servers. You can also access your data through [comma connect](https://connect.comma.ai/). We use your data to train better models and improve openpilot for everyone.

openpilot is open source software: the user is free to disable data collection if they wish to do so.

openpilot logs the road facing cameras, CAN, GPS, IMU, magnetometer, thermal sensors, crashes, and operating system logs.
The driver facing camera is only logged if you explicitly opt-in in settings. The microphone is not recorded.

By using openpilot, you agree to [our Privacy Policy](https://comma.ai/privacy). You understand that use of this software or its related services will generate certain types of user data, which may be logged and stored at the sole discretion of comma. By accepting this agreement, you grant an irrevocable, perpetual, worldwide right to comma for the use of this data.

Safety and Testing
----

* openpilot observes ISO26262 guidelines, see [SAFETY.md](docs/SAFETY.md) for more details.
* openpilot has software in the loop [tests](.github/workflows/selfdrive_tests.yaml) that run on every commit.
* The code enforcing the safety model lives in panda and is written in C, see [code rigor](https://github.com/commaai/panda#code-rigor) for more details.
* panda has software in the loop [safety tests](https://github.com/commaai/panda/tree/master/tests/safety).
* Internally, we have a hardware in the loop Jenkins test suite that builds and unit tests the various processes.
* panda has additional hardware in the loop [tests](https://github.com/commaai/panda/blob/master/Jenkinsfile).
* We run the latest openpilot in a testing closet containing 10 comma devices continuously replaying routes.

Directory Structure
------
    .
    ├── cereal              # The messaging spec and libs used for all logs
    ├── common              # Library like functionality we've developed here
    ├── docs                # Documentation
    ├── opendbc             # Files showing how to interpret data from cars
    ├── panda               # Code used to communicate on CAN
    ├── third_party         # External libraries
    ├── pyextra             # Extra python packages
    └── selfdrive           # Code needed to drive the car
        ├── assets          # Fonts, images, and sounds for UI
        ├── athena          # Allows communication with the app
        ├── boardd          # Daemon to talk to the board
        ├── camerad         # Driver to capture images from the camera sensors
        ├── car             # Car specific code to read states and control actuators
        ├── common          # Shared C/C++ code for the daemons
        ├── controls        # Planning and controls
        ├── debug           # Tools to help you debug and do car ports
        ├── locationd       # Precise localization and vehicle parameter estimation
        ├── logcatd         # Android logcat as a service
        ├── loggerd         # Logger and uploader of car data
        ├── modeld          # Driving and monitoring model runners
        ├── proclogd        # Logs information from proc
        ├── sensord         # IMU interface code
        ├── test            # Unit tests, system tests, and a car simulator
        └── ui              # The UI

Licensing
------

openpilot is released under the MIT license. Some parts of the software are released under other licenses as specified.

Any user of this software shall indemnify and hold harmless Comma.ai, Inc. and its directors, officers, employees, agents, stockholders, affiliates, subcontractors and customers from and against all allegations, claims, actions, suits, demands, damages, liabilities, obligations, losses, settlements, judgments, costs and expenses (including without limitation attorneys’ fees and costs) which arise out of, relate to or result from any use of this software by user.

**THIS IS ALPHA QUALITY SOFTWARE FOR RESEARCH PURPOSES ONLY. THIS IS NOT A PRODUCT.
YOU ARE RESPONSIBLE FOR COMPLYING WITH LOCAL LAWS AND REGULATIONS.
NO WARRANTY EXPRESSED OR IMPLIED.**

---

<img src="https://d1qb2nb5cznatu.cloudfront.net/startups/i/1061157-bc7e9bf3b246ece7322e6ffe653f6af8-medium_jpg.jpg?buster=1458363130" width="75"></img> <img src="https://cdn-images-1.medium.com/max/1600/1*C87EjxGeMPrkTuVRVWVg4w.png" width="225"></img>

[![openpilot tests](https://github.com/commaai/openpilot/workflows/openpilot%20tests/badge.svg?event=push)](https://github.com/commaai/openpilot/actions)
[![Total alerts](https://img.shields.io/lgtm/alerts/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:python)
[![Language grade: C/C++](https://img.shields.io/lgtm/grade/cpp/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:cpp)
[![codecov](https://codecov.io/gh/commaai/openpilot/branch/master/graph/badge.svg)](https://codecov.io/gh/commaai/openpilot)
