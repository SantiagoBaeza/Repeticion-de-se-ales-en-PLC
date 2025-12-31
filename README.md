[⬅️ Volver a "Proyectos con PLC"](https://github.com/SantiagoBaeza/PLC-Siemens-TIA-Portal-)
# Repetición de bobinas de salida en PLC – Error común en LAD

Este proyecto muestra un error típico en programación de PLCs: **la repetición de bobinas de salida** en distintos segmentos. A través de una simulación sencilla, se evidencia por qué esta práctica está prohibida y cómo puede generar resultados engañosos.

---

## Contexto

Durante el curso de programación en escalera, se propuso un esquema de enclavamiento con dos motores. Se añadió una segunda bobina de salida (`motor3 - %M1.2`) en el mismo segmento donde ya estaba `motor2`, y luego se repitió `motor3` en un segundo segmento. Aunque la simulación inicial parece funcionar, el segundo segmento revela que `motor3` **no se energiza realmente**, demostrando el error.

## Capturas

- **Captura 01**: Comienzo de la simulación.
  ![Simulcion1](https://github.com/SantiagoBaeza/Repeticion-de-se-ales-en-PLC/blob/main/01%20.jpg)
- **Captura 02**: Circuito energizado, a punto de forzar el botón de inicio.
  ![Simulcion2](https://github.com/SantiagoBaeza/Repeticion-de-se-ales-en-PLC/blob/main/02.jpg)
- **Captura 03**: Resultado final, donde se observa que `motor3` no está encendido en el segundo segmento.
  ![Simulcion3](https://github.com/SantiagoBaeza/Repeticion-de-se-ales-en-PLC/blob/main/03.jpg)

## Lección importante

> Nunca se deben repetir bobinas de salida en distintos segmentos.  
> Aunque parezca funcionar, el PLC ignora la segunda instancia, generando errores silenciosos y mala práctica profesional.
> El PLC evalúa la lógica de izquierda a derecha y la última asignación de la bobina sobrescribe el estado anterior, por lo que la repetición genera resultados inconsistentes.

## Simulación realizada en

- Siemens S7-1200 (TIA Portal)
- Lógica en escalera (LAD)

## Comentarios finales: 
El [archivo](https://github.com/SantiagoBaeza/Repeticion-de-se-ales-en-PLC/blob/main/04%20repeticion%20de%20se%C3%B1ales%20(no%20hacer).ap16) del proyecto se incluye para que cualquier persona con acceso a TIA Portal V16 pueda abrirlo y realizar la simulación. En mi caso, el software fue proporcionado como parte del curso de Udemy que estoy realizando. Este ejercicio tiene como objetivo servir de práctica y dejar registro de mis avances en programación de PLC.

---

> 🧩 Estos espacios estan en construcción y se actualizan de forma frecuente.
