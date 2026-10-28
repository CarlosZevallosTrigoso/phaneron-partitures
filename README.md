# phaneron-partitures

Secuenciador en un solo HTML para tocar partituras escritas con criterios matemáticos y conceptuales: métricas cambiantes, polimetría, polirritmos, ritmos euclidianos y afinaciones microtonales (divisiones iguales, pitagórica, generador apilado, razones de Stern, razones justas, cents).

Las voces pueden leer series como ritmo, como duraciones o como alturas: Fibonacci, primos, la serie infinita de Nørgård, Recamán, Collatz, mira y di de Conway, Stern, Thue-Morse, la palabra de Fibonacci, Kolakoski, el triángulo de Pascal, autómatas celulares elementales y el mapa logístico.

Para buscar una música a-significante hay herramientas que desactivan, una por una, las pistas con que el oído construye sentido: afinaciones sin octava (`afinación paso 78`, `afinación tritava 13`), tiempo sin pulso (`tiempo libre`, ataques de Poisson), notas esparcidas en varias octavas (`dispersar`), fuerzas al azar (`vel azar`), permutaciones que agotan las alturas antes de repetir, y un generador de `expectativa` que elige según un modelo de oyente, de lo más esperado (un ritornelo) a lo menos esperado. Un medidor calcula para cada voz la entropía de las alturas, la sorpresa por nota, los motivos repetidos y la regularidad del tiempo. Una observación medida: el punto menos predecible no es «siempre lo inesperado» sino el azar; rechazar lo esperado de forma sistemática vuelve a formar patrón.

Hay también ruido continuo de tres colores (`voz ruido` con `color blanco`, `rosa` o `marrón`), que puede sonar solo o debajo de cualquier pieza. Un metaanálisis (Nigg y colegas, 2024) encontró que el ruido blanco o rosa mejora un poco la atención en niños y adolescentes con TDAH y la empeora un poco en quienes no lo tienen; no es un tratamiento.

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

El botón «Todo piano» escribe `instrumento piano` al comienzo de la partitura: mientras esa línea esté, todas las voces suenan en el piano.

## Ejemplos

Las partituras de ejemplo se escribieron para esta aplicación a partir de reglas matemáticas; ninguna transcribe ni adapta una obra existente. Cada una explica en sus comentarios la idea que la organiza. Hay 21 para piano, 3 para leer, 3 de ruido (blanco, rosa y marrón), 4 a-significantes (también para piano), 7 para los sintetizadores y una plantilla. Las piezas para leer no están demostradas como óptimas: aplican el principio, con respaldo en la investigación sobre sonido irrelevante, de que lo que distrae al leer es el cambio impredecible.

## Fuentes y homenajes

Algunas piezas toman ideas o procedimientos de otros, y lo dicen en sus comentarios:

- La métrica 9/8 · 8/8 · 7/8 de «987» es un homenaje a *Lateralus* de Tool.
- La serie infinita (`norgard`) es de Per Nørgård.
- «Rhythmicon» sigue la idea de Henry Cowell y Léon Theremin: los mismos cocientes como ritmo y como altura.
- «Canon 3:4:5» rinde homenaje a los canones de tempo de Conlon Nancarrow para pianola.
- «Otonalidad» usa el término y la escala armónica de Harry Partch; «Treinta y uno», la división de la octava de Christiaan Huygens y Adriaan Fokker.
- «Octatónica» y «No retrogradables» usan dos ideas de Olivier Messiaen: los modos de transposición limitada y los ritmos palindrómicos.
- Los ritmos euclidianos siguen el análisis de Godfried Toussaint sobre ritmos tradicionales.
- Las herramientas a-significantes retoman ideas conocidas: los procesos de Poisson de la música estocástica de Iannis Xenakis; la escala alfa de Wendy Carlos; la escala de Heinz Bohlen y John Pierce; el puntillismo de Anton Webern; la dinámica independiente de Messiaen (*Mode de valeurs et d'intensités*); el principio dodecafónico de no repetir antes de agotar las alturas. El modelo de oyente sigue la teoría de la expectativa de David Huron y el modelo IDyOM de Marcus Pearce. La observación de que el rechazo sistemático y el azar convergen recuerda el análisis de György Ligeti sobre *Structures Ia* de Boulez. El término «a-significante» es de Félix Guattari.
- Las series y teoremas citados (Fibonacci, Pisano, Dirichlet, Stern, Calkin-Wilf, Thue-Morse, Prouhet, Kolakoski, Conway, Collatz, Recamán, Lucas, Wolfram, Cook, Li-Yorke, Lorenz) son de dominio matemático.

## Créditos

Piano: [Salamander Grand Piano V3](https://sfzinstruments.github.io/pianos/salamander) de Alexander Holm, bajo licencia [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/). Se usan 4 de sus 16 capas, en mono, recortadas y en MP3; el detalle de los cambios está en `muestras/piano/CREDITOS.txt`.
