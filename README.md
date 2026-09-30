# Panel Easy

A generic ESPHome touch panel for Home Assistant, configured through a Blueprint. Sibling project of [NSPanel Easy](https://github.com/edwardtfn/NSPanel-Easy), built on LVGL instead of Nextion.

> [!WARNING]
> Early development. Not ready for use yet.

## Supported boards

| Board                                          | Resolution | Status      |
| ---------------------------------------------- | ---------- | ----------- |
| Guition ESP32-S3-4848S040                      | 480x480    | In progress |
| Waveshare ESP32-S3-Touch-LCD-4B (Smart 86 Box) | 480x480    | Planned     |
| Espressif ESP32-S3-BOX-3                       | 320x240    | Planned     |

## Configuration

Combine one board package from `boards/` with `panel_easy.yaml`:

```yaml
substitutions:
  device_name: my-panel
  wifi_ssid: !secret wifi_ssid
  wifi_password: !secret wifi_password

packages:
  remote_package:
    url: https://github.com/edwardtfn/Panel-Easy
    ref: dev
    refresh: 300s
    files:
      - boards/guition_esp32_s3_4848s040.yaml
      - panel_easy.yaml
```
