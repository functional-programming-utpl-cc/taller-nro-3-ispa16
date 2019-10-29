# Programación Funcional
## Taller Nro. 1

Utilizando la siguiente lista:

```scala
val countries = List("Ecuador", "Venezuela", "Colombia", "Perú", "Chile", "Argentina", "Uruguay", "Paraguay", "Brasil")
```
Elabore una función lambda que filtre aquellos países (countries) cuyos nombres:
1. Empiezan por la letra C.
2. Contienen la letra E.
3. Inician con la letra E o contienen la letra I.
4. Tengan una longitud mayor que 5.

Con la siguiente lista:
```scala
val numbers = List(10, 11, 12, 18, 20, 50, 60, 80, 81, 96)
```
5. Cree una función lambda que filter aquellos números que no son abundantes.


## Taller Nro. 3

Dentro de un archivo CSV(separado por ;) que se encuentra en la carpeta [aquí](/data/GLigaPro_2019.csv)(/data/GLigaPro_2019.csv) se ha almacenado los datos de los goleadores del campeonato Ecuatoriano de fútbol Liga Pro 2019.

El archivo posee 5 columnas (la primera fila corresponde a los nombres de las columnas), cada una de ellas se describe así:
- Jugador: El nombre del jugador
- Club: Nombre del club al que pertenece
- Nacionalidad: Nacionalidad del jugador
- Goles: Números de goles marcados
- Autogol: Cuando su valor es Si, señala que se trata de un gol en propia meta. Cuando es No, es el caso contrario.

Lectura de los datos desde el archivo:

```scala
 val lines = Source.fromFile(“ruta_al archivo_GLigaPro_2019.csv”).getLines.drop(1).toList
```

Convertir a una lista de tuplas de 5 elementos

```
val data = lines.map(
   line => line.split(";") match { 
      case Array(a, b, c, d, e) => (a.trim, b.trim, c.trim, d.trim.toInt, e.trim) 
   })
```

- Con los datos (valores en *data*) anteriores, responder a las siguiente preguntas:
- Presente en orden alfabético el nombre de los jugadores con más de 10 goles.
- Presente el nombre de los jugadores con mas de 10 goles, esta vez ordenados de forma descendente por el número de goles marcados. Consulte sobre la función sortBy.
- ¿A qué club pertenece el máximo goleador del campeonato?
- ¿Cuál es la nacionalidad del máximo goleador del campeonato?
- ¿Cuáles son los nombres de los jugadores que han marcado un autogol?
- ¿Cuál es la frecuencia de los goles marcados? (Cuántos jugadores tienen 1 gol, 2 goles, 3 goles, 4, goles, etc). Consultar groupBy y mapValues.
- ¿Cuáles son los nombres de los jugadores que han marcado goles en más de un club?
- ¿Cuáles son las nacionalidades y su frecuencia (número de veces que se repite) de los jugadores que han marcado más de 9?
