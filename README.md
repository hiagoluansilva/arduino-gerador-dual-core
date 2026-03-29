# arduino-gerador-dual-core

Gerador de funções de dois canais simultâneos no ESP32 usando os dois núcleos do processador (dual-core).

## Descrição

Versão avançada do gerador de funções que explora o ESP32 dual-core: o sinal **senoidal** é gerado no Core 1 via ISR de timer de hardware, enquanto o sinal **triangular** é gerado no Core 0 por uma task FreeRTOS. Os dois canais operam simultaneamente e de forma independente.

## Hardware

- Placa: ESP32
- Canal seno: GPIO 25 (DAC1) — Core 1
- Canal triangular: GPIO 26 (DAC2) — Core 0

## Arquitetura

```
Core 1 (App CPU)        Core 0 (Protocol CPU)
─────────────────       ──────────────────────
Timer ISR (seno)        FreeRTOS Task (triangular)
dacWrite(25, ...)       dacWrite(26, ...)
```

## Parâmetros

| Parâmetro | Valor |
|-----------|-------|
| Amostras por ciclo | 112 |
| Resolução DAC | 8 bits |
| Timer Core1 prescaler | 992 |
| Intervalo Core0 | 100 µs |

## Como usar

1. Abra `gerador_dual_core.ino` no Arduino IDE
2. Selecione **ESP32 Dev Module**
3. Compile e grave
4. Observe os dois sinais simultâneos nos pinos 25 e 26

## Escola

Centro Tecnológico Liberato — Novo Hamburgo/RS
