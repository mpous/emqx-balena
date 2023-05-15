# EMQX MQTT broker running on balena

This repository provides a guide on how to run EMQX, a MQTT broker, with balena. 

The combination of EMQX and balena.io allows to enable MQTT messaging in IoT applications deployed on edge devices such as Raspberry Pi or Intel NUCs.


## Requirements

### Hardware

* Raspberry Pi 0/2/3/4 or Intel devices
* SD card in case of the Raspberry Pi
* Power supply and (optionally) ethernet cable


### Software

* A balenaCloud account ([sign up here](https://dashboard.balena-cloud.com/))
* [balenaEtcher](https://balena.io/etcher)


## Deploy

You have two options here. You can deploy this project to a new balenaCloud application in one click using the button below:

[![](https://balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/emqx-balena)

Or, you can create an application in your balenaCloud dashboard and balena push this code to it the traditional way with the [balena CLI](https://www.balena.io/docs/reference/balena-cli/).


## Contributing

Contributions to this project are welcome! If you encounter any issues, have suggestions, or would like to improve the integration guide, please submit a pull request or open an issue on this repository and write to the [balena forums](https://forums.balena.io).


## Disclaimer

This project is for educational purposes only. Do not deploy it into your premises without understanding what you are doing. 
