# De dónde sacamos los datos

## 1. Temperatura ideal para tomar café (`cotter_dataset.csv`)
- **Fuente:** Estudio de Cotter et al. (2022) sobre preferencias de temperatura en café negro (*Scientific Reports*, DOI: 10.1038/s41598-022-24372-6). Descargado el 25 de noviembre de 2026.
- **Para qué lo usamos:** Tiene 3.186 pruebas de 118 personas. Filtramos solo las respuestas donde la gente dijo que el café estaba "justo en su punto" (`Temp == 3`) y sacamos el promedio de temperatura (`90Sec Temp`), que nos dio **62,8 °C**. Ese es nuestro objetivo.

## 2. Enfriamiento del tinto minuto a minuto (`serie_simulada_tinto.csv`)
- **Origen:** Serie simulada usando la Ley de Enfriamiento de Newton para dos tazas de tinto en Manizales (del minuto 0 al 25).
- **Por qué no medimos con termómetro:** El monitor Juan Miguel Galeano nos dijo en el laboratorio que no hacía falta ponernos a medir todo el día con termómetro y que podíamos armar los datos apoyándonos en la teoría física.
- **Valores usados:** Arrancamos en 85 °C (Corrida 1) y 84 °C (Corrida 2), que es más o menos como queda el tinto recién servido en casa en Manizales, con temperatura ambiente de 18 °C y 20 °C y una constante de enfriamiento típica de taza abierta ($k \approx 0,055$ y $0,060\text{ min}^{-1}$).
