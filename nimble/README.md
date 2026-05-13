# BLE Example   
This is LoRa and BLE gateway application.   
ESP-IDF can use either the ESP-Bluedroid host stack or the ESP-NimBLE host stack.   
The differences between the two are detailed [here](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-guides/ble/overview.html).   
This project uses the ESP-NimBLE host stack.   

```
           +------------+          +------------+          +------------+
           |            |          |            |          |            |
           | Smartphone |--(BLE)-->|   ESP32    |--(SPI)-->|   SX126x   |==(LoRa)==>
           |            |          |            |          |            |
           +------------+          +------------+          +------------+

           +------------+          +------------+          +------------+
           |            |          |            |          |            |
==(LoRa)==>|   SX126x   |--(SPI)-->|   ESP32    |--(BLE)-->| Smartphone |
           |            |          |            |          |            |
           +------------+          +------------+          +------------+
```



# Configuration
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/b0a9d188-2c81-4ad9-aba1-6f9744669a8b" />

### BLE to LoRa
Receive from BLE and send to LoRa.   
```
           +------------+          +------------+          +------------+
           |            |          |            |          |            |
           | Smartphone |--(BLE)-->|   ESP32    |--(SPI)-->|   SX126x   |==(LoRa)==>
           |            |          |            |          |            |
           +------------+          +------------+          +------------+
```

<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/9ca0e67f-cfb1-46e9-861b-f87ab743e81b" />

Communicate with Arduino Environment.   
I tested it with [this](https://github.com/nopnop2002/esp-idf-sx126x/tree/main/ArduinoCode/Ra01S-RX).   

### LoRa to BLE
Receive from LoRa and send to BLE.   
```
           +------------+          +------------+          +------------+
           |            |          |            |          |            |
==(LoRa)==>|   SX126x   |--(SPI)-->|   ESP32    |--(BLE)-->| Smartphone |
           |            |          |            |          |            |
           +------------+          +------------+          +------------+
```

<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/aa7449db-044c-4e26-a4b7-7e63706e6619" />

Communicate with Arduino Environment.   
I tested it with [this](https://github.com/nopnop2002/esp-idf-sx126x/tree/main/ArduinoCode/Ra01S-TX).   

# Android Application   
I used [this](https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal) app.   

- pair with ESP_NIMBLE_SERVER   

- Launch the app and select device  
Menu->Devices->Bluetooth LE   

- Long press the device and select the Edit menu   
![Image](https://github.com/user-attachments/assets/2d36b757-585a-4310-919c-a57f136c7f20)

- Select Custom and specify UUID   
The UUIDs are different for ESP-Bluedroid and ESP-NimBLE.   
![Image](https://github.com/user-attachments/assets/9b0f23bc-86f4-4631-81e6-1df8d876f41b)

- Connect to device   
You can communicate to UNO using android.   
![Image](https://github.com/user-attachments/assets/e84fa3b1-a0ee-4af3-a64c-695a5b383857)

# iOS Application   
[This](https://apps.apple.com/jp/app/bluetooth-v2-1-spp-setup/id6449416841) might work, but I don't have iOS so I don't know.   

# Concurrent connection
Unlike ESP-Bluedroid host stack, ESP-NimBLE host stack allows concurrent connections.   
The maximum number of simultaneous connections is specified here.   
![Image](https://github.com/user-attachments/assets/9d1e1182-ed41-4b9e-bc55-bb3c75dd4745)   
You can communicate to UNO using multiple Android devices.   
![Image](https://github.com/user-attachments/assets/4d84823a-69c4-48bf-9671-64644f048ccd)   
