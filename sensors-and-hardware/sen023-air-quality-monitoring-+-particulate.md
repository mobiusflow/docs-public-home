# SEN023 - Air Quality Monitoring + Particulate

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
