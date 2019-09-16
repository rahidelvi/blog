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

Set

```bash
gsettings set org.gnome.shell.app-switcher current-workspace-only true
```

If you want GNOME to only show you apps in the current desktop

- This is useful in multiple screen environments

---

Set

```bash
gsettings set org.gnome.shell.app-switcher current-workspace-only false
```

If you want GNOME to only show you apps from all desktops

- This is useful in single screen environments
- This allows you for instance to have _many desktops_, and the `Alt` + `Tab` will allow you to access apps from _other desktops_

---

via

https://coderwall.com/p/m5mhoq/gnome-3-how-to-alt-tab-windows-on-current-workspace-only