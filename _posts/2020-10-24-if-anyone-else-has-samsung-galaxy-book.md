---
layout: single
title: Fix for No Sound in Headphones on Fedora 32/33
date: '2020-10-24T00:27:00.009-04:00'
author: Sonny Parlin
categories:
  - Blog
tags:
- headphones not working
- systemd
- fedora
- linux
- bash
- no sound
modified_time: '2020-10-25T00:44:25.890-04:00'
blogger_id: tag:blogger.com,1999:blog-274791723093518550.post-634707510706044153
blogger_orig_url: https://www.sparl.in/2020/10/if-anyone-else-has-samsung-galaxy-book.html
---

<p>Okay if anyone else has a Samsung Galaxy Book Flex ⍺ running Fedora 32/33 and runs into the issue of getting no sound in your headphones, I have a solution/workaround that is satisfying enough for me. First let's get the headphones working on boot.</p> <p>Create a service like so:</p>

```bash
[root@localhost ~]# cat /usr/lib/systemd/system/headphones.service
[Unit]
Description=Start headphones
After=multi-user.target

[Service]
Type=oneshot
ExecStart=/usr/local/bin/headphones

[Install]
WantedBy=basic.target
```

As you can see it makes a call to /usr/local/bin/headphones, this file looks like so:

```bash   
[root@localhost ~]# cat /usr/local/bin/headphones
#!/usr/bin/bash
/usr/bin/hda-verb /dev/snd/hwC0D0 0x1a SET_PIN_WIDGET_CONTROL 0x5
```

Make sure to make the file executable:

```bash
chmod +x /usr/local/bin/headphones
```

We still need to install acpid:

```bash
sudo dnf install acpid
```

Now create the corresponding scripts to detect when headphones have been plugged/unplugged:

```bash    
[sonnyparlin@localhost ~]$ cat /etc/acpi/events/headphone_jack
event=jack/headphone.*
action=/etc/acpi/actions/headphone.sh
```

The action points to /etc/acpi/actions/headphone.sh, which looks like so:

```bash
[sonnyparlin@localhost ~]$ cat /etc/acpi/actions/headphone.sh
#!/bin/bash
/usr/local/bin/headphones
```

Don't forget to make it executable chmod +x /etc/acpi/actions/headphone.sh

Now let's make sure it works after suspend:

```bash    
[sonnyparlin@localhost ~]$ cat /usr/lib/systemd/system-sleep/headphones.sh
#!/bin/sh
if [ "${1}" == "post" ]; then
  # Do the thing you want after suspend here, e.g.:
  hda-verb /dev/snd/hwC0D0 0x1a SET_PIN_WIDGET_CONTROL 0x5
fi
```

I'm pretty sure that's it, it took me 3 days to come up with all this and browsing various forums and solutions. The only thing I've noticed is that if the headphones are plugged in when you boot up, you may have to log in as root and manually type:

```bash
/usr/local/bin/headphones
```
And that will solve the problem. If you boot up without headphones, turn on some music then plug your headphones in, it should switch over and give you sound. I hope this helps someone.
