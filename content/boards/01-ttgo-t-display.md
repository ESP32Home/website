---
title: "TTGO T-Display"
description: "Small dev kit with O-LED display"
date: 2020-12-25T00:00:00+09:00
draft: false
weight: 1
---
![img](/images/ttgo_t-display.png)

## Hello Wold
* [epaper-TTGO-T5_1_2-hello](https://github.com/ESP32Home/epaper-TTGO-T5_1_2-hello)

### dependencies
* [GxEPD](https://github.com/ZinggJM/GxEPD)

```ini
lib_ldf_mode = deep+
lib_deps =
    GxEPD@3.1.0
```
### Example
```c++
#include <Arduino.h>
#include <SPIFFS.h>
#include <epaper.h>

EPaper epaper;

void setup()
{
    Serial.begin(115200);
    SPIFFS.begin();
    epaper.init();
    delay(500);

    if (esp_sleep_get_wakeup_cause() == ESP_SLEEP_WAKEUP_UNDEFINED) {
        epaper.display.fillScreen(GxEPD_WHITE);
        epaper.drawBitmap("/esp_home.bmp", 0, 50, true);
        epaper.displayText("Hello simple", 20, EPaper::RIGHT_ALIGNMENT);
        epaper.display.update();
    }
}

void loop()
{
    delay(5000);
    Serial.print(".");
}
```

## Display
* IPS ST7789V
* 1,14 Zoll
* 135x240

## Suppliers
* [Aliexpress ~ 10€](https://de.aliexpress.com/item/4000829894292.html?spm=a2g0s.9042311.0.0.33794c4dbkKB4T)
