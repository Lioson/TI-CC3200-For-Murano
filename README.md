# Summary
This is a Murano demo for the TI cc3200 board. This readme guide will explain how to build and run the demo.  

![image](assets/cc3200lp.png)


# Installation and Build Guide
![image](assets/setup.JPG)

## What you need to build

* Access to this source repository to clone (git term) or download to your computer.
* Setup TI Code Composer Studio v6.0 or later in your computer.[Link - http://www.ti.com/lit/ug/swru376d/swru376d.pdf]
* Setup TI Uniflash v4.0 or later in your computer.[Link - http://www.ti.com/tool/UNIFLASH?keyMatch=cc3200%20uniflash&tisearch=Search-EN-Everything]
* A valid Murna account (Sign up in www.exosite.com)

## GETTING STARTED

### CREATE A PRODUCT IN MURANO

In this section, you will create a new Product in Murano.

1. In Murano, navigate to the Products tab
2. To add a Product, click "NEW PRODUCT."
![image](assets/thingdev_5.png)
3.In the New Product popup:
	a.Enter a name for the Product in the Name field.
	b.Select Start from scratch in the Choose starting point drop-down menu.
	c.Copy and paste the following URL into the Link to your product template field:https://raw.githubusercontent.com/exosite-garage/arduino_exosite_library/master/examples/Murano-SmartLightBulb-ThingDevBoard/product_spec_smart_lightbulb_example.yaml
		This will allow you to use a product template spec file to set up the product definition.
	d.Click "ADD."
	![image](assets/thingdev_6.png)

4.Once the Product has been created, navigate to the DEFINITION tab.

These are the resources your device will interact with. They were created automatically from the product template you selected in the previous step. In this example, the device will generally write data to the temperature, humidity, and uptime aliases, while watching the state alias for changes.
![image](assets/thingdev_7.png)

NOTE: If you did not use the template URL in the previous step, you can manually configure your product definition. From the DEFINITION tab, configure your dataport resources as specified below. Also, set the default value for state to 0 so the device has a default value it reads to know to turn the LED on or off. Click on the state resource in the DEFINITION tab and write a 0 to the value.

* alias: _temperature_, format: _float_
* alias: _humidity_, format: _float_
* alias: _uptime_, format: _integer_
* alias: _state_, format: _integer_

### FLASH AND RUN THE EXAMPLE APPLICATION

In this section, you will flash and run an example application for a connected lightbulb in CC3200-LAUNCHXL.

1. Open CCS, import 3200ExositeDemo project (The source code you have download from github), in project explore, you shall see 5 projects, if not, setup environment refer to here: [Link - http://www.ti.com/lit/ug/swru376d/swru376d.pdf]	
	![image](assets/thingdev_8.png)
	
2. Click on "3200ExositeDemo", open main.c , enter Product ID.	
	![image](assets/thingdev_9.png)
	
#### FIND YOUR PRODUCT ID:

		a. In Murano, navigate to the Products tab and select the product you just created.
		
		b. On the INFO tab, locate the Product ID and copy it.			
			![image](assets/thingdev_10.png)
			


