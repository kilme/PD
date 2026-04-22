# MIDI en Pure Data

## Configuración inicial
- Ir a **Media > MIDI Settings** al abrir Pd
- Los dispositivos hardware aparecen listados automáticamente
- Pd numera los puertos desde 1 (no desde 0)

## Objetos MIDI esenciales

| Objeto | Función |
|---|---|
| `[notein]` | Recibe note on/off (pitch, velocity, channel) |
| `[noteout]` | Envía note on/off |
| `[ctlin]` | Recibe Control Change (knobs, faders) |
| `[ctlout]` | Envía Control Change |
| `[pgmin]` | Recibe Program Change |
| `[bendin]` | Recibe Pitch Bend |
| `[bendout]` | Envía Pitch Bend |
| `[midiin]` | Recibe bytes MIDI raw |
| `[midiout]` | Envía bytes MIDI raw |

## Separar canal MIDI
`[notein]` sin argumento escucha todos los canales.
`[notein 1]` escucha solo el canal 1.

## Hardware conectado
- Dispositivo: (completar cuando se configure)
- Canal por defecto: (completar)

## Tips aprendidos
- Pd debe iniciarse DESPUÉS de conectar el hardware MIDI para detectarlo
- Si no aparece el dispositivo, cerrar y reabrir Pd con el hardware ya conectado
