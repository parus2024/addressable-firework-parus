# addressable-firework-parus: Addressable LED Strip Effect for ESPHome

Fireworks‑Parus — a fireworks (salute) effect for addressable LED strips in ESPHome  
![ESPHome Logo](esphome1.png) ![Home Assistant Logo](https://avatars.githubusercontent.com/u/13844975?s=200&v=4)  
![appearance](addressable-firework-parus.jpg)  

<p align="center">  
    <img alt="Static Badge" src="https://img.shields.io/badge/made%20by-ParusSmartHome-blue">  
    <img alt="Static Badge" src="https://img.shields.io/badge/version-v2.0%20Beta-green">  
    <img alt="Static Badge" src="https://img.shields.io/badge/esphome min version-2025.7.5-red">  
    <img alt="Static Badge" src="https://img.shields.io/badge/license-MIT-orange">  
</p>

## 🌟 Project Description

**A fireworks (salute) effect for addressable LED strips in ESPHome**

The effect simulates a fireworks explosion on a one‑dimensional LED strip:  
- The main rocket ascends with acceleration, slowing down under the influence of "gravity".  
- At a preset height, an explosion occurs with gradual emission of sparks.  
- Sparks scatter upward/downward, leave colored trails, and fade out smoothly.  
- Feature: all key parameters are controlled via sliders, allowing fine‑tuning of the effect’s dynamics and appearance.

**Key Features**

***Customization Options***

The effect responds to three sliders:

*effect_speed (0–255)*  
- Increases the rocket’s initial speed.  
- Boosts the sparks’ scattering speed.  
- Shortens the sparks’ fade‑out time (the faster the setting, the shorter the trail).  

*effect_intensity (0–255, inverted)*  
- Increases the number of sparks during the explosion.  
- Decreases the length of spark heads and tails (intense explosion = many small sparks).  
- Shortens the main rocket’s head length.  

*effect_scale (0–100)*  
- Optionally adjusts the "gravity force" (free‑fall acceleration).  
- Allows making the rocket’s flight smoother or more abrupt.  

The project is based on ESP8266 or ESP32.  
Strip type: any addressable strip (WS2812B, SK6812, etc.).  


---

## 🛠️ Key Functions

**Rocket Ascent:**  
- Initial speed: 1.5–4.0 px/step.  
- Gravity: –0.02…–0.04 px/step².  
- Rocket head: 1–3 pixels.  
- Rocket tail: smooth fade‑out (8 pixels).  

**Explosion and Sparks:**  
- Number of sparks: 4–35 units.  
- Scattering speed: 1.0–2.5 px/step.  
- Spark head length: 1–3 pixels.  
- Spark tail length: 4–12 pixels.  
- Fade‑out time: 1.5–5.0 sec.  
- Spark colors: random palette (6 variants).  


---

### Software Dependencies  
- **ESPHome**: Version 2024+.  

---

## 📋 Installation and Setup

### 3. ESPHome Configuration  
- Insert the code from the project file into your main ESPHome file as an `addressable_lambda:` effect, or via include.

## 🔧 Advanced Configuration

### Sliders for Control and Customization
Add the sliders `effect_speed`, `effect_scale`, `effect_intensity` to your ESPHome configuration.  
Insert the code into the `addressable_lambda` block.  
Configure `led_count` (number of LEDs) in your setup.  
Adjust the effect via the web interface (e.g., ESPHome Dashboard).


```yaml
number:
  # Effect Settings
  - platform: template
    name: Effect Intensity
    icon: mdi:spotlight
    min_value: 0
    max_value: 255
    step: 1
    optimistic: true
    id: effect_intensity
    initial_value: 128
    mode: slider
  - platform: template
    name: Effect Speed
    icon: mdi:speedometer
    min_value: 0
    max_value: 255
    step: 1
    optimistic: true
    id: effect_speed
    initial_value: 128
    mode: slider
  - platform: template
    name: Effect Scale
    icon: mdi:drag-variant
    min_value: 0
    max_value: 100
    step: 1
    optimistic: true
    id: effect_scale
    initial_value: 50
    mode: slider
```

---

## 📊 Screenshots and Videos

- [YAML firmware file](addressable_firework_parus.yaml)  
- [Screenshot](addressable-firework-parus.jpg)  
- [YouTube Video](https://youtu.be/iwBEjguX0Tw)  

---

## Additional Information Sources

Telegram channel: https://t.me/parus_smart

---

## 🙏 Acknowledgments

- The ESPHome community for the excellent framework.  
- Home Assistant for integration.  
- You for using it! If the project is useful, please give it a ⭐ on GitHub.
