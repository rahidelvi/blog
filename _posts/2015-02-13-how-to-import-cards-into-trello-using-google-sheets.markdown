---
layout: post
current: post
cover: https://i.imgur.com/FQxzkGK.png
navigation: True
title: How to import cards into Trello using Google Sheets
date: '2015-02-13 20:12:09'
tags: tech web extensions trello tutorial
class: post-template
author: rahi
---

Is it possible to import cards into Trello from a spreadsheet, complete with card descriptions and members assigned? Yes, and here's how to do just that.

This approach uses Trello's handy email to board feature.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IFK1Sap2dBA" frameborder="0" allowfullscreen></iframe>

#### Ingredients:

- A Trello board to work with
- The email address of the list you want to import to
- A Google Sheet
- The [Yet Another Mail Merge](https://chrome.google.com/webstore/detail/yet-another-mail-merge/mgmgmhkohaenhokbdnlpcljckbhpbmef?hl=en) (YAMM) add-on for Google Sheets
- Gmail

#### Directions:

To get started, head into the settings of your Trello board and copy the email address for the list you want to import your cards to.

Next, create a new Google Sheet with the following columns starting with `email`, `title`, `members` and `description`.

Under the `email` header paste the email address you copied from Trello earlier. You'll want to fill that down for as many cards are you plan to import.

Each row on the sheet will import into Trello as a new card. Next, fill in as many rows on the sheet as you need. Under the `members` header you only need to enter the `@username` of the person you want the card assigned to. Of course, the person has to be a member of the board to begin with.

Alright, once you've got all of this done, from your Google Sheet click Add-ons and search for Yet Another Mail Merge. Install it and authorize it to connect with your Google Account. Before heading to Gmail, copy the `title`, `members` and `description` headers to your clipboard.

In Gmail, compose a new message. Hit <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>v</kbd> to paste the plain text into the body of your email. Now, wrap the headers with two angle brackets on either side. Like this, `<<title>>`, `<<members>>` and `<<description>>`.

Select `<<title>>` and `<<members>>` and drag it to the subject line of your Draft message. Your email should look like this.

![YAMM Gmail Draft][1]

Now, let's head back to our Google Sheet and start the Mail Merge. Click Add-ons, YAMM and Start Mail Merge.

Give it a couple of moments before you start seeing the cards trickle into Trello.

#### Caveats:

1. YAMM allows you to send up to 100 emails a day. That means you can import 100 cards into Trello for free. If you need more, consider supporting the developer for a higher send limit.

2. The order in which you list your rows for your Trello cards isn't preserved.  I'd be well out of my depth if I tried to explain it. Suffice to say, don't get attached to the order in which your cards appear, or be prepared to reorder them if needed.

3. Lastly, things change and so this approach may not work at anytime. Google might update their API for Google Sheets or Gmail, Trello might do something at their end and its possible the YAMM add-on may not be maintained. It might break is what I'm saying. Hopefully it doesn't.

[1]:https://lh3.googleusercontent.com/Nnoe-GkOfJ-qWCbj9G72BoDLZ100Y-V03OXjuaJcrZLb3xCesL6zFCKL5S6e0CV027fLrBxt-m69v5-NExWbeyrwyBaXyoGMBEToWTW56GeoTkWOMnHxyh5MEg92ZubaRUqMYuAPWtm7teZQcJi_ZUSmxMWa6_7mm3ydRcRk1NOkdfx7hf7Lcc5V0v9tWeJ7d0VfvnC1d6mhD7sFDqhPRwoZLOm6FvL0IzFB-MjhmDgfxp-JVCyVhYX2rnXVXc5OC1SIRc2yGweTnNuKTB7FKRovpxzln2Ve6Nk1eXQuGzDKoel2CYEfzATEOr9ZGQK3wug0N_C0bzXkc2k9UTXVzPCxIWxPwFtQU7DqhCmGIEmy6LcPGwY_ZWi3vM1RUuGlI_7PIN0NIwHj8dMCL8MM67yjlJ9k379UyOS63qU2MWz2wMmhw0fdV8GI5398j_ZKV3bymavEhaBvnaZSzMARwcEvzPsbuSW0l3FLwsfcncQRFgXZ2VCyTEAXN6CSnRIT5rdC2YAzD4les62T3bP-fiM202naPhUu02c4unrBpegNwrIyk509gHr04-A-S_VvIN6x4gxjm5dGRhMP62ymWYuT7s3c1_pFIQApOdJsWy2KlxPhDWyx_Q=w510-h469-no
