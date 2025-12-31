[⬅️ Volver a "Proyectos con PLC"](https://github.com/SantiagoBaeza/PLC-Siemens-TIA-Portal-)
# Repetición de señales en PLC – Error común y su demostración

Este proyecto muestra un error típico en programación de PLCs: **la repetición de bobinas de salida** en distintos segmentos. A través de una simulación sencilla, se evidencia por qué esta práctica está prohibida y cómo puede generar resultados engañosos.

---

## Contexto

Durante el curso de programación en escalera, se propuso un esquema de enclavamiento con dos motores. Se añadió una segunda bobina de salida (`motor3 - %M1.2`) en el mismo segmento donde ya estaba `motor2`, y luego se repitió `motor3` en un segundo segmento. Aunque la simulación inicial parece funcionar, el segundo segmento revela que `motor3` **no se energiza realmente**, demostrando el error.

## 📸 Capturas

- **Captura 01**: Esquema sin simular.
  ![Simulcion1](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/07%20boton%20sin%20presionar%20de%20vuelta%20.jpg)
- **Captura 02**: Circuito energizado, a punto de forzar el botón de inicio.
  ![Simulcion2](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/07%20boton%20sin%20presionar%20de%20vuelta%20.jpg)
- **Captura 03**: Resultado final, donde se observa que `motor3` no está encendido en el segundo segmento.
  ![Simulcion3](https://github.com/SantiagoBaeza/Enclavamiento-de-motor-simulacion-/blob/main/07%20boton%20sin%20presionar%20de%20vuelta%20.jpg)

## Lección clave

> Nunca se deben repetir bobinas de salida en distintos segmentos.  
> Aunque parezca funcionar, el PLC ignora la segunda instancia, generando errores silenciosos y mala práctica profesional.

## Simulación realizada en

- Siemens S7-1200 (TIA Portal)
- Lógica en escalera (LAD)

---

> 🧩 Estos espacios estan en construcción y se actualizan de forma frecuente.
