This parses Oregon Scientific protocol v3 signals from a 433MHz receiver and sends the 
data to a MQTT server. 

The hardware uses an ESP8266 Sparkfun Thing in order to contact
wifi directly. GPIO 4 is input from an external 433MHz receiver unit


In order to compile you have to provide a local.c with this content in it:

```
const char *wifi_ssid =  "***YOUR WIFI SSID***";
const char *wifi_pass =  "***YOUR WIFI PASSWORD***";
const int mqtt_host_ip[4] = {
    /* Your MQTT server's host ip address */
};
```


MQTT topic structure is:
|osc/rain|rain total inches, don't know the time range for the total?|
|osc/rain_rate|rain rate in inches per hour|
|osc/wind_speed|average speed m/s|
|osc/wind_gust|gust speed m/s|
|osc/wind_direction|0 through 360 degrees, compass rose... however direction is quantized internally to 16 segments coming off the sensor|
|osc/temperature|celsius|
|osc/humidity|whole percent|
