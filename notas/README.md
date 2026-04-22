# Pure Data - Aprendizaje progresivo

## Estructura del proyecto

| Carpeta | Contenido |
|---|---|
| `01_osciladores/` | Ondas básicas: seno, diente de sierra, cuadrada, ruido |
| `02_filtros/` | Filtros pasa-bajos, pasa-altos, resonancia |
| `03_envolventes/` | ADSR, line~, vline~ |
| `04_efectos/` | Delay, reverb, distorsión |
| `05_samplers/` | Lectura de samples, looping, pitchshift |
| `06_sintesis_avanzada/` | FM, síntesis granular, wavetable |
| `07_midi_control/` | Entrada MIDI, mapeo de controles |
| `08_generativo/` | Secuenciadores, aleatoriedad, patrones |

## Notas

- [audio.md](audio.md) — síntesis, objetos de audio útiles
- [midi.md](midi.md) — configuración MIDI, dispositivos
- [comunicacion.md](comunicacion.md) — pdsend/pdreceive, OSC

## Convención de rutas

Todos los patches usan rutas relativas (`./`) para que funcionen
en cualquier máquina independientemente de dónde esté instalado PD.
