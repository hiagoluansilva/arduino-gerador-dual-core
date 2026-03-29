🇧🇷 Português | 🇺🇸 [English](#english)

# arduino-gerador-dual-core

Gerador dual-canal no ESP32 usando os dois núcleos: seno no Core1 (ISR), triangular no Core0 (FreeRTOS).

**Core1:** GPIO 25 (seno via timer ISR)
**Core0:** GPIO 26 (triangular via FreeRTOS task)

## Como usar

1. Abra `gerador_dual_core.ino` no Arduino IDE
2. Selecione **ESP32 Dev Module**
3. Compile e grave

Centro Tecnológico Liberato — Novo Hamburgo/RS

---

<a name="english"></a>
🇧🇷 [Português](#) | 🇺🇸 English

# arduino-gerador-dual-core

Dual-channel generator on ESP32 using both cores: sine on Core1 (ISR), triangle on Core0 (FreeRTOS).

**Core1:** GPIO 25 (sine via timer ISR)
**Core0:** GPIO 26 (triangle via FreeRTOS task)

## Usage

1. Open `gerador_dual_core.ino` in Arduino IDE
2. Select **ESP32 Dev Module**
3. Compile and flash

Centro Tecnológico Liberato — Novo Hamburgo/RS, Brazil
