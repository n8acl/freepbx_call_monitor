# FreePBX Missed Call Monitor
Python based notifications of missed calls to FreePBX/Asterisk to various messaging services.

---

# Description

This is a Python based script that will pull the last missed call data from the asteriskcdrdb database table on a FreePBX Server as well as check for new voicemails and send a notification with the missed call information parsed to one of the supported messaging services.

This was born out of a need to have an easy way to get notifications of a missed call or a voicemail coming into my home PBX when I was away from home.

Note that this is not solely for the use of Amateur Radio Operators, but for anyone who wants to get missed call notifications to a messaging service they use.

## Assumptions

For this script, the following is assumed

- You have an already configured FreePBX/Asterisk Server.
  - This has been run and tested on a server that has Ubuntu 20.02 Server installed and Incredible PBX 2021 installed on it.
  - If you can install Python3 on the FreePBX Server, you should be able to run this.

---

## Supported Services

This script will push a notification to the following services:

- Discord
- Telegram
- Slack
- Mattermost
- Pushover
- DAPNET (Amatuer Radio Operators Only)

---

## Use Cases
* Send a notification to your private/family Discord Server
* Send a notification to your Home Automation bot on Telegram
* Amateur Radio Operators can send notifications to their DAPNET Pager

---

## FreePBX/Asterisk Versions

Currently, this works with the following PBX Version:

|Software|Version|
|--------|-------|
|Incredible PBX|2021.01U for Ubuntu 20.04|
|FreePBX|15.0.17.55|
|Asterisk|18.6.0|

You may need to tweak the sql query to make sure it is pulling from the correct database, but this should not change often. As my PBX is updated, I will test and update this script of course.

---

## Installation/Setup Instructions

[Click here to see the installation and setup steps](https://github.com/n8acl/freepbx_call_monitor/blob/main/Installation-Setup.md). Then come back here. This is a bit of a long document, so read it all carefully.

---
## Contact
If you have questions, please feel free to reach out to me. You can reach me in one of the following ways:

- Twitter: @n8acl
- Discord: Ravendos#7364
- Mastodon: @n8acl@mastodon.radio
- E-mail: n8acl@qsl.net

Or open an issue on Github. I will respond to it, and of course you, when I can. 

If you reach out to me and have an error, please include what error you are getting and what you were doing. I may also ask you to send me certain files to look at. Otherwise just reach out to me :).

---

## Change Log
* 04/02/2022 - Release 04022022
  * Fixed issues with the Voicemail notify - Forgot to add all the other services besides Discord.
  * New for Amateur Radio Operators Only - Added Notifications to the De-centralized Amateur Paging Network (DAPNET).
  * Updates to README.md

* 03/28/2022 - Release 03282022
  * Refined query to check destination channel versus the destination extension. When using a ring group, this helps to grab the missed call to the extension
  * Added the ability to check for and notify if a new voicemail has been left. Also lets the user know the number of voicemails sitting in the inbox for that extension. This is total number, not just new voicemails.

* 01/30/2022 - Release 01302022
  * Added more supported messaging services for notifications
  * Refined the SQL query that pulls the last call data
  * Refined the way the script parses the data for missed call
  * Added Installation steps document
  * Added startbot.sh as an example to allow for launch at startup.

* 01/29/2022 - Inital Release
