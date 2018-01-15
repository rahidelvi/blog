---
layout: post
current: post
navigation: True
class: post-template
author: rahi
title: How to import an outline into MindMup
cover: https://i.imgur.com/H0zNQVl.jpg
date: '2017-02-22 01:35:38'
tags: tech web mindmup tutorial
---

[MindMup][2] is my mind mapping tool of choice.

While it’s not as pretty as other options on the market, it more than compensates in function and usability. It’s minimal, super responsive and comes with a neat set of keyboard shortcuts. Build in a little muscle memory and you’ll be manipulating ideas on the canvas with no effort. And if you’re using MindMup with Google Drive, it’s free, including real time collaboration capabilities.

Sometimes I realize the best tool for the job is a mind map after I've started an outline somewhere else like on a word processor or a slide deck. Sometimes my fellow collaborator started their outline outside a mind map. So how do you bring these kinds of outlines into MindMup?

There isn't a convenient way.

MindMup allows you to import an offline MindMup file with the `.mup` extension or a Freemind file with the `.mm` extension. You can't directly import plain text or csv files. At least not yet.

But [Freeplane][5], a fork of the Freemind project, offers a pretty convenient way of importing plain text content into a Freeplane mind map. From there it's easy to bring it into MindMup.

To pull this off, you’ll need access to a modern text editor like [Atom][3] or [Caret][4] for the editor’s multiple cursors feature, and Freeplane. You can install them on Windows, Mac and Linux.

There are 3 main steps to this workaround.

###### Step 1: Word Processor to Text Editor

We want to prepare our outline so it plays nicely with Freeplane.

To begin, copy the outline from your word processor and paste it into your text editor.

![Word Processor Outline on Text Editor Start][6]

You’ll want to treat each line as a separate node on your mind map. If the line is too long just toggle the wrap text feature off in your editor. That way the long lines show up as one line.

![Each Line is a Node][7]

To create sibling and children nodes you just tab separate lines (under a parent). And this is where your editor’s multiple cursors option really helps. To create several level 2 mind map nodes, for instance, select the start of several level 2 lines, then hit tab. Repeat the process for level 3 nodes, and so on.

![GIF Create Level 2 and Level 3 Sibling Nodes][8]

You’ll end up with something that looks like this.

![Word Processor Outline on Text Editor Done][9]

###### Step 2: Text Editor to Freeplane

This part is easy. All you really do is another copy and paste job.

Open up Freeplane on your computer and create a new mind map. You don’t need to give the root node a name because you’ll have a chance to adjust things when it’s all in MindMup.

Select everything you have in the text editor (<kbd>CTRL</kbd> + <kbd>A</kbd>), copy it to your clipboard (<kbd>CTRL</kbd> + <kbd>C</kbd>), go back to your Freeplane document, select the root node, and paste (<kbd>CTRL</kbd> + <kbd>V</kbd>).

![GIF Create Freeplane Mind Map from Text Editor][10]

Now just save the mind map in the Freemind format (with the `.mm` file extension). We’re almost done.

![Save .mm File][11]

###### Step 3: Freeplane to MindMup

To import your Freemind file into MindMup, create a new MindMup document, then click `File` > `Import` and then select the Upload tab and load the file you saved in step 2.

![Import .mm File into MindMup][12]

Now that you have the word processor content in MindMup, you can use the cut and paste or click and drag options to move your content around, and most importantly, continue to tweak and work on your outline.

---

Phew, that seems like a lot. I know.

Ideally you pick the right tool for the task early in your creative process. But if you don't, with a little bit of practice, you can learn how to pull off these steps in just a few minutes. I hope in the future MindMup developers provide users easier options of importing data into to the tool.

---

*Cover image by: [Impact Hub on Flickr](https://www.flickr.com/photos/thehub/4711501346/sizes/l/) (CC BY-SA 2.0)*


[2]: https://drive.mindmup.com/
[3]: https://atom.io/
[4]: https://chrome.google.com/webstore/detail/caret/fljalecfjciodhpcledpamjachpmelml?hl=en
[5]: https://www.freeplane.org/wiki/index.php/Main_Page
[6]: https://lh3.googleusercontent.com/URm98YRVouthxT7aoyFmKCzZDezO0Qvs32C4iEsedVdfcoJ8kn96oE8HmuDR2qf2IgZe8ghGG8toyvyP43T_YSg_clXy2IXpN3iMEMhzfY25wh5ujS0lyQwM0cAyUzuRsRappbRASpPDOA8jktXLEp3XsJjCG-MsIscFHyDemXW6G4oW2wVAMhlbPp_o_io20mlnHnUPs07rE9jnNu-pt6zzDkhDQQmlKsUpWZQ_5WmNyzDG8cfpVqhEUpE6txP4OC4pPXnh-DooVQbEEwgnVFQczkzIcWdSLeYzAI5dCZeMwlOBHus5__qHkI3lEomnG_LUSAbZCe_AFSDU_FMRL4HaXWzkNx83_Go1yFb-n7XLEm01DqLJ9Zdnc4fFNiY0PThPZ66KSSsuod7zYCBM-lpNg1NP7HIEwuniZ39hNn4vXmJloc9fTIO_JJj2QBLeOJl77tyZz2Z1vijZ_kM42d_f7I4McQAqa5BPkSVclLPNCl4HEARjPpc9qZ1XP-DJ-DsScwUNESwxosfH1ojMAxW-yOVWweTzc8difLJy3uzfsj0Oz7jPwlR2ioopbdDvZQ-F_p6Y8MEJdWjc2Rt_tQKMkF_c4RgE9wC_qPnKmzO4dGz22SD9mw=w1280-h690-no
[7]: https://lh3.googleusercontent.com/Tl0HvHQ2WRWwiqbFntoSwFSgG-qs7yMebWqBTM3mTyIdDdYBWpnazrP84dIXon2QUu9n5TujQShY3V9EUoKPMe-dkPu8qchm3mGHhFk0Fegcgob-ft7CKTj0eUsHycYVVsSMCIYwS2uBh-mZYd9N9HwZDZxX-PIbLu44k45c7j7Pc16ONa6pSV5YO7B1J93QrlaAegR7ccHQyxC0YFijO1WE0sZfEBs8BP8bm68cIF7COYfU0cPF86LBKZIthYD9aQvZsYKEDuUM6fd_bU31RNliaUUcSHCCRRf7eYYGT2EvqS8yIYUbeJ-81SeAKv74r-uG0NJHMA8BazPVrRK7JyEyZU-5DdWYT-_1zMDgyHraCP0iWLYTPb63vve_kniyWYqx-Hhzm7ykuMsELIUGerbv0PHtVgnJfGhGby1q2-rSEUKxgq-PCeLLlrpVwF7z_kmxdO1UPZkP27SoB5f0w74aKK6puWKX3BczY-Y7GARLnA7PjMPQfMHhiYW-CRhPPRmefcsDQ1CyVYSdyLn2IShG7MbND2rHBDbZwK6g-GznmG2-S9xhUhCrM5CGGt9DamKym8-Rw-ZHcu1sFLItgTma09wSV8YL4wngrbludhwB2n9DzlCZ_A=w1280-h690-no
[8]: https://lh3.googleusercontent.com/wvSCJo2VBk2GlSHv8kN3XRzMKkRF7fK155d7kt5iCW03auIi8h0JFBpg1pcZbKK09pq44m2FQ7QqasZmKIHgPInvOIsZnCIJ4xx75du3rsc7wYHPliRGtTYCuMJsl2-d-M1Kx15PSLt6zCnw6OHTJoM-HL1qZIj6Cqu98rhajYv2NqbgTY8wv2V0Ye82ukfpOMzzpTsW62rKKB2NmTflfanYqFfnMKb88OXYjLQZiKlRzEdEQVPO67b83kIM-4PSQU8rc0izfu6I7ZNVdgY8RkvvajO5BHVwQvwaFxZ3DpVA9yGly0N6bOLqU8eJmAHhk5k239WLsp32g7yQTwdbNmCtPJj3QLIf0eMgdQDMeOu16hTknZm2jx69dUKWukyqlzFafUxfOBDA9vlw4u2cESTAHJpKR_e9v3wRlg0JiMZ6b5JMiiRwcgx785tjp5SUTpPFEACoRhppMA1TWj4g-S8m6FInmixrfO-XQYdyNftVjO6KSFEJ514w_DtT_-3m6kizojYM6q0Us4n710OM3oSfam5XtM5qn0cdwpHabN0XO7dy2sK1UNMubYEqzBZokaHCJMAYVEo26YsbUQycBGIkrkBelVnEfWRlbqnBlsPhOC_bICJt2g=w1280-h690-no
[9]: https://lh3.googleusercontent.com/mSp1wIjk5mesbrsP8CuTTIa4y71rbMlmRWC1Bl3wYs1KzNzuhoPMY_bc7tsQFBZTWKzanpZNVuCsBl53Ac88-Onh5Te9gkgw6cJMWu1fx07mUH2d8NvsKYtFEFHaDYLL3mhdRdc3eWQiRH13LNWgysUkCCd0fhPtvQoUDHiAKg19MygDl51u_GiDgD7JMzOgn8vgsHiUThJeNviFHdk978pjXpMk9mRjE_opepiIRrdlEhrsCA8oiM3cvHEnMJsGuPlIK8hSd9Uj3CxGe9asq6yIbXPmz3XX4rGrih568U-IKPg_hUQmnC1yEI7g4XCUbeTWzJF6mPdQJeycG0SEsEEsgzOpFNcPIxHFhG1Bs5i2HQeZpFP_LN9hPBBVFgLj7nlgD9O7viQYkbmgusbRnGvySaHZn5xiLznZhNBz0odaWitL7_l__0HkKrzUcf_2TE38HbYgodfrHVPDgvNdcLisr-umckWtrgHjI2Oat19o2tbEesaFNzRjHdrMsuP9tE0hWngLlB6tj6JVnNWu1139VHkdZTibDza6irHn41AsSe-w9M5C7u-vtMXNeJQx9HVguTQTzg3cHDhkDnceM2LKH6kpF5o0cOScAzV2-53IzAgZIguGRA=w1273-h692-no
[10]: https://lh3.googleusercontent.com/u5WghAXGydS4hmNp8XTT2eU6OIg5pjuumVt4gOHd80eTkFAn5rRJInUX9s0NpMBPT9YuofhvoYpdJ_4v5k8-YPvqQEHKxiT4HySzY-W3vldHbNhQgdD9TV9BPM8M8T7M0DnNhnryoFRWdLqHFj05entfY0Z7FrvJfEGBiQC9ZWaHFiKsQla1RnCdkiJc44sce5PwwWl3NTIFr2-KWxudkCb42E3IXQB0-qolXcwkiVgJEWF1a8MK_CUsuWYJ2WngO3hwlYjau0aQPS4WNt453TK3ViH016_F8ZAAe6q6t8ReHvxkJbGOqUGePST8MUs_KYjNDFcfsO8PgXLbdrl3IJbRigzQ5ic7J_M2hUlIaIcfj2SnIzGU353FWAi83V2ZRyd1aYjfwXlCuVbjR-hRgul61u968l9nZwByawlJFNrGSUFEhNwdcpyU1_17RwDI4GGze87LSnbt8kwzP-obUfY4yKfIlLhNBjc1uDPBjH1oU-KgbSCvM1ar42mty4Dm60acDtNKMs11NNcDNHslLw59l5TwiCacZogl3uneB3Z1Kd1-tNmLDsDIWexUcwIvhScUVS0_U6FVH1I2198hEQy5kSEpGOxAbvlwKVMrIrwaqzOHErESUQ=w1274-h690-no
[11]: https://lh3.googleusercontent.com/8Vl8o6NtTDFlwY04EmGvlKVgUdy51grGtH54x5A8YtBEoafuwAV6J-myluRH_UDXhZNOFNwxhDbFtDJEXfVC9ZoOFeEcL3lPa-7l0cNuUd4O6I0qqyCyyYceM6IuUOX1p1DBWw9dgVSb_Zx_fq2D7-zWjQTsShsyUEl_NsRr8ppGTRVOQ4vsKul845lhyekfj05PhMa5AjAgnNlU1UHnZSjHp2UoPbYr80ziJtOU5v3QGh-rsgAY4A1w_cURUrAvTReMc4OoaPIksziK0IgCThITz8tDXKeKq-75LYvbq0cQ-ThP0VXkWlTyuCIN4vOr3M8XIpJj6Nu8DEms2MpBLuBr79d1cZ8p21ZeZWXoQjQ_9ErjTfLuEAhvgil9r_XW6R4K4-8VCeplLrmVsgeIASYCTnWjUrcjO18-UoP7uzT0eXJmt94MCuXzVzbrVmHwHIN7M_CoBWHB4zv2pPZFgwTBjOb9ZouHvvq0GOrdHfwbBJsZaPl0zxvt-kJHI32eMN5_CmcUj2zbXoq9yYzAwbyzmjnxIpfTxIa7oHcqO2Uc0CzNO3CjlGW7grvAPgcjgl2MWOJzVp4Cep2fnFnsGPhXDZRRfcp6n80qo_2ZnccV8A5Bu3LdQQ=w1274-h690-no
[12]: https://lh3.googleusercontent.com/j6gSo0j8empqd5Kizq1nmavgdVi8Z69FpDWnFYIlRqGxeIBEssEd22-_D0-b61nuY_5I09KZvFPjZsgJsefENwXjGYs9tTTeHgGlO_X6aqrfkeKeNulho7JCeLwza9k4wxCGykjjI5M_2QmenP9mxh921SF5vQa3SI0r6z-MBhrvE5yGObjib4cBxd-F0DGC8YBq5yvg4LHvQ50wUWR91FxeJPpJeuRO85y9PsnagWUWw-Z1Kr2i93TQbpXQXF0JJYNaObb6_Bn-Do1caD5cFzalTLZCaazSLGeJLwLtuBxgVz-G3oH4GSHI7L13M9p4JyEGmTRK1QCqxY9_phlcn-2RdQKy0z9CPAHi9BcCxxOdgz9d-qUCDIfRrjxH71inUVKsxWylOk2UOnYvtX18c09Oo0sVXH_C6za4tcUMwn_dGqeR2cjtU29qatQKjwWoDeKZ8jOoUdb8Pc45l2nrDwu0zNZQcNjMJt62w2UgHgPUsekuufWzNMdhDigPsuVRcljL73dmbsRXGpGHZZZ1Gj59rU6BXiMA2oFbWYr-XNuDtSbUp7tWz6ukXygdjMJdsHSf7EKZbINr13UojKYUBUAIuzzjH1EhmpQtkvD6OVBGqOKa-dcmpA=w1274-h690-no
