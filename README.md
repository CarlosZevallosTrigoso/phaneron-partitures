# phaneron-partitures

Secuenciador en un solo HTML para tocar partituras escritas con criterios matemáticos y conceptuales: métricas cambiantes, polimetría, polirritmos, ritmos euclidianos y afinaciones microtonales (divisiones iguales, pitagórica, generador apilado, razones de Stern, razones justas, cents).

Las voces pueden leer series como ritmo, como duraciones o como alturas: Fibonacci, primos, la serie infinita de Nørgård, Recamán, Collatz, mira y di de Conway, Stern, Thue-Morse, la palabra de Fibonacci, Kolakoski, el triángulo de Pascal, autómatas celulares elementales y el mapa logístico.

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
