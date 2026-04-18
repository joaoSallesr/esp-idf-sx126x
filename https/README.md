# HTTPS Example   
This is LoRa and HTTPS gateway application.   
Receive from LoRa and send to HTTPS Server.   
ESP32 acts as HTTPS Client.   

```
           +-----------+           +-----------+            +------------+
           |           |           |           |            |            |
==(LoRa)==>|  SX126x   |--(SPI)--->|   ESP32   |--(HTTPS)-->|HTTPS Server|
           |           |           |           |            |            |
           +-----------+           +-----------+            +------------+
```

# Installation
```
git clone https://github.com/nopnop2002/esp-idf-sx126x
cd esp-idf-sx126x/https/
chmod 777 mkkey.sh
./mkkey.sh
idf.py menuconfig
idf.py flash
```

mkkey.sh creates a server certificate file.   
The server certificate file is associated with the HTTPS server's IP address.   
mkkey.sh automatically obtains the HTTPS server's IP address.   
To manually configure the HTTPS server's IP address, change it as follows:   
```
IP="192.168.0.123"
openssl req -x509 -new -nodes -key server.key -subj "/CN=${IP}" -days 10000 -out server.crt
```


# Configuration
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/b878ab55-13ca-4e23-93d1-a80d4d30bd8b" />
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/2eabcd50-df1d-44d7-ab36-3a7809d9f654" />

## WiFi Setting
Set the information of your access point.   
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/e853a239-1747-4994-a421-2f3d7a09b808" />

## Server Setting
Set the information of your HTTPS server.   
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/e562973f-9b9b-4182-88a1-8b32a2b039b6" />

# Start the HTTPS server
```
python3 https-server.py
```
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/f230ae5d-54bc-41c4-b80d-7d63b46bcc4e" />

