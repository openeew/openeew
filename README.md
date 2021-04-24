[![Slack](https://img.shields.io/badge/Join-Slack-blue)](https://join.slack.com/t/openeew/shared_invite/zt-cibhc0za-XKReMPobi2DsrPusORJZVQ)
[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) 
![CCBYSA](https://img.shields.io/badge/License-CC%20BY%20SA%204-blue)

<img src="/images/logo_2020.svg" alt="logo" width="400px"/>
OpenEEW is an open network of affordable seismic stations distributed around the world that send data to a detection system for earthquake early-warnings (EEWs). 

Traditional government-run EEWs have cost 10s millions of USD, but instead we rely on modern off-the-shelf IoT and Cloud technologies. Since 2017, Grillo has demonstrated that a cheaper IoT-based EEW can perform as well as an expensive traditional solution.

## Learn More
Please refer here for more information about the various Earthquake Early-Warnings, their evolution and the uniqueness of our open source solution.

## Get Started
To participate you need an OpenEEW seismic sensor. You can make your own PCB following these instructions, or you can buy one at directly from PCBWay.

Once you have a sensor, please refer to the Wiki for instructions on installation, provisioning, and monitoring.

## Dashboard
To view sensors and earthquake events you can visit the OpenEEW dashboard. If you have your own sensor you can sign in here and see additional information relating to your device.

## Contribute
You can contribute to OpenEEW by

- Providing Pull Requests (Features, Proof of Concepts, Language files or Fixes)
- Testing new released features and reporting issues
- Contributing missing documentation for features

Our community is active on [Slack](https://join.slack.com/t/openeew/shared_invite/zt-cibhc0za-XKReMPobi2DsrPusORJZVQ) where you can ask questions and offer suggestions. Please refer to our [Code of Conduct](https://github.com/openeew/openeew/blob/master/CODE_OF_CONDUCT.md) and [Contributing Guidelines]().

## History
OpenEEW was initiated by [Grillo](https://grillo.io) in 2019 as a means to share its growing [sensor data](https://registry.opendata.aws/grillo-openeew/) via the AWS Open Data program. In 2020, IBM and Linux Foundation joined to support the open source project and help expand it to include hardware schematics and firmware, as well as code for the detection system, dashboard and alerts.
























## What is an Earthquake Early-Warning (EEW) ?
An earthquake early-warning (EEW) system is a set of capacities to detect and characterize a significant earthquake, estimating the distribution of shaking and distribute the information to communities and organizations, enabling individuals to prepare and act appropriately and in sufficient time to reduce the possibility of loss and protect life. 

The alerts are sent in real-time to people before the shaking or the strong part arrives. However, [only some governments have attempted to build EEWs](http://www.unesco.org/new/en/natural-sciences/special-themes/disaster-risk-reduction/geohazard-risk-reduction/early-warning-systems/ip-eews/) due to the incredibly high-cost of traditional seismometers, dedicated telecommunications, and bespoke software.

[Grillo](https://grillo.io) has already demonstrated that an IoT-based approach to EEW systems is not only within the reach of many global citizens, but [performs as well if not better than some government-run systems](https://openeew.com/blog/eew-benchmark). 

***OpenEEW*** is a [Call for Code® with The Linux Foundation](https://www.linuxfoundation.org/projects/code-and-response/) project that features a set of core Grillo EEW components; hardware, software and know-how, that will place effective EEWs to be within the reach of many underserved communities around the world.

All OpenEEW projects require the following components:

- **A network of OpenEEW sensors**. You can [build your own](https://openeew.com/docs/build-sensor), [buy here](https://grillo.io/product/openeew-node/), or use someone else's network. 
<img src="/images/openeew-sensor.svg" alt="sensor" width="200"/>

-  **A detection system running on a server**. You can find instructions for deploying your own [here](https://openeew.com/docs/deploy-detection-docker).
<img src="/images/openeew-detection.svg" alt="detection" width="200"/>

- **A method for sending alerts**. For example, to a Twitter account, via [a mobile app](https://openeew.com/docs/build-app), or an IoT device. 
<img src="/images/openeew-alarm.svg" alt="alarm" width="200"/>

## Getting Started
Start by reading this [OpenEEW project website section](http://openeew.com/docs/read-first) which leads to tutorials, guidance and more.

You are also welcome to join our [Slack](https://join.slack.com/t/openeew/shared_invite/zt-cibhc0za-XKReMPobi2DsrPusORJZVQ) for getting to know the community and discussing issues in real-time, including the creation of a network for your region.

Please refer to the [Github project](https://github.com/orgs/openeew/projects) for the current roadmap.

Each individual Github repo will contain additional issues that need resolving.

## Contributing
Please read [our contributing guidelines](https://openeew.com/docs/contributing) for details of how you can get involved, and [Code of Conduct](CODE_OF_CONDUCT.md) for information about how to participate.

## Authors
* **Grillo** - *Initial work* - [Grillo](https://grillo.io)

Enjoy!  Give us [feedback](https://github.com/openeew/openeew/issues) if you have suggestions on how to improve this information.

## License
This project is licensed under the Apache Software License, Version 2, unless otherwise stated.  Separate third party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1 (DCO)](https://developercertificate.org/) and the [Apache Software License, Version 2](http://www.apache.org/licenses/LICENSE-2.0.txt).

OpenEEW data on AWS is licensed under CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/).
