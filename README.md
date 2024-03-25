# Appliance connector

![Applicance connector render](imagesAndVideos/casing/casing_render_2.png)

## Initial idea - visible gap on the market

The history behing this device came from my experience - I used to install smart home systems and saw some market gap in integrating smart home devices which oryginally was not intended to be "smart". I have in mind devices controlled over infrared, like air condationers, TVs, home theaters, audio systems, satellite and cable boxes, projectors, controlled over serial port (RS-232), like projectors, some audio entertainment systems, video conferencing systems, surveillance camera systems, etc., finishing on most simple, controlled with dry contact, like garage and gate openers, access control systems or blinds and curtains systesm, to just name a few. Backbone of most smart home systems in the end, almost always is TCP/IP network. Proabably the most universal method between both vendor locked and open smart home systems is communication via REST API. This device main prupose was to cover this gap, allow integration of all listed devices in thoughtfully manner. 

## Similar devices

Back in 2019, when we were working on this device, already some alternatives existed. There were deivces, which adresses only part of the problem. To list a few:

### Global Cache iTach

- **Pros**: Supports various connection options, compact, compatible with many systems.
- **Cons**: Setup complexity, may not suit simple needs, separate devices for RS232 and IR, high price

### BroadLink RM Pro+

- **Pros**: Affordable, supports IR and RF 433MHz, works with major voice assistants.
- **Cons**: RF control issues reported, app usability, lack of REST API.

### Remotec AC Master ZXT-600

- **Pros**: Specialized for AC control, supports major brands, energy-efficient.
- **Cons**: Limited to AC, setup complexity with certain hubs, lack of REST API.

### Blastbot IR Blaster

- **Pros**: Smartphone and voice control, supports schedules.
- **Cons**: Cloud dependency, IR only, lack of REST API.

### Remotec ZXT-310US

- **Pros**: Z-Wave to IR for AV devices, supports learning IR codes.
- **Cons**: Focus on AV, manual configuration for uncommon devices, lack of REST API.

### Hank IR Transceiver

- **Pros**: Z-Wave Plus, IR learning, compact.
- **Cons**: AV control focus, setup technicality, lack of REST API.

### Xiaomi Universal IR Remote Controller

- **Pros**: Very affordable, wide device support, integrates with Mi Home.
- **Cons**: Wi-Fi dependency, app/setup challenges for non-Chinese speakers, lack of REST API.

### Logitech Harmony

- **Pros**: Broad device compatibility, advanced automation, supports multiple connection types.
- **Cons**: Higher cost, discontinued models may affect support, lack of REST API.



## First prototype

First prototype was rough. Designed in `Autodesk Eagle` (shortly after buying it from CadSoft). It only purpose was to get rid off breadboards, which often cause more problems than circuit itself. This devkit was an extension to `Lolin32 Lite` prototyping board. This board I would call as "it ain't much, but it honest work" and most important allowed us quick start working on the software.

![DevKit photo](imagesAndVideos/dev_kit.jpeg)


It has necessary components for testing initially agreed functionalities:
- IR leds for controlling devices
- IR receiver `PNA460XM`
- two experimental touch buttons (ESP32 has itself option for capacitive buttons support, but in the end we were unable to figure out how to make it work)
- connector for `TTTP223` based touch button module
- `WS2812B` Leds for showing status of the device
  
![DevKit schematic](imagesAndVideos/devKitSchematic.png)

## Functional requirements and UI design

At this point we more or less know how device should function, which features implement. Form of the device was not clear yet, but anyway it didn't stop us from working on software. Basic user interface was designed in `Affinity Designer`. Simple mockup of the software, not functional, but give us good base for creating user interface in web technologies.

![Applicance connector render](UIDesign/RS232.jpg)

## Software development

As the web server is running on the ESP32 itself - the webpage had to as simple and lightweight as possible. Only 4MB of storage were avaiable, so every kB was counting. Most of the images were .svg and whenever possible - were generated in css. 

ESP32 is running `ESP-IDF FreeRTOS`. Writing so advance application in plain C - especially functions like wi-fi connection, filesystem management, webserver, etc. would make the app much more complex. 


## Enclosure



## Hardware


## 
