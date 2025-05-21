# unRAID Plugins for CA

- ## ```Mover Tuning```

This is a simple [Unraid](https://unraid.net/) plugin that will let you fine-tune the operation of the [mover](https://docs.unraid.net/unraid-os/manual/additional-settings/#mover).

- On scheduled runs of mover    
    - Only actually move file(s) if the cache drive is getting full (selectable thresholds) or/and based on files age, size, etc.
    - Optionally don't move if a parity check / rebuild is already in-progress.
    - Optionally validate input filenames to prevent attacks on the filename.
- Optional ability to completely disable the scheduled runs of mover.
- Manually executed runs of mover ("Move Now" button) or via command line ("mover start") can follow schedule rules or/and always move all files.
- Expanded functionality with numerous additional options and settings.

https://github.com/masterwishx/ca.mover.tuning<br>
https://forums.unraid.net/topic/70783-plugin-mover-tuning<br>

<br>
<br>

# unRAID Docker templates XML for CA

- ## ```browserless.xml```

browserless is a web-service that allows for remote clients to connect, drive, and execute headless work; all inside of docker. It offers first-class integrations for puppeteer, playwright, selenium's webdriver, and a slew of handy REST APIs for doing more common work.

This docker is needed for changedetection.io for Playwright content fetcher.

more read here:<br>
https://github.com/dgtlmoon/changedetection.io/wiki/Playwright-content-fetcher<br>
https://docs.browserless.io/docs/docker-quickstart.html<br>

Docker size about 910Mb.

add this var after install to your changedetection.io:
PLAYWRIGHT_DRIVER_URL=ws://yourIP:yourPORT/?stealth=1&--disable-web-security=true

- ## ```browserless-v2.xml```

browserless is a web-service that allows for remote clients to connect, drive, and execute headless work; all inside of docker. It offers first-class integrations for puppeteer, playwright, selenium's webdriver, and a slew of handy REST APIs for doing more common work.

This docker is needed for changedetection.io for Playwright content fetcher.<br>
https://github.com/browserless/browserless


- ## ```UrBackup.xml```

UrBackup is an easy to setup Open Source client/server backup system, that through a combination of image and file backups accomplishes both data safety and a fast restoration time.
File and image backups are made while the system is running without interrupting current processes.
UrBackup also continuously watches folders you want backed up in order to quickly find differences to previous backups. Because of that, incremental file backups are really fast.
Your files can be restored through the web interface, via the client or the Windows Explorer while the backups of drive volumes can be restored with a bootable CD or USB-Stick (bare metal restore).
A web interface makes setting up your own backup server really easy.

https://www.urbackup.org/<br>
https://hub.docker.com/r/uroni/urbackup-server<br>
https://github.com/uroni/urbackup_backend<br>

- ## ```GrafanaMimir.xml```

Grafana Mimir provides horizontally scalable, highly available, multi-tenant, long-term storage for Prometheus.<br>
https://github.com/grafana/mimir

- ## ```Fio-Tester.xml```

Flexible I/O Tester

Fio was originally written to save me the hassle of writing special test case programs when I wanted to test a specific workload, either for performance reasons or to find/reproduce a bug. The process of writing such a test app can be tiresome, especially if you have to do it often. Hence I needed a tool that would be able to simulate a given I/O workload without resorting to writing a tailored test case again and again.

A test work load is difficult to define, though. There can be any number of processes or threads involved, and they can each be using their own way of generating I/O. You could have someone dirtying large amounts of memory in a memory mapped file, or maybe several threads issuing reads using asynchronous I/O. fio needed to be flexible enough to simulate both of these cases, and many more.

Fio spawns a number of threads or processes doing a particular type of I/O action as specified by the user. fio takes a number of global parameters, each inherited by the thread unless otherwise parameters given to them overriding that setting is given. The typical use of fio is to write a job file matching the I/O load one wants to simulate.<br>
https://github.com/axboe/fio

- ## ```RedisInsight.xml```

RedisInsight - The GUI for Redis.

Take your productivity to the next level when developing with Redis or Redis Stack! Use RedisInsight to visualize and optimize Redis data. A powerful desktop manager, RedisInsight provides an intuitive and efficient UI for Redis and Redis Stack and supports CLI interaction in a fully-featured desktop UI client.<br>
https://redis.io/insight/

