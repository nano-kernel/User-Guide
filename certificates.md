---
layout: docwithnav

title: X.509 Certificate Based Authentication
description: NanoIoT  X.509 Certificate based authentication for IoT devices and projects.

---
    
X.509 Certificate Based Authentication is used in Two-Way SSL connection. In this case, the certificate itself is the client's  ID, thus, Access Token is no longer needed.

Instructions below will describe how to generate a client-side certificate and connect to the server that is running MQTT over SSL.
You will need to have the public key of the server certificate in PEM format. 

#### Update keygen.properties file
 
Open the keygen.properties file, and update the values if needed:

```bash
DOMAIN_SUFFIX="$(hostname)"
ORGANIZATIONAL_UNIT=NanoIoT
ORGANIZATION=NanoIoT
CITY=San Francisco
STATE_OR_PROVINCE=CA
TWO_LETTER_COUNTRY_CODE=US

SERVER_KEYSTORE_PASSWORD=server_ks_password
SERVER_KEY_PASSWORD=server_key_password

SERVER_KEY_ALIAS="serveralias"
SERVER_FILE_PREFIX="mqttserver"
SERVER_KEYSTORE_DIR="/etc/NanoIoT/conf/"

CLIENT_KEYSTORE_PASSWORD=password
CLIENT_KEY_PASSWORD=password

CLIENT_KEY_ALIAS="clientalias"
CLIENT_FILE_PREFIX="mqttclient"
```

#### Run Client keygen script


```bash
chmod +x client.keygen.sh
./client.keygen.sh
```

The script outputs the following files:

 - **CLIENT_FILE_PREFIX.jks** - Java Keystore file with the server certificate imported
 - **CLIENT_FILE_PREFIX.nopass.pem** - Client certificate file in PEM format to be used by non-java client 
 - **CLIENT_FILE_PREFIX.pub.pem** - Client public key

#### Provision Client Public Key as Device Credentials

Go to **NanoIoT Web UI -> Devices -> Your Device -> Device Credentials**. Select **X.509 Certificate** device credentials, insert the contents of  **CLIENT_FILE_PREFIX.pub.pem** file and click save.
Alternatively, the same can be done through the REST API.

#### Run Two-Way MQTT SSL Python Client

Specify your client-side certificate and path to the public key of the server certificate.

```python
# Some code omitted

client.tls_set(ca_certs="mqttserver.pub.pem", certfile="mqttclient.nopass.pem", keyfile=None, cert_reqs=ssl.CERT_REQUIRED,
                       tls_version=ssl.PROTOCOL_TLSv1, ciphers=None);

# Some code omitted
```

**Note** Script uses **8883** MQTT port and requires paho-mqtt library that you can install using the following command: **pip install paho-mqtt**



To run Java client, import **CLIENT_FILE_PREFIX.jks** file as follows:

