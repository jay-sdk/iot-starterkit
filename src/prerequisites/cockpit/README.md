# Getting started in the Cloud

## Create Device Information in Internet of Things Services Cockpit

>Previous Step [Enable Internet of Things Services](../service)

The following description of interaction steps with the IoT Service Cockpit
shows you how to create a Device Type and Message Types associated with it as well as a Device instance.

Remark: The specific values that you create in this process as well as the
specific OAuth Authorization Token for your Device instance need to be used to adapt
the [configuration file config.py](../../examples/python/iot-starterkit-for-desktop/template-config.py) for the example
applications.

* Open Internet of Things Service Cockpit
 * Press on the Go to Service icon of the Internet of Things Services subscription.
 * The Internet of Things Services Cockpit will open.
 
Further information: [`Internet of Things Services`](https://help.hana.ondemand.com/iot) > Getting Started > Accessing the Internet of Things Services Cockpit 


* Create Device Type
 * Press on Device Types tile in your Internet of Things Services Cockpit.
 * Press on the + button to add a new device type.
 * Enter a Name for the device type.
 * Press on Create to continue.

![IoT Cockpit - Device Type Example](../../../images/iot_cockpit_add_device_type.png?raw=true "IoT Cockpit - Device Type Example")

Further information: [`Internet of Things Services`](https://help.hana.ondemand.com/iot) > Internet of Things Services Cockpit > Configuring Device Type.


* Create Message Type
 * Press on Message Types tile in your Internet of Things Services Cockpit.
 * Press on the + button to add a new message type.
 * Enter a Name for the message type.
 * Select a Device Type from the dropdown list.
 * Select a Direction from the dropdownlist.
 * Enter a Name and select a Type for the first row of the Fields table.
 * Optional: Add additional Fields by pressing on the + button on the top right corner of the Fields table.
 * Press on Create to continue.

The examples in the Starter Kit use the following specific Message Types that you should also create in order to make the code working without any necessary modification:
* for the communication ```from Device```:
```
	sensor:string
	value:string
	timestamp:long
```

![IoT Cockpit - Outbound Message Type Example](../../../images/iot_cockpit_add_message_type_01.png?raw=true "IoT Cockpit - Outbound Message Type Example")

* for the communication ```to Device```:
```
	opcode:string
	operand:string
```

![IoT Cockpit - Inbound Message Example](../../../images/iot_cockpit_add_message_type_02.png?raw=true "IoT Cockpit - Inbound Message Example")

Further information: [`Internet of Things Services`](https://help.hana.ondemand.com/iot) > Internet of Things Services Cockpit > Configuring Message Type.


* Create Device
 * Press on Devices tile in your Internet of Things Services Cockpit.
 * Press on the + button to add a new device.
 * Enter a Name for the device.
 * Select the Device Type for the new device from the drop down menu.
 * Press on Create to continue.

![IoT Cockpit - Device Example](../../../images/iot_cockpit_add_device_01.png?raw=true "IoT Cockpit - Device Example")

 * You will see a pop-up window Device Token Generated including the Token ID generated for the new device.

![IoT Cockpit - OAuth Token Example](../../../images/iot_cockpit_add_device_02.png?raw=true "IoT Cockpit - OAuth Token Example")

 * Copy the generated Device Token since it is needed on the device as OAuth credential for secure communication with the services.

Further information: [`Internet of Things Services`](https://help.hana.ondemand.com/iot) > Internet of Things Services Cockpit > Configuring Device.

* Final result
 * You should now have created at least 1 Device Type with 2 associated Message Types and 1 Device instance.

![IoT Cockpit - Example Configuration](../../../images/iot_cockpit_02.png?raw=true "IoT Cockpit - Example Configuration")

### Authentication mechanisms
Communication with the HCP IoT Services is protected by 2 different authentication mechanisms.
* IoT Devices use OAuth authentication with a respective OAuth token for an individual device provided via the IoT Cockpit
* Applications that trigger interactions with devices via IoT Services or consume data provided by these use Basic Authentication with the respective credentials for the individual user of the HCP account

Respective credential usage is part of the provided source code examples.

>Next Step [Deploy the Message Management Service (MMS)](../mms)