[![Slack](https://img.shields.io/badge/Join-Slack-blue)](https://join.slack.com/t/openeew/shared_invite/zt-cibhc0za-XKReMPobi2DsrPusORJZVQ)
[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) 
![CCBYSA](https://img.shields.io/badge/license-CC%20BY%20SA%204-blue)


<img src="/images/logo.svg" alt="logo" width="100"/>

# OpenEEW

Let's create ***earthquake early-warning (EEW) systems*** for every seismically-vulnerable community in the world!

[OpenEEW](https://openeew.com) is an initiative by [Grillo](https://grillo.io) to democratize EEW systems throughout the world by sharing our:
* Entire archive of **unprocessed accelerometer data** from Mexico, Chile and other countries, including earthquakes records with magnitudes above 7 and recorded at different distances 
* **Algorithms for the detection and characterization of earthquakes** in real time
* **Software examples** for creating your own EEW server
* **Hardware designs and firmware** so you can build your own IoT-based seismic sensors
* **Application software** so that users can receive your alerts via mobile apps, devices and more.
* **Guidance to help with your project** including deployment of sensors, installations, and more.

If you're interested in hosting a sensor in the OpenEEW seismic network or in accessing real-time data, please send us an email at [hello@openeew.com](mailto:hello@openeew.com).

We have a well-documented [landing site for OpenEEW that](https://openeew.com) provides additional information.

## What is an Earthquake Early-Warning (EEW) ?
An earthquake early-warning (EEW) system is a set of capacities to detect and characterize a significant earthquake, estimating the distributionof shaking and distribute the information to comunities and organizations, enabling individuals to prepare and act appropriately and in sufficient time to reduce the possibility of loss and protect life. 

The alerts are send real-time to people before the shaking or the strong part arrives. However [only several governments have attempted to build EEWs](http://www.unesco.org/new/en/natural-sciences/special-themes/disaster-risk-reduction/geohazard-risk-reduction/early-warning-systems/ip-eews/) due to the incredibly high-cost of traditional seismometers, dedicated telecommunications, and bespoke software.

[Grillo](https://grillo.io) has already demonstrated that an IoT-based approach to EEW systems is not only within the reach of many global citizens, but [performs as well if not better than government-run systems](https://openeew.com/blog/eew-benchmark). 

***OpenEEW*** is a [Code and Response™ with The Linux Foundation](https://www.linuxfoundation.org/projects/code-and-response/) project that features a set of core Grillo EEW components; hardware, software and know-how, that will place effective EEWs to be within the reach of many underserved communities arond the world.

All OpenEEW projects require the following components:

- **A network of OpenEEW sensors**. You can [build your own](https://openeew.com/docs/build-sensor), [buy here](https://openeew.com/docs/buy-sensor), or use someone else's network. 
<img src="/images/openeew-sensor.svg" alt="sensor" width="200"/>

-  **A detection system running on a server**. You can find instructions for deploying your own [here](https://openeew.com/docs/deploy-detection).
<img src="/images/openeew-detection.svg" alt="detection" width="200"/>

- **A method for sending alerts**. For example, to a Twitter account, via [a mobile app](https://openeew.com/docs/build-app), or an IoT device. 
<img src="/images/openeew-alarm.svg" alt="alarm" width="200"/>

## Getting Started
Start by reading this [landing page document section](http://openeew.com/docs/read-first) which leads to tutorials, guidance and more.

## Contributing
Please read [our contributing guidelines](https://openeew.com/docs/contributing) for details of how you can get involved, and [Code of Conduct](CODE_OF_CONDUCT.md) for information about how to participate correctly.

## Authors
* **Grillo** - *Initial work* - [Grillo](https://grillo.io)

Enjoy!  Give us [feedback](https://github.com/openeew/openeew/issues) if you have suggestions on how to improve this information.

## License
This project is licensed under the Apache Software License, Version 2, unless otherwise stated.  Separate third party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1 (DCO)](https://developercertificate.org/) and the [Apache Software License, Version 2](http://www.apache.org/licenses/LICENSE-2.0.txt).

OpenEEW data on AWS is licensed under CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/).
