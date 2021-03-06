# SEN023 - Air Quality Monitoring + Particulate

## ![](broken-reference)Configuring the Sensor <a href="#configuring_the_connector" id="configuring_the_connector"></a>

{% hint style="info" %}
The Connector will automatically exit configuration mode and reboot after 10 minutes.
{% endhint %}

The Connector is configured using a web browser to view the configuration pages served by the Connector's onboard web server. To activate this web server press and hold the **Configuration Button** using a small pin. Release the button as soon as display on the sensor indicates that it is in configuration mode (bottom right).&#x20;

Once the Connector is in configuration mode it will create a WiFi access point. Using a mobile phone, tablet, or laptop search for a WiFi network with the same name as the Connector's serial number (the serial number can be found on a label on the side of the Connector). Enter the WiFi password if required to complete the WiFi connection.

{% hint style="danger" %}
The default configuration WiFi password is **iaconnects**. This password _should_ be changed during configuration.
{% endhint %}

Open a web browser and type **192.168.4.1** into the address bar and hit enter. The Connector configuration Home page will load.

### Home Page

| ![](<../.gitbook/assets/SEN023 - Config Home.png>) | <p>The <strong>Home</strong> page has the following options:</p><ul><li><strong>Configure Network</strong> - select an upstream connection method and network settings</li><li><strong>Manage Certificates</strong> - add and remove certificates for secure TLS connections</li><li><strong>Configure MQTT</strong> - configure the connection to the MQTT Broker</li><li><strong>Configure AQMP</strong> - configure the Air Quality Sensor</li><li><strong>Set Config Mode Password</strong> - set the configuration mode WiFi password</li><li><strong>About</strong> - view information such as installed modules, network MAC addresses and, version numbers</li><li><strong>Reboot Device</strong> - reboot the Sensor to apply the settings</li></ul> |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Configure Network Page

| ![](<../.gitbook/assets/SEN023 - Config Network.png>) | <p>The <strong>Configure Network</strong> page has the following options:</p><ul><li><strong>Select Network Type</strong> - select the upstream connection method. Options are <em>WiFi only</em></li><li><strong>Timeout</strong> - the Sensor will attempt to connect to your network and your MQTT Broker. If it is unable to connect within this time it will reboot and try again</li><li><strong>Select TCP/IP Mode</strong> - select <em>via DHCP</em> or <em>Manually</em> to choose how TCP/IP settings are configured. If you select DHCP the TCP/IP settings section below will be hidden</li><li><strong>TCP/IP Settings</strong> - this section will only be visible if you have selected to manually assign an IP address. Set the <em>IP address</em>, <em>Subnet Mask</em>, <em>Network Gateway</em> and <em>DNS Server</em>addresses for your network</li><li><strong>WiFi Settings</strong> - this section will only be visible if you have selected to WiFi Network as the connection type. Enter the <em>WiFi SSID</em> and <em>Password</em>. You can scan for networks to see a list of available WiFi networks. Choosing one from the list will populate the SSID field</li><li><strong>Save</strong> - click <em>Save</em> to save these settings</li><li><strong>Cancel</strong> - click <em>Cancel</em> to ignore any changes</li></ul> |
| ----------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Manage Certificates Page <a href="#manage_certificates_page" id="manage_certificates_page"></a>

| ![](<../.gitbook/assets/SEN023 - Config Certs.png>) | <p>The <strong>Manage Certificates</strong> page allows you to paste in certificates for TLS and has the following options:</p><ul><li><strong>CA Certificate</strong> - paste in your server's root certificate. This is required for TLS. The default CA certificate is <em>DST Root CA X3</em> which is used by MobiusFlow Virtual Cloud Gateways</li><li><strong>Client Certificate</strong> - paste in your client certificate if required</li><li><strong>Private Key</strong> - paste in your client certificate's private key if required</li><li><strong>Save</strong> - click <em>Save</em> to save these settings</li><li><strong>Cancel</strong> - click <em>Cancel</em> to ignore any changes</li></ul><p><strong>Note:</strong> private keys with a passphrase are not currently supported</p> |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

### Configure MQTT Page <a href="#configure_mobius_page" id="configure_mobius_page"></a>

| ![](<../.gitbook/assets/SEN023 - Config MQTT.png>) | <p>The <strong>Configure MQTT</strong> page is used to setup the connection between the Sensor and an MQTT Broker. It has the following options:</p><ul><li><strong>Topic</strong> - the MQTT topic used by the sensor.</li><li><strong>Addr / URL</strong> - the <em>TCP/IP Address</em> or <em>URL</em> of the Broker</li><li><strong>Port</strong> - the <em>TCP/IP Port</em> of the Broker</li><li><strong>Username</strong> - The MQTT Broker username</li><li><strong>Password</strong> - The MQTT Broker password</li><li><strong>Security</strong> - select whether TLS and Client Certificates should be used. Before selecting these options ensure that you have added the relevant certificates</li><li><strong>Save</strong> - click <em>Save</em> to save these settings</li><li><strong>Cancel</strong> - click <em>Cancel</em> to ignore any changes</li></ul> |
| -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

### Configure AQMP Sensor Page

| ![](<../.gitbook/assets/SEN023 - Config Sensor.png>) | <p>The <strong>Configure AQMP</strong> sensor page is used to adjust calibration offsets, target temperature and enter description and location information fo the sensor</p><ul><li><strong>Target Temperature</strong> - this is used as the ideal temperature when calculating the score for the temperature</li><li><strong>Temperature Offset</strong> - the temperature calibration offset</li><li><strong>Humidity Offset</strong> - the humidity calibration offset</li><li><strong>CO2 Offset</strong> - the CO2 calibration offset</li><li><strong>Description</strong> - the sensor description</li><li><strong>Location</strong> - the sensor location</li></ul> |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Set Config Mode Password Page <a href="#set_config_mode_password_page" id="set_config_mode_password_page"></a>

| ![](<../.gitbook/assets/SEN023 - Config Password.png>) | <p>The <strong>Set Config Mode Password</strong> page allows you change the configuration mode WiFi password.</p><p>Enter a new password and confirm it. The password must be at least 8 characters long.</p><p>Click <strong>Save</strong> to update the password or <strong>Cancel</strong> to ignore any changes</p><p><strong>Note:</strong> It is not possible to recover this password if you forget it. You will have to perform a factory reset</p> |
| ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### About Page <a href="#about_page" id="about_page"></a>

| ![](<../.gitbook/assets/SEN023 - Config About.png>) | <p>The <strong>About</strong> page shows details such as the MAC Addresses of the network interfaces.</p><p>Click <strong>Update Firmware</strong> to update the connector's firmware</p> |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Factory Reset <a href="#factory_reset" id="factory_reset"></a>

It is possible to factory reset a Sensor. This will clear all settings including the configuration mode WiFi password.

To reset the Connector, hold in the **Configuration Button** for 6 seconds.

## MQTT Payload

### MQTT Topic

The topic is user definable in the sensor configuration

### MQTT Payload

The MQTT payload is shown below. The **sensors** object contains the actual sensor readings and the **scores** object contains the score for each property. The scores are based on the UK DEFRA standards where 1 is bad and 5 is excellent.

The **description** and **location** fields are free text which can be set in the sensor configuration.

```
{
  sensors: {
    temperature: <number>,
    humidity: <number>,
    co2: <number>,
    tvoc: : <number>,
    tvoc_mgPerM3: <number>,
    pm10_nc: <number>,
    pm25_nc: <number>,
    pm40_nc: <number>,
    pm100_nc: <number>,
    pm10_mc: <number>,
    pm25_mc: <number>,
    pm40_mc: <number>,
    pm100_mc: <number>,
    typpartsize: <number>,
  },
  scores: {
    temperature: <number - 0 to 5>,
    humidity: <number - 0 to 5>,
    co2: <number - 0 to 5>,
    tvoc: <number - 0 to 5>,
    pm25: <number - 0 to 5>,
    total: <number - 0 to 25>,
  },
  description: <string>,
  location: <string>
} 
```
