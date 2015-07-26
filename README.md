In order to compile you have to provide a local.c with this content in it:

```
const char *wifi_ssid =  "***YOUR WIFI SSID***";
const char *wifi_pass =  "***YOUR WIFI PASSWORD***";
const int mqtt_host_ip[4] = {
    /* Your MQTT server's host ip address */
};
```

