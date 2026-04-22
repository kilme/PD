# Comunicación externa con Pure Data

## pdsend / pdreceive (vienen con Pd)
Ubicación: `C:\Program Files\Pd\bin\`

### Enviar mensaje a Pd desde terminal
```bash
echo "mensaje" | pdsend 3000
# o con argumento directo:
pdsend 3000 localhost udp
```

### Recibir mensajes de Pd
```bash
pdreceive 3001
```

## Desde Python
```python
import subprocess
# Enviar mensaje simple a Pd
subprocess.run(['pdsend', '3000', 'localhost', 'udp'], input=b'play 60;\n')
```

O mejor con socket UDP directo:
```python
import socket

def send_to_pd(message, port=3000):
    sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
    sock.sendto((message + ';\n').encode(), ('127.0.0.1', port))
    sock.close()

send_to_pd('note 60 127')
```

## En el patch Pd (receptor)
```
[netreceive 3000 udp]
        |
     [print]   <- para debug, ver qué llega
```

## Puertos usados en este proyecto
- 3000 → Python/script → Pd (entrada)
- 3001 → Pd → Python/script (salida)

## OSC (Open Sound Control)
Para proyectos más complejos, usar la librería `mrpeach` o `osc`:
- Instalar desde **Help > Find Externals** dentro de Pd
- Permite mensajes con rutas tipo `/synth/note 60 127`
