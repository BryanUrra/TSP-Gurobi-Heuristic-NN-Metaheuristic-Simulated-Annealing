Desarrollo en Python del problema del vendedor viajero o Travelling Salesman Problem (TSP) comparando una solución óptima
con Gurobi, una solución heurística con el vecino más cercano y una solución metaheurística con Recocido Simulado. 
Se realiza un análisis de sensibilidad de los parámetros y se grafica la solución, la cual se guarda en imágenes para 
crear posteriormente un video con el comportamiento de la solución y su variación en el tiempo.

- Heurística del Vecino más Cercano: Una solución TSP puede hallarse comenzando con una ciudad (nodo) y luego conectándola 
con la ciudad no conectada más cercana (los empates se rompen arbitrariamente). La ciudad que se acaba de agregar se conecta 
entonces con su ciudad no conectada más cercana. El proceso continúa hasta que se forma un recorrido.

- Metaheurística: Escapa del entrampamiento en el óptimo local al permitir movimientos inferiores, si es necesario. 
Se espera que la flexibilidad agregada a la búsqueda conduzca a una mejor solución.

- El recocido simulado o Simulated annealing (SA): Escapa del atrapamiento de un óptimo local utilizando una condición de 
probabilidad que acepta o rechaza un movimiento inferior (siempre se acepta un mejor movimiento). A medida que la cantidad 
de iteraciones se incrementa, el RS busca una determinación más selectiva de estrategias de solución utilizando un parámetro
ajustable 𝑇, llamado temperatura, es decir, se hace progresivamente más pequeño de acuerdo con un programa de temperatura. 

ITERACIONES y GRÁFICOS

Semilla: 100 gráficos cambiando la semilla del 1 al 100 (parámetros: Semillas,100,0.9,10,0.9)

Cantidad de iteraciones: Semilla fija en la mejor solución anterior (seed=9), se realiza 50 iteraciones 
con los parámetros (9,cant_iteraciones,0.9,10,0.9). Las iteraciones varían de 10 en 10 desde 10 a 500

Alfa: Semilla fija en la mejor solución anterior (seed=9) y se realiza 50 iteraciones con los parámetros 
(9,100,Alfas,10,0.9).Las iteraciones varían de 0.001 a 0.001 desde 0.5 a 0.99

Aceptaciones: Semilla fija en la mejor solución anterior (seed=9), se realiza 50 iteraciones 
con los parámetros (9,100,0.9,Aceptaciones,0.9). Las iteraciones varían de 10 en 10 desde 10 a 500

Temperatura: Semilla fija en la mejor solución anterior (seed=9) y aceptaciones en 43 (misma solución óptima
pero en menor tiempo). Se realiza 50 iteraciones con los parámetros (9,100,0.9,43,Temperatura). 
Las iteraciones varían de 0.001 a 0.001 desde 0.5 a 0.99

Metaheurística: Se utilizan los mejores resultados de las iteraciones anteriores. Se realizan 100 iteraciones
con distintas semillas y sus parámetros son (Semillas,100,0.64,43,0.56). 

Conclusión: Los parámetros que más afectan son las semillas, aceptaciones y temperatura. Al probar con los 
"mejores parámetros" se obtienen una mejor solución (1,04%) que sólo cambiando semillas (1,1%). Además, las 
soluciones tienden a tener un GAP inferior (no superan el 15,54%, mientras que sólo con semilla llegan a 21,39%.
