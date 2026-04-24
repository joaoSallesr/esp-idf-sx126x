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

mkkey.sh creates a server certificate file.   
The server certificate file is associated with the SSL server's IP address.   
mkkey.sh automatically retrieves the IP address of the server on which the script is executed and treats that address as an SSL server.   
To manually configure the SSL server's IP address, modify the script as follows:   
```
IP="192.168.0.123"
openssl req -x509 -new -nodes -key server.key -subj "/CN=${IP}" -days 10000 -out server.crt
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
	<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/153253a2-47a8-485f-a8ff-9780526ed5e7" />

- python script
	```
	cd python-tls-communication
	python3 server.py
	```
	<img width="659" height="486" alt="Image" src="https://github.com/user-attachments/assets/577c56ea-1f9b-4a7b-9cc2-84b1ac513ee2" />

