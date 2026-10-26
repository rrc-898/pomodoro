# pomodoro

Temporizador Pomodoro para la terminal: números grandes en ASCII, barra de progreso y ciclo automático estudio → descanso → estudio… Un solo fichero en Python, sin dependencias (usa `curses` de la biblioteca estándar).

```
                    ESTUDIO  ·  pomodoro #1

               ██████  ██████      ██████  ██████
                   ██  ██  ██  ██  ██  ██  ██  ██
               ██████  ██  ██      ██  ██  ██  ██
                   ██  ██  ██  ██  ██  ██  ██  ██
               ██████  ██████      ██████  ██████

           [█████████░░░░░░░░░░░░░░░░░░░░░░░░░]  26%


      estudio 30 min  ·  descanso 5 min  ·  completados 0
e cambiar tiempos · +/- ±1 min · espacio pausa · s saltar · r reiniciar · q salir
```

## Instalación

```sh
git clone https://github.com/rrc-898/pomodoro.git
install -Dm755 pomodoro/pomodoro ~/.local/bin/pomodoro
```

(`~/.local/bin` tiene que estar en el `PATH`.)

## Uso

```sh
pomodoro            # 30 min de estudio y 5 de descanso (o lo último que usaste)
pomodoro 25         # 25 min de estudio, descanso guardado
pomodoro 50 10      # 50 min de estudio, 10 de descanso
```

Los minutos admiten decimales (`0.5`). Lo que cambies se recuerda en `~/.config/pomodoro/config.json`.

| Tecla | Acción |
|---|---|
| `espacio` | pausa / reanudar |
| `+` / `-` | ±1 min al bloque actual |
| `e` | cambiar las duraciones de estudio y descanso |
| `s` | saltar al siguiente bloque |
| `r` | reiniciar el bloque |
| `q` | salir |

Al acabar cada bloque suena una alarma (`pw-play`) y aparece una notificación (`notify-send`); si no están instalados, simplemente se omiten. En terminales pequeñas se muestra una versión compacta.
