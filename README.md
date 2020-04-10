# Selenium_grid_docker
This repo use docker images to run selenium tests on grid.
It also uses chrome and firefox docker images to run the test.

## docker images
docker images can be downloaded from [SeleniumHQ](https://github.com/SeleniumHQ/docker-selenium)

below images needs to be downloaded
- **selenium/hub:** Image for running a Grid Hub
- **selenium/node-chrome-debug:** Grid Node with Chrome installed and runs a VNC server, needs to be connected to a Grid Hub
- **selenium/node-firefox-debug:** Grid Node with Firefox installed and runs a VNC server, needs to be connected to a Grid Hub

docker commands to initiate the hub and link chrome and firefox
```
docker run -d -p 4545:4444 --name selenium-hub selenium/hub
docker run -d -p --link selenium-hum:hub selenium/node-firefox-debug
docker run -d -P --link selenium-hub:hub selenium/node-chrome-debug
```

