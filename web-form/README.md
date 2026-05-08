# Web Form Example   
Data entered through the web form is sent to LoRa.   
Data received from LoRa is displayed in a web form.   
```
           +-----------+              +-----------+              +-----------+
           |           |              |           |              |           |
           |  WebForm  |-(WebSocket)->|   ESP32   |----(SPI)---->|  SX126x   |==(LoRa)==>
           |           |              |           |              |           |
           +-----------+              +-----------+              +-----------+

           +-----------+              +-----------+              +-----------+
           |           |              |           |              |           |
==(LoRa)==>|  SX126x   |----(SPI)---->|   ESP32   |-(WebSocket)->|  WebForm  |
           |           |              |           |              |           |
           +-----------+              +-----------+              +-----------+
```

I used [this](https://github.com/Molorius/esp32-websocket) component.   
This component can communicate directly with the browser.   
It's a great job.   

# Configuration
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/45a3cfaf-200b-4740-b4b8-5ef5107ff8da" />   
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/1a72ee18-a18a-4c8e-9fc4-2612622a310f" />   

## WiFi Setting
Set the information of your access point.   
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/12e1e0ef-6b22-42d6-b2b8-3ebfffec4b71" />

## Radio Setting
Set the wireless communication direction.   

### Web to LoRa
Data entered through the web form is sent to LoRa.   
```
           +-----------+              +-----------+              +-----------+
           |           |              |           |              |           |
           |  WebForm  |-(WebSocket)->|   ESP32   |----(SPI)---->|  SX126x   |==(LoRa)==>
           |           |              |           |              |           |
           +-----------+              +-----------+              +-----------+
```

<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/39da732e-e1d1-400b-a87f-18624c493f41" />


### LoRa to Web
Data received from LoRa is displayed in a web form.   

```
           +-----------+              +-----------+              +-----------+
           |           |              |           |              |           |
==(LoRa)==>|  SX126x   |----(SPI)---->|   ESP32   |-(WebSocket)->|  WebForm  |
           |           |              |           |              |           |
           +-----------+              +-----------+              +-----------+
```

<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/1ad7b03e-cc87-4968-aaa1-8902c8f64e41" />


# Launch a web browser
Enter the following in the address bar of your web browser.   
```
http:://{IP of ESP32}/
or
http://esp32-server.local/
```

<img width="901" height="890" alt="Image" src="https://github.com/user-attachments/assets/47aa7958-37f7-4b88-999b-772149040c51" />
<img width="901" height="890" alt="Image" src="https://github.com/user-attachments/assets/ba24f64c-a8a5-4f20-943d-de25b112472b" />

### Web to LoRa
Enter the data to send in the TextBox and press the Send button.   
<img width="901" height="890" alt="Image" src="https://github.com/user-attachments/assets/de182cd8-9fea-44c1-ab35-fe7e4647467a" />

### LoRa to Web
The received data will be displayed in the TextBox.   
The Change button changes the number of lines displayed.   
The Copy button copies the received data to the clipboard.   
<img width="901" height="890" alt="Image" src="https://github.com/user-attachments/assets/c5d86191-1ac5-4f5a-9a0a-8020835ad005" />
<img width="901" height="890" alt="Image" src="https://github.com/user-attachments/assets/39ec53cc-a874-4c82-a9f3-48f6816daa59" />

# WEB Pages
WEB Pages are stored in the html folder.   
I used [this](https://bulma.io/) open source css.   
You can change root.html as you like.   


