---
layout: post
current: post
navigation: True
class: post-template
author: rahi
title: Alt tab tweak for Ubuntu
cover: 'http://i.imgur.com/cnXYLIe.png'
date: '2019-09-16 07:52:00'
tags: tech ubuntu desktop tips
---

I like the Ubuntu OS. Of course there are headaches in setting some things up, that just comes with the territory. However, there are some tweaks that just make this OS too compelling. Here's a _simple want_.

If you want GNOME to only show you apps from your current desktop, set

```bash
gsettings set org.gnome.shell.app-switcher current-workspace-only true
```

- This is useful if you have multiple screens
- For me anyway

---

If you want GNOME to show you apps from all of your desktops, set

```bash
gsettings set org.gnome.shell.app-switcher current-workspace-only false
```

- This is useful in single screen environments
- Hitting `Alt` + `Tab` now will allow you to access apps from _other desktops_

The benefit? When screen real estate is low, this ☝ setting, oddly, gives me _more_ screen real estate in a fairly decluttered manner.

Seems tiny, I know. However, I'm grateful for the FOSS community that even makes this stuff possible.

---

Tip via [coder wall][1].

[1]: https://coderwall.com/p/m5mhoq/gnome-3-how-to-alt-tab-windows-on-current-workspace-only
