# Bitácora de decisiones del equipo

## Decisión 1: Cómo definimos la temperatura ideal para tomarse el tinto
- **Qué hicimos:** Usamos los datos reales de Cotter et al. (2022) y sacamos el promedio de temperatura cuando los catadores marcaron que estaba "justo en su punto" (`Temp == 3`), lo que nos dio **62,8 °C**.
- **Qué descartamos:** Inventarnos una temperatura al ojo o decir "a nosotros nos gusta a tal grado" sin respaldo.
- **Por qué:** Es más confiable apoyarnos en 118 personas reales que en una opinión, aunque sabemos que allá probaron café filtrado y nosotros hablamos de tinto en Manizales.

## Decisión 2: Cómo armamos la tabla de enfriamiento
- **Qué hicimos:** Generamos dos corridas simuladas (de 0 a 25 minutos) con temperaturas típicas de Manizales, siguiendo lo que nos permitió el monitor Juan Miguel Galeano.
- **Qué descartamos:** Hacer el montaje físico con termómetro de cocina.
- **Por qué:** Para avanzar rápido en el modelado matemático como nos indicó el monitor, dejando aclarado con total sinceridad en `datos/FUENTES.md` que son datos simulados.

## Decisión 3: Qué fórmula elegimos para el modelo (Hito 2)
- **Qué hicimos:** Ajustamos dos curvas a nuestros datos: una **Exponencial** (Ley de Newton) y una **Parábola** (cuadrática). Elegimos la **Exponencial**.
- **Qué descartamos:** La Parábola (`np.polyfit` grado 2).
- **Por qué:** La exponencial tiene menos error promedio frente a los datos, y además tiene sentido físico: si dejamos el tinto mucho tiempo, la exponencial se frena en 18 °C (la temperatura del cuarto). En cambio, la parábola baja hasta el minuto 30 y después vuelve a subir hacia arriba, como si el tinto frío se calentara solo.

## Decisión 4: Hasta dónde vale el modelo (Intervalo de validez)
- **Qué hicimos:** Declaramos que nuestro modelo vale entre el **minuto 0 y el minuto 25**.
- **Qué descartamos:** Confiar en la parábola fuera de esos 25 minutos.
- **Por qué:** En ese rango de tiempo el error es mínimo y alcanzamos a ver perfectamente cuando el tinto pasa por los 62,8 °C ideales (alrededor del minuto 7).
