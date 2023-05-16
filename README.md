# unraid-templates

Unraid Docker templates XML for CA

1. browserless.xml

browserless is a web-service that allows for remote clients to connect, drive, and execute headless work; all inside of docker. It offers first-class integrations for puppeteer, playwright, selenium's webdriver, and a slew of handy REST APIs for doing more common work.

This docker is needed for changedetection.io for Playwright content fetcher.

more read here:<br>
https://github.com/dgtlmoon/changedetection.io/wiki/Playwright-content-fetcher
https://docs.browserless.io/docs/docker-quickstart.html

Docker size about 910Mb.

add this var after install to your changedetection.io:
PLAYWRIGHT_DRIVER_URL=ws://yourIP:yourPORT/?stealth=1&--disable-web-security=true


2. UrBackup.xml
 
 UrBackup is an easy to setup Open Source client/server backup system, that through a combination of image and file backups accomplishes both data safety and a fast restoration time.
 File and image backups are made while the system is running without interrupting current processes.
 UrBackup also continuously watches folders you want backed up in order to quickly find differences to previous backups. Because of that, incremental file backups are really fast.
 Your files can be restored through the web interface, via the client or the Windows Explorer while the backups of drive volumes can be restored with a bootable CD or USB-Stick (bare metal restore).
 A web interface makes setting up your own backup server really easy.

 

https://www.urbackup.org/

https://hub.docker.com/r/uroni/urbackup-server
