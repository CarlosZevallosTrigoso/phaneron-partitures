# phaneron-partitures

Secuenciador en un solo HTML para tocar partituras escritas con criterios matemáticos y conceptuales: métricas cambiantes, polimetría, polirritmos, ritmos euclidianos y afinaciones microtonales (divisiones iguales, pitagórica, generador apilado, razones de Stern, razones justas, cents).

Las voces pueden leer series como ritmo, como duraciones o como alturas: Fibonacci, primos, la serie infinita de Nørgård, Recamán, Collatz, mira y di de Conway, Stern, Thue-Morse, la palabra de Fibonacci, Kolakoski, el triángulo de Pascal, autómatas celulares elementales y el mapa logístico.

Los instrumentos son sintéticos: batería analógica, un bajo con ampli en paralelo (grave limpio, medios saturados), pads de filtro lento con vibrato tardío, campanas FM, cuerda pulsada y seno, con una sala oscura por convolución.

El piano es grabado: usa muestras de Salamander Grand Piano en `muestras/piano/`, con la afinación real de cada nota medida, así que los microtonos y las razones justas suenan donde se escriben. Se descargan solo las capas de fuerza que usa la partitura.

`index.html` no tiene dependencias ni paso de compilación. El audio usa la Web Audio API del navegador y lo que se oye es lo mismo que se exporta en WAV.

## Partituras

La carpeta `partituras/` guarda las partituras en texto plano. Para tocar una, ábrela con «Abrir .txt» o pégala en el editor y pulsa Tocar. La referencia completa del lenguaje está dentro de la aplicación.

```
tempo 132
compás 9/8 8/8 7/8
afinación pitagórica 7
base 55

voz bombo
  ritmo euclides(3)
voz bajo
  ritmo euclides(5)
  grados fib mod 7
```

El piano necesita que la app se sirva desde una web (por ejemplo GitHub Pages): si se abre `index.html` como archivo local, el navegador bloquea la carga de las muestras y el resto de los instrumentos sigue sonando.

## Créditos

Piano: [Salamander Grand Piano V3](https://sfzinstruments.github.io/pianos/salamander) de Alexander Holm, bajo licencia [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/). Se usan 4 de sus 16 capas, en mono, recortadas y en MP3; el detalle de los cambios está en `muestras/piano/CREDITOS.txt`.
