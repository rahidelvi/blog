---
layout: post
current: post
navigation: True
class: post-template
author: rahi
title: Battery level notifications for Ubuntu
cover: https://i.imgur.com/cwEAXuP.png
date: '2017-01-31 02:05:37'
tags: tech desktop command-line ubuntu experiments
---

The power manager on your laptop does an *okay* job letting you know when it needs charging. But it never tells you if it’s been plugged in for too long. The solution? A script that notifies you when it's time to either plug in or unplug your battery charger.

[Jump to the script][5].

#### Context

My laptop gets a pretty serious workout almost everyday at GrantBook, my wonderful BYOD workplace. I upgraded to a new laptop in October 2014 and by October 2016 it could barely hold a charge. Part of the problem was my battery overheated often (too many applications running), but it was also almost always plugged in. It’s super easy to forget about your battery when you’re immersed in interesting work.

I had my laptop battery replaced in October 2016, and this time I'm hoping to do a better of maintaining it.

#### Research

If you’ve done [some reading on the topic][1], you would have learnt that apart from keeping your battery cool, it’s also a good idea to keep it charged somewhere in the range of 40% to 80%. That’s supposed to be optimal. And, about once a month, it helps to discharge the battery completely.

That once a month deep discharge task is easy to remember. A recurring event in your calendar should do the job. But what about keeping your battery charged in that 40% to 80% range?

Fortunately, *KasiyA* over on Ask Ubuntu [shared a script][2] that lets you know when your battery reaches an upper or lower threshold (that you get to set).

#### Solution

Now when my laptop battery’s charge reaches 80%, I get this notification.

![Upper Limit Notification][3]

And when it drops below 40%, I see this.

![Lower Limit Notification][4]

If for some reason I miss or ignore the notification, the script puts my screen to sleep. It’s not as horrible as it sounds. It only takes a second to unlock my screen and get back to what I was doing.

##### The Script

Here’s my slightly modified version of the script. It runs when my computer starts.

```bash
#!/bin/bash

## Tutorial on battery level notifications (askubuntu.com/a/518955/60869)

    while true
    do
        export DISPLAY=:0.0
        battery_level=`acpi -b | grep -P -o '[0-9]+(?=%)'`
        if on_ac_power; then
            if [ $battery_level -ge 80 ]; then
                notify-send "Rahi, you can unplug the AC adapter. The battery is charging above 80%." "Charging: ${battery_level}% "
                sleep 40
                if on_ac_power; then
                    gnome-screensaver-command -l   ## lock the screen if you don't unplug AC adapter after 40 seconds
                fi
             fi
        else
             if [ $battery_level -le 40 ]; then
                notify-send "Rahi, time to plug in the AC adapter! Battery charge is lower than 40%." "Charging: ${battery_level}%"
                sleep 40
                if ! on_ac_power; then
                    gnome-screensaver-command -l   ## lock the screen if you don't plug AC adapter after 40 seconds
                fi
             fi
        fi

        sleep 300 # 300 seconds or 5 minutes
    done
```
---

Although I've been diligently adhering to the notifications it's still a little early to tell if it's making a difference. I’ll have to write a follow up post one day and let you know how this experiment went.

The battery heat issue is still not an easy problem to solve. I think it would require a major change in my current work habits. As for the problem of a perpetually plugged in laptop, I think I'm quite happy with the notifications approach to keeping it properly charged.

Do you have a battery maintenance strategy?


[1]: http://tab.bz/jg72t
[2]: http://askubuntu.com/a/518955/60869
[3]: https://lh3.googleusercontent.com/8ADwre1faOtOMmOIXcxrkjYaTEJyyayYNfv39zOmdvslml7TC2V6JVqWbqV_vFpG-fZn6uJ6z4kKgU5bgmwowCt8JQTmStA5GTFOBT_qieGYhH--aQoaZ8r5MY2pv3UwkpeddwR2HygQQEb46pyNPDX-tSXy_cIome8ZGezthHseBmmIP2NKej-pUwEOSwQL7zucrF6mGMTywXUHd-c3yx8r8gwc8Of2FWohBI85vWcWU5gBQDXXQzNAgV6WTsDFPevoemCWRzfgxzxj4Xt33ip4dtSeMjO2IwFeWXtz9VX8wWT2F755Huz1Gf9IJNsc9iB9vmhHjvZv9dJUub7IvcWsrl1Gj7nhqdUtxZFMLIfFpaZM-YMWdS4rpMuppdOSS8moxzgrQ0sHdgdHIBkGkMNgtzw44Un5zvTiaW6PqMJKElD6wNdiDp8M7L8dNA2wnHmfzLThHydX3931EGhXyTemP_EH7WqPO9DPQk8yZIZ_DkpNI_r5D0_JAG8lDBL1t1cVF6uoi_c0CxBR5Q3L1IR3HYrMkUqA8mMX-OYByVeVYGcsl6lMjG2KAvNH0bt2K4dNkwzu_xLV4lDlyjzqKyPJB3W1Ukj3iQerN816V5_Yljz3oVN9Lg=w351-h75-no
[4]: https://lh3.googleusercontent.com/SQwtcVNb7CWWcH28yEbcLnZf31wKE76cjSZSavQD7TTVb3FdfeSvMgkyXPNqtXKj6IZHH_wloenZve9zPUgsbK5-2kBwFfk-P11Gof7KY_rK_UCLHsH4rOJXAnlPRJ3p2IEt901ameAYSXuBfzEhaPbx1ZnO0XBAppFxZb9RJkldYTjGdndJ73-YGF_Ce6t9fPSN672Xv5LUBs8O0hSSB8IafI9XGzXXNjvCDiJJQMDOq_n4Wreyr0dOLJGYg127uhjmquwOmnHczk-6mKiEz3FTWSFedD-fWhfZ39MH7q5RRPz37C9YIxLK6_wmFgMnSyYeQ7Zx_QXgyNnaLipqfpkB64-msTweorRJKoRwvju5a3LTMHsni9ioW2rFPPqxkgxlZqxKVrWWuA-AfdTrWSGP98qV3PCuZNVZIU9t_EQ5G6YRzSP-DPf_JR51yENSsNVadbDjvqFlnriaKgA-bPWqx1Z2zYi8bSA0cKtaRIb7j6FGTXUxkc2i8Jgs4EBM7_8JKOsNRCi7z5KUORWWN5KNN40yF9f4zXTkkIQIygGe_rG6kuredARLhKxmSiFW2f6A2oe6zQJ-7ZNVWAMFUbX1sLei6fSP74jy0P5lAOs7eOVGhcU1gA=w351-h74-no
[5]: https://blog.rahidelvi.ca/battery-level-notifications-for-ubuntu/#the-script
