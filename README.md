# Arduino Gerador Dual Core — FreeRTOS no ESP32

🇧🇷 **Português** | 🇺🇸 [English](#english)

---

## Português

Gerador de funções dual-core no ESP32 usando FreeRTOS: Core1 gera onda senoidal via ISR de timer (PSC=992) e Core0 gera onda triangular via task FreeRTOS (100 µs).

### O que faz
- **Core1**: Gera onda senoidal via interrupção de timer (PSC=992)
- **Core0**: Gera onda triangular via task FreeRTOS com intervalo de **100 µs**
- Demonstra uso simultâneo dos dois núcleos do ESP32-S3/ESP32

### Arquitetura dual-core
```
Core1: Timer ISR (PSC=992) → tabela senoidal → DAC
Core0: FreeRTOS Task (100 µs) → rampa triangular → DAC
```

### Parâmetros
| Parâmetro | Core1 (Senoidal) | Core0 (Triangular) |
|---|---|---|
| Tipo de controle | Timer ISR | FreeRTOS Task |
| PSC / Intervalo | PSC = 992 | 100 µs |
| Forma de onda | Senoidal | Triangular |

### Por que dual-core?
O ESP32 tem dois núcleos Xtensa LX6. Ao distribuir formas de onda entre os núcleos, cada uma pode ser atualizada independentemente sem conflito de temporização.

### Plataforma
ESP32 — Arduino Framework + FreeRTOS

---

## English

Dual-core function generator on ESP32 using FreeRTOS: Core1 generates sine wave via timer ISR (PSC=992) and Core0 generates triangle wave via FreeRTOS task (100 µs).

### What it does
- **Core1**: Generates sine wave via timer interrupt (PSC=992)
- **Core0**: Generates triangle wave via FreeRTOS task every **100 µs**
- Demonstrates simultaneous use of both ESP32 cores

### Dual-core architecture
```
Core1: Timer ISR (PSC=992) → sine table → DAC
Core0: FreeRTOS Task (100 µs) → triangle ramp → DAC
```

### Parameters
| Parameter | Core1 (Sine) | Core0 (Triangle) |
|---|---|---|
| Control type | Timer ISR | FreeRTOS Task |
| PSC / Interval | PSC = 992 | 100 µs |
| Waveform | Sine | Triangle |

### Why dual-core?
The ESP32 has two Xtensa LX6 cores. By distributing waveforms across cores, each can be updated independently without timing conflicts.

### Platform
ESP32 — Arduino Framework + FreeRTOS
