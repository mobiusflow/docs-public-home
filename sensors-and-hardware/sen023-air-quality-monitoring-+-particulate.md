# SEN023 - Air Quality Monitoring + Particulate

## Configuration

|   | <p></p><p>The <strong>Home</strong> page has the following options:</p><ul><li><strong>Configure Network</strong> - select an upstream connection method and network settings </li><li><strong>Manage Certificates</strong> - add and remove certificates for secure TLS connections</li><li><strong>Configure Mobius</strong> - configure the connection to the MobiusFlow Gateway</li><li><strong>Set Config Mode Password</strong> - set the configuration mode WiFi password</li><li><strong>About</strong> - view information such as installed modules, network MAC addresses and, version numbers</li><li><strong>Reboot Device</strong> - reboot the Connector to apply the settings</li></ul> |
| - | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

|   | <p></p><p>The <strong>Configure Network</strong> page has the following options:</p><ul><li><strong>Select Network Type</strong> - select the upstream connection method. Options are <em>WiFi</em>, <em>Wired</em>, <em>NB-IoT</em>, or <em>LTE-M</em>. Only available options are shown. WiFi, NB-IoT, or LTE-M settings sections will become visible at the bottom of the page if you select on of these types</li><li><strong>Timeout</strong> - the connector will attempt to connect to your network and your Mobius gateway. If it is unable to connect within this time it will reboot and try again</li><li><strong>Select TCP/IP Mode</strong> - select <em>via DHCP</em> or <em>Manually</em> to choose how TCP/IP settings are configured. If you select DHCP the TCP/IP settings section below will be hidden</li><li><strong>TCP/IP Settings</strong> - this section will only be visible if you have selected to manually assign an IP address. Set the <em>IP address</em>, <em>Subnet Mask</em>, <em>Network Gateway</em> and <em>DNS Server</em>addresses for your network</li><li><strong>WiFi Settings</strong> - this section will only be visible if you have selected to WiFi Network as the connection type. Enter the <em>WiFi SSID</em> and <em>Password</em>. You can scan for networks to see a list of available WiFi networks. Choosing one from the list will populate the SSID field</li><li><strong>Save</strong> - click <em>Save</em> to save these settings</li><li><strong>Cancel</strong> - click <em>Cancel</em> to ignore any changes</li></ul> |
| - | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

## MQTT Payload

### MQTT Topic

The topic is user definable in the sensor configuration, but always starts with **iaqmp/**.&#x20;

e.g. `iaqmp/sensor1` where the sensor configuration contains **sensor1** in the MQTT topic field.

### MQTT Payload&#x20;

The MQTT payload is shown below. The **sensors** object contains the actual sensor readings and the **scores** object contains the score for each property. The scores are based on the UK DEFRA standards where 1 is bad and 5 is excellent.&#x20;

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
