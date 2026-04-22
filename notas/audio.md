# Audio en Pure Data

## Activar audio
- **Media > Audio Settings** — elegir dispositivo de salida
- Botón **DSP on** (o Ctrl+/ ) para activar el procesamiento de audio
- `[dac~]` es la salida de audio (izquierda = L, derecha = R)
- `[adc~]` es la entrada de micrófono/línea

## Objetos de síntesis básicos

| Objeto | Función |
|---|---|
| `[osc~ 440]` | Oscilador sinusoidal a 440 Hz |
| `[phasor~]` | Osciladorcsaw (diente de sierra) |
| `[noise~]` | Ruido blanco |
| `[bp~]` | Filtro pasa-banda |
| `[lop~]` | Filtro pasa-bajos |
| `[hip~]` | Filtro pasa-altos |
| `[vcf~]` | Filtro resonante controlado por voltaje |
| `[env~]` | Envelope follower |
| `[line~]` | Interpolación suave para audio |
| `[vline~]` | line~ con mayor precisión temporal |
| `[sig~]` | Convierte número a señal de audio |
| `[*~]` | Multiplicación de señales (volumen, AM) |
| `[+~]` | Suma de señales (mezcla) |

## MIDI a frecuencia
`[mtof]` convierte nota MIDI a Hz (ej: 69 → 440)
`[ftom]` convierte Hz a nota MIDI

## Patrón típico nota MIDI → sonido
```
[notein] → pitch outlet → [mtof] → [osc~] → [*~] → [dac~]
                velocity outlet → [/ 127] → [*~]
```

## Tips de audio
- Siempre multiplicar por la velocity (dividida por 127) para tener dinámica
- Usar `[line~]` para evitar clicks en cambios de volumen abruptos
- El sample rate por defecto es 44100 Hz, block size 64
