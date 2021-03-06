---
layout: single
title: Spending my time developing bots
date: 2021-02-10T16:16:00.000-05:00
author: Sonny Parlin
categories:
- blog
tags:
- telegram
- python
- development
modified_time: 
header:
  teaser: ''

---
During the last few weeks I've been practicing up on my Python coding by creating a couple of Telegram bots. It's been a good way to keep my mind off of politics and get back to exercising the muscle between my ears. So far I've developed two bots.

## Send Help Now bot for Telegram

1. First Create a private or public group or channel, I created a private group called *Emergency*

2. Add *sendhelp_bot* as an admin to your new group or channel

3. Connect your group or channel to sendhelp_bot by typing `/add @sendhelp_bot` from your group or channel

4. Open *sendhelp_bot* in Telegram, click `/finish_setup`.

5. Now the bot is ready to use, click on `Need a Ride` to notifiy your emergency contacts that you need a ride or click
on `In Danger` to notify your emergency contacts that you're in danger. They will receive your request with your current location. Clicking
the map will open a new screen with a larger map and an option for directions, which will open up your maps app.

![](https://i.imgur.com/Rl5Td7O.png){:width="300px"}  ![](https://i.imgur.com/WdvbKbc.png){:width="300px"}  ![](https://i.imgur.com/wkQAE5Q.png){:width="300px"}  ![](https://i.imgur.com/a01WEm0.png){:width="300px"}  ![](https://i.imgur.com/T3Wlnwr.png){:width="300px"}  ![](https://i.imgur.com/mjDHIkZ.png){:width="300px"}  ![](https://i.imgur.com/XbelsVj.png){:width="300px"}  ![](https://i.imgur.com/xpRCjbW.png){:width="300px"}

<br/>
## Gist Controller bot for Telegram

This bot can interact with Github gists. You can view gists, create gists and more. In order to access your Github account through Telegram, you'll need a personal access token from Github. You can get one for free here: [https://github.com/settings/tokens/new](https://github.com/settings/tokens/new) (make sure to check the gist box). Bot developed by [@sonnygrapples](http://t.me/sonnygrapples "http://t.me/sonnygrapples"), support available at [Gist Controller bot talk](http://t.me/gistcontrollerbottalk "http://t.me/gistcontrollerbottalk").

![](/uploads/screenshot_20210210-170116.png){:width="300px"}  ![](/uploads/screenshot_20210210-170128.png){:width="300px"}   ![](/uploads/screenshot_20210210-170448.png){:width="300px"}   ![](/uploads/screenshot_20210210-170606.png){:width="300px"}

Both bots were developed using Python and the [Python Telegram Bot](https://python-telegram-bot.org/ "https://python-telegram-bot.org/") API.

