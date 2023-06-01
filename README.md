# EMQX MQTT broker running on balena

This repository provides a guide on how to run EMQX, a MQTT broker, Neuron from EMQX and a MQTT random data generator with balena. 

The combination of EMQX and balena.io allows to enable MQTT messaging in IoT applications deployed on edge devices such as Raspberry Pi or Intel NUCs.

## Disclaimer

This project is for educational purposes only. Do not deploy it into your premises without understanding what you are doing. USE THE SOFTWARE AT YOUR OWN RISK. THE AUTHORS AND ALL AFFILIATES ASSUME NO RESPONSIBILITY FOR YOUR SECURITY.

We strongly recommend you to have some coding and networking knowledge. Do not hesitate to read the source code and understand the mechanism of this project or contact the authors.


## Requirements

### Hardware

* Intel devices
* USB drive
* Power supply and (optionally) ethernet cable


### Software

* A balenaCloud account ([sign up here](https://dashboard.balena-cloud.com/))
* [balenaEtcher](https://balena.io/etcher)


## Deploy

You have two options here. You can deploy this project to a new balenaCloud application in one click using the button below:

[![](https://balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/emqx-balena)

Or, you can create an application in your balenaCloud dashboard and balena push this code to it the traditional way with the [balena CLI](https://www.balena.io/docs/reference/balena-cli/).


### Try EMQX MQTT broker

[EMQX](https://www.emqx.io/) is a modern MQTT broker that not only accepts MQTT data but others such as Websockets, QUIC or LWM2M. Once the device has deployed the application successfully (EMQX, Neuron and the MQTT random data generator services) you should be able to see the balenaCloud running with these services.

![Captura de pantalla 2023-06-01 a les 19 54 40](https://github.com/mpous/emqx-balena/assets/173156/538ddae7-d9cf-43a4-a87f-b2481e404a99)

To access to the EMQX broker type your local IP address on a browser. The EMQX is mapped in the port 80. Alternatively you can use the `Public Device URL` to access to the EMQX dashboard.

![Captura de pantalla 2023-06-01 a les 10 04 04](https://github.com/mpous/emqx-balena/assets/173156/4925bd90-2d79-4d9c-9afd-45145ad10f5a)

To log in use the credentials `admin` and `public`.

![Captura de pantalla 2023-06-01 a les 20 03 49](https://github.com/mpous/emqx-balena/assets/173156/d310c09e-5d85-4af5-b7f4-147c2da9d77e)

Once logged in, you will see something similar, with 3 MQTT connections sending data to the EMQX MQTT broker. If there are not MQTT connections and you see on the balenaCloud Logs errors from the `data-generator` service, restart this service.

### Try Neuron

[Neuron](https://www.emqx.com/en/products/neuron) is a service that gets industrial data from PLCs, sensors and others. Neuron is able to collect data from Modbus TCP, Modbus Serial, OPC UA and more and it sends the collected data to northbound connections such as the MQTT broker that we have at the `emqx` service or to another MQTT broker. In this case, the main idea is to use the `emqx` MQTT broker as a single source of truth in the edge, so any data collected from Modbus TCP. **DISCLAIMER the free version of Neuron only allows to collect data from Modbus TCP**.

![Captura de pantalla 2023-06-01 a les 13 30 28](https://github.com/mpous/emqx-balena/assets/173156/eac63e85-e742-457d-b84b-0d9c6cc63da4)

To log in use the credentials `admin` and `0000`. In case the interface appears in Chinese, log in and go to the last option of the menu and the last option to change the language on the dropdown form.

![image](https://github.com/mpous/emqx-balena/assets/173156/cda927e8-6224-474d-a138-e7829aaf84b6)

![Captura de pantalla 2023-06-01 a les 20 26 11](https://github.com/mpous/emqx-balena/assets/173156/3a598f09-51db-4e9a-aaf9-7e8e52172b8e)

And then start defining the Southbound devices.

![Captura de pantalla 2023-06-01 a les 20 26 02](https://github.com/mpous/emqx-balena/assets/173156/4c0974f7-19ac-4881-bc9e-bddbeae3fb86)

And the Northbound Apps to the `emqx` service.

![Captura de pantalla 2023-06-01 a les 20 25 54](https://github.com/mpous/emqx-balena/assets/173156/5f7f911b-d992-4b26-bb94-c9e99c7edfe6)

From here it will be great to see your innovation.

## Contributing

Contributions to this project are welcome! If you encounter any issues, have suggestions, or would like to improve the integration guide, please submit a pull request or open an issue on this repository and write to the [balena forums](https://forums.balena.io).
 
