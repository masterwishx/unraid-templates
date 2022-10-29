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