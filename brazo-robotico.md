---
# ===== Datos del proyecto (aparecen en la tarjeta y en la cabecera) =====
titulo: "Brazo robótico de 4 ejes"
resumen: "Brazo de acrílico con 4 servos, controlado con Arduino y un driver PCA9685, y luego desde una Raspberry Pi con cámara."
fecha: 2026-12-20            # año-mes-día; ordena los proyectos (el más reciente primero)
duracion: "3 semanas"
estado: "En progreso"        # "Terminado" o "En progreso"
tecnologias: [Arduino, PCA9685, Servos SG90, Raspberry Pi 5, Python]
imagen: /assets/img/proyectos/brazo-robotico/portada.svg   # foto principal
video: ""                    # solo el código del video de YouTube, ej: "dQw4w9WgXcQ"
codigo: ""                   # enlace al repositorio en GitHub
---

> **Este es un proyecto de EJEMPLO.** Reemplaza los textos con tu propia experiencia
> (o úsalo como guía y bórralo cuando tengas tu primer proyecto real).

## La idea

Quería entender cómo se mueve un brazo industrial: cómo se coordinan varias
articulaciones para llegar a un punto. Mi meta era que el brazo pudiera
**tomar una pieza pequeña y dejarla en otro lugar**, primero con comandos
manuales y después reconociendo el objeto con una cámara.

## Diseño

- Kit de brazo de acrílico de 4 grados de libertad (base, hombro, codo y pinza).
- Un servo SG90 por articulación.
- El Arduino no puede alimentar 4 servos directamente, así que usé un
  **driver PCA9685** (controla hasta 16 servos por I²C) con su propia fuente de 5V.

![Diagrama de conexiones](/assets/img/proyectos/brazo-robotico/portada.svg)
*Pie de foto: aquí iría tu diagrama o un boceto en papel.*

## Materiales

| Componente | Cantidad | Para qué sirve |
|---|---|---|
| Kit brazo acrílico 4 DOF | 1 | Estructura |
| Servo SG90 | 4 | Mover cada articulación |
| Driver PCA9685 | 1 | Controlar los servos |
| Fuente 5V 2A | 1 | Alimentar los servos |
| Arduino Uno | 1 | Cerebro (fase 1) |
| Raspberry Pi 5 + Cámara Module 3 | 1 | Visión (fase 2) |

## Proceso

### 1. Armado mecánico
Escribe qué hiciste, en qué orden y agrega fotos. Las fotos del proceso son
lo que más valoran quienes revisan un portafolio.

### 2. Conexiones
Conecté el PCA9685 al Arduino por I²C (SDA → A4, SCL → A5) y los servos a
los canales 0 a 3.

### 3. Programación
Un fragmento corto del código, si ayuda a explicar:

```cpp
#include <Adafruit_PWMServoDriver.h>
Adafruit_PWMServoDriver pwm;

void setup() {
  pwm.begin();
  pwm.setPWMFreq(50);   // los servos trabajan a 50 Hz
}
```

## Problemas y cómo los resolví

Esta es la sección más importante: demuestra cómo piensas.

- **Problema:** al mover dos servos a la vez, el Arduino se reiniciaba.
  **Causa:** los servos tomaban demasiada corriente del USB.
  **Solución:** alimentar los servos con una fuente aparte y unir las tierras (GND).
- **Problema:** el brazo se movía muy brusco y la pieza se caía.
  **Solución:** mover los servos en pasos pequeños con una pausa entre cada uno.

## Resultado

Qué logré, qué funcionó y qué no. Si hay video, aparece arriba automáticamente.

## Qué aprendí y próximos pasos

- Aprendí la diferencia entre alimentar la lógica y alimentar los motores.
- Próximo paso: usar la cámara de la Raspberry Pi para detectar el objeto.
  *Ojo:* la Pi trabaja a 3.3V y el Arduino a 5V; los conectaré por USB.
