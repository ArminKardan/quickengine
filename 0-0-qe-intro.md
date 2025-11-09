# What is QE?
[QE](http://qepal.com) is an echosystem for having SaaS easily and rapidly.
It can build Admin Panels, Websites (With Great SEO Optimization), highly flexible, multilingual SaaS (Software as a Service) solution designed to simplify and accelerate the development of cloud-based applications. It eliminates the complexities typically associated with SaaS development, allowing developers to focus on building robust and scalable software.

---

## QE Services
What empowers QE and makes it unique are its **Services**, which are composed of various microservices that we call **Blocks**. On the QE website, we create a service, develop the Blocks that make it up, and then publish them. Our SaaS service is then ready.

### QE Service Design Rules
Every QE Developer must obey the [Design Rules](https://qepal.com/docs/0-1-design-rules.md) because of the integrity of system. 



### Service GUI Blocks:
   These blocks are used for having a web interface to control services.
   - [XWebsite](https://qepal.com/docs/3-0-xwebsite.md) For stand-alone websites and landing pages.
   - [Admin Panel](https://qepal.com/docs/2-0-adminpanel.md) For direct control of a service.


### Worker Blocks:
   These blocks are used for processing and loadbalancing heavy process on server side or on a specific device like android or deal with hardwares and electronic modules.
   - [Nodejs Worker](https://qepal.com/docs/3-0-nodejs.md) for having every process that we need. 
   - [Python Worker](https://qepal.com/docs/3-1-python.md) If there is confliction with libraries and technologies like (AI) we use python workers but it's not priority.
   - [Android Device Manager](https://qepal.com/docs/3-2-android-dm.md) We use to control devices and hardwares like Android and use it's Sensors, features, and also control MCUs and Electronic Modules.
   - [Android Nodejs Worker](https://qepal.com/docs/3-3-android-node.md): If we need to have a Nodejs to be run stable on an android device.
   - [Android Python Worker](https://qepal.com/docs/3-4-android-python.md): If we need to have a Python to be run stable on an android device.


### Nexus:
   Nexus is a realtime communication system for QE echo system and it's designed and customized to be compatible with all QE blocks. each block can communicate to another one using this system. It also provides a powerful authentication and security easily for data-transferring.

   - [Nexus Description and Examples](https://qepal.com/docs/4-nexus.md)


### Database (MongoDB):
   MongoDB is the backbone of a QE service and It's available on the Back-end and Front-end (through GAPIs) and all workers. 




