---
layout: post
current: post
navigation: True
class: post-template
author: rahi
title: Battery level notifications for Ubuntu
cover: https://i.imgur.com/cwEAXuP.png
date: '2020-03-25 03:42:55'
tags: tech soul desktop command-line ubuntu experiments
---

Subhan'allah! [Thank you dear God][🌦]. We are to You, ...

... [and to You we are returning][🐺]. This post was updated "this day", as my little munchkin Claire calls it. Almost not calling today "this day" anymore. What a joy? "This day". Also, kindly note, the read time in the html on the blog home needs to be debugged. Zee issue?

> I used [Meld](https://meldmerge.org/) when I was [tinkering](https://blog.rahidelvi.ca/credits) sometime in 2019.

And..., the read time is misleading if you follow the links on this page. Not 3 mins, for sure.

Also, Tom I'd rather be writing guy at Amazon recently said updating blog posts is a good idea. Al'hamdulilah. May God reward him with good. _And_, this post was formerly gregorian dated `date: '2017-01-31 02:05:37'` or `170131` or _Jan 31, 2017_.

### Onward to the main show

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

![Subhan'allah, dear Allah..., you are lovely](https://i.imgur.com/HnHolx6.jpg)

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

[🌦]: https://i.imgur.com/FEnpvTM.png
[🐺]: https://listed.to/p/CuGZEwVpeE
[1]: http://tab.bz/jg72t
[2]: http://askubuntu.com/a/518955/60869
[3]: https://i.imgur.com/c2W40BX.png
[4]: https://i.imgur.com/qsUZmmj.png
[5]: https://blog.rahidelvi.ca/battery-level-notifications-for-ubuntu/#the-script
