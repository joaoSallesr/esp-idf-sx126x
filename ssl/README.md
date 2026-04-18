# SSL Example   
This is LoRa and SSL gateway application.   
Receive from LoRa and send to SSL Server.   
ESP32 acts as SSL Client.   

```
           +-----------+           +-----------+           +-----------+
           |           |           |           |           |           |
==(LoRa)==>|  SX126x   |--(SPI)--->|   ESP32   |--(SSL)--->| SSL Server|
           |           |           |           |           |           |
           +-----------+           +-----------+           +-----------+
```

# Installation
```
git clone https://github.com/nopnop2002/esp-idf-sx126x
cd esp-idf-sx126x/ssl/
chmod 777 mkkey.sh
./mkkey.sh
idf.py menuconfig
idf.py flash
```

# Configuration
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/9320f7eb-84ac-428e-bd22-5bc512748282" />
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/be1ca9e8-f436-4734-b3d0-ecad27afd7da" />

## WiFi Setting
Set the information of your access point.   
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/7c95615f-6637-4fba-9c57-bb4f2cc322ff" />

## Server Setting
Set the information of your SSL server.   
<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/b640de7f-46b8-4c61-a223-fc5c97012d61" />

# Start the SSL server
- C language
	```
	cd clang-tls-communication
	make
	./server
	```
	![Image](https://github.com/user-attachments/assets/e030e803-c799-4e28-91b6-c2ab1ed66a47)

- python script
	```
	cd python-tls-communication
	python3 server.py
	```
	![Image](https://github.com/user-attachments/assets/a9a0bfec-fc3f-48c8-9fd3-f27596dfa961)


