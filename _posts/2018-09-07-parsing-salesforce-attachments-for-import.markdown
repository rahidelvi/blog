---
layout: post
current: post
navigation: True
class: post-template
author: rahi
title: Parsing Salesforce attachments for import
cover: https://i.imgur.com/PwPsLY3.jpg
date: '2018-09-07 21:41:37'
tags: tech desktop web command-line salesforce tutorial
---

I found deleting and renaming files en masse via the command line _based on a list_ super handy for a recent Salesforce data preparation task.

I was working on a Salesforce to Salesforce migration and of some 56K attachments in the legacy instance I had to isolate less than 2K attachments and prepare them for import into the new instance. I was working with a complete data export from Salesforce including all attachments.

When you extract the Salesforce data export zip files you'll see an `Attachments.csv` that lists all attachments, and an _Attachments_ directory that contains the file binaries. You may have to extract several zip files depending on the volume of attachments. I consolidated them from several zip extracts into one directory.

```bash
cp -v -a /Source/Directory/Attachments/. /Destination/Directory/Consolidated
```
<br>
Each record in the `Attachments.csv` file has a Record Id like `00P80000003BdZLEA0` and if you search for that Id in your _Attachments_ directory you'll find the actual file. You might need to add the proper file extension to view it (`docx`, `xlsx`, `pdf`, etc).

I used the `Attachments.csv` file to isolate the records (attachments) we were going to migrate. This also meant I had my list of files _I didn't need_ anymore.

I used a simple shell script to run the delete job _based on a list_ in a csv file.

My `files.csv` delete sheet had records that looked like this (no headers).

<table>
  <tr>
    <th>/Destination/Directory/Consolidated/00P80000003BdZLEA0</th>
  </tr>
</table>
<br>
This was the script I used courtesy _nos_ on [stack exchange](https://stackoverflow.com/a/5142498/1889962).

```bash
#!/bin/bash

for f in $(cat files.csv) ; do
  rm "$f"
done
```
<br>
After running the delete job the files left in the my _Consolidated_ directory were exactly the ones I needed to migrate into the new Salesforce instance.

There was just one more step.

Salesforce recommends prepping the `AttachmentsImport.csv` sheet [like this](https://help.salesforce.com/articleView?id=How-do-I-import-notes-and-attachments&language=en_US&type=1):

> For Attachments, you will need to prepare the import file with the following columns:
> - **ParentId**: ID of the object associated with the attachment
> - **Name**: The name of the attachment file
> - **Body**: The absolute path to the attachment file's location on your local drive.

The files in my _Consolidated_ directory needed to be renamed for the import.

I used another simple shell script to run the rename job, again, based on a list in a csv file.

My `filesrename.csv` sheet had records that looked like this (no headers).

<table>
  <tr>
    <th>/Destination/Directory/Consolidated/00P80000003BdZLEA0</th>
    <th>/Destination/Directory/Consolidated/UniqueFileName.xlsx</th>
  </tr>
</table>
<br>
I got some help modifying a script shared by _terdon_ on [stack exchange](https://askubuntu.com/a/438580/60869) resulting in this.

```bash
#!/bin/bash

for f in $(cat filesrename.csv) ; do
  echo $f | while IFS=, read orig new
  do
    mv $orig $new
  done
done
```
<br>
Now I had my index and files ready for import.

---

Photo by [Rich Tervet](https://unsplash.com/photos/q2GNdFmhxx4) on Unsplash
