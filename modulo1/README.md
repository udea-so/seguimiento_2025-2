## MÓDULO 1 - VIRTUALIZACIÓN DE LA CPU

## Objetivos

### Objetivo general

* Evaluar el impacto de distintas políticas de planificación de la CPU en el rendimiento de un sistema operativo mediante simulación.
  
### Objetivos Especificos

* Analizar los mecanismos y características de las políticas de planificación FCFS, SJF, STCF, Round Robin y Prioridades (MLFQ).
* Implementar estas políticas en un simulador para procesar una serie de tareas predefinidas.
* Medir y comparar el rendimiento de cada política utilizando métricas como el tiempo de retorno promedio y el tiempo de espera promedio para determinar la más eficiente en cada escenario.

## Instrucciones de entrega

Suba un documento pdf en la plataforma con el procedimiento a mano y las capturas de la simulaciones realizadas. No olvide anotar las conclusiones.

## Ejercicios

### Parte 1: Políticas de planificación

1. Considere que cinco procesos llegan a la cola ready en el orden P1, P2, P3, P4 y P5 en el instante de tiempo cero. Asumiendo que el intervalo de cambio de contexto es despreciable (cero) y que las ráfagas de CPU (en microsegundos) para los procesos se muestran en la siguiente tabla:

   | Process | CPU burst |
   | :---- | :---- |
   | **P1** | 135 |
   | **P2** | 102 |
   | **P3** | 56 |
   | **P4** | 148 |
   | **P5** | 125 |

   **Procedimiento a mano**

   Desarrolle el siguiente procedimiento a mano:
   * Dibuje el diagrama de Gantt (o diagrama de ejecución) si la política de planificación empleada es la FCFS (FIFO).  
   * Usando la información obtenida del diagrama de Gantt, complete la siguiente tabla:

     | Process | *Tarrival*  | *Tfirstrun*  | *Tcompletion* | *Tturnaround* | *Tready* |
     | :---- | :---- | :---- | :---- | :---- | :---- |
     | **P1** |  |  |  |  |  |
     | **P2** |  |  |  |  |  |
     | **P3** |  |  |  |  |  |
     | **P4** |  |  |  |  |  |
     | **P5** |  |  |  |  |  |
     |  |  |  | **Promedio** |  |  |

   **Simulación**
 
   Empleando el script [scheduler.py](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/cpu-sched/scheduler.py) realice la simulación de la política anterior y compare los resultados teóricos con los de la simulación para la política FCSF (ver instrucciones de uso del simulador en el siguiente [link](https://github.com/remzi-arpacidusseau/ostep-homework/tree/master/cpu-sched)).

   Una vez realizado esto, compare los resultados obtenidos en la simulación con los que hizo a mano y saque conclusiones.
        
2. Teniendo en cuenta la misma información del problema anterior, pero empleando la política de planificación SJF, realice las siguientes actividades.
   
   **Procedimiento a mano**
     
   * Dibuje el diagrama de Gantt.  
   * A partir del diagrama de complete la siguiente tabla:

     | Process | *Tarrival*  | *Tfirstrun*  | *Tcompletion* | *Tturnaround* | *Tready* |
     | :---- | :---- | :---- | :---- | :---- | :---- |
     | **P1** |  |  |  |  |  |
     | **P2** |  |  |  |  |  |
     | **P3** |  |  |  |  |  |
     | **P4** |  |  |  |  |  |
     | **P5** |  |  |  |  |  |
     |  |  |  | **Promedio** |  |  |

   **Simulación**
   
   Empleando el script [scheduler.py](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/cpu-sched/scheduler.py) realice la simulación de la política anterior y compare los resultados teóricos con los de la simulación para la política SJF (ver instrucciones de uso del simulador en el siguiente [link](https://github.com/remzi-arpacidusseau/ostep-homework/tree/master/cpu-sched)). No olvide comparar y sacar conclusiones.
     
3. Ahora asuma, para el mismo problema anterior, que la política de planificación empleada es la RR con una ventana de tiempo (quantum) de 40 microsegundos y realice los siguientes procedimientos:  
   
   **Procedimiento a mano**
   * Dibuje el diagrama de Gantt.  
   * A partir del diagrama de complete la siguiente tabla:

     | Process | *Tarrival*  | *Tfirstrun*  | *Tcompletion* | *Tturnaround* | *Tready* |
     | :---- | :---- | :---- | :---- | :---- | :---- |
     | **P1** |  |  |  |  |  |
     | **P2** |  |  |  |  |  |
     | **P3** |  |  |  |  |  |
     | **P4** |  |  |  |  |  |
     | **P5** |  |  |  |  |  |
     |  |  |  | **Promedio** |  |  |

   **Simulación**

   Empleando el script [scheduler.py](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/cpu-sched/scheduler.py) realice la simulación de la política anterior y compare los resultados teóricos con los de la simulación para la política RR de quantum 40 (ver instrucciones de uso del simulador en el siguiente [link](https://github.com/remzi-arpacidusseau/ostep-homework/tree/master/cpu-sched)). Compare y saque conclusiones


4. A la luz de las diferentes métricas previamente obtenidas para cada una de las tres políticas de planificación previamente analizadas ¿cual es mejor?Justifique su respuesta.  
     
5. Considere ahora el problema anterior pero teniendo en cuenta que los procesos no llegan a la vez. Para este caso, el proceso P1 llega en el instante de tiempo 0, el proceso P2 llega en el instante 145, el proceso P3 en el instante 200, el proceso P4 en el instante 300 y el proceso P5 en el instante 400\.  
   Asumiendo que el intervalo de cambio de contexto es despreciable (cero). Se pide:  
   * Complete la siguiente tabla teniendo en cuenta la información anterior actualice la siguiente tabla:
   
     | Process | Arrival time | CPU burst |
     | :---- | :---- | :---- |
     | **P1** |  |  |
     | **P2** |  |  |
     | **P3** |  |  |
     | **P4** |  |  |
     | **P5** |  |  |

   * Dibuje el diagrama de Gantt correspondiente a la política STCF.  
   * Teniendo en cuenta el diagrama anterior complete la siguiente tabla:

     | Process | *Tarrival*  | *Tfirstrun*  | *Tcompletion* | *Tturnaround* | *Tready* |
     | :---- | :---- | :---- | :---- | :---- | :---- |
     | **P1** |  |  |  |  |  |
     | **P2** |  |  |  |  |  |
     | **P3** |  |  |  |  |  |
     | **P4** |  |  |  |  |  |
     | **P5** |  |  |  |  |  |
     |  |  |  | **Promedio** |  |  |

### Parte 2: MLFQ

6. La siguiente tabla muestra la información relacionada con 4 procesos que serán ejecutados por el planificador:

   | Process | arrival time | execution time |
   | :---- | :---- | :---- |
   | **P0** | 0 | 8 |
   | **P1** | 1 | 4 |
   | **P2** | 2 | 9 |
   | **P3** | 3 | 5 |

   
   Para este caso se emplea un planificador MLFQ cuyas reglas se muestran a continuación:
   * **Regla 1**: Si prioridad(A) \> prioridad(B); A se ejecuta.  
   * **Regla 2**: Si prioridad(A) \= prioridad(B); RR para A y B.  
   * **Regla 3**: Cuando un trabajo llega al sistema es ubicado en la cola con la prioridad más alta.  
   * **Regla 4**: Cuando un trabajo consume su asignación de tiempo en un nivel su prioridad es reducida (sin importar las veces que este retome el uso de la CPU).  
   * **Regla 5**: Después de un tiempo S, mueva todos los trabajos al mayor nivel de prioridad  
    
  El planificador se caracteriza por tener 3 Colas:   
  * Q2 (máxima prioridad, Q=1)  
  * Q1 (media, Q=2)  
  * Q0 (baja, Q=4).  
    
  En el caso dato, no se va a tener en cuenta el valor de S.  
  
  **Procedimiento manual**

  Teniendo en cuenta la información anterior:
  * Llene el siguiente diagrama resaltando en qué cola se encuentran cada uno de los 4 procesos a medida que transcurre el tiempo (Colocando en cada celda de la respectiva el proceso que está usando la CPU):   
     
    | Cola |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | 
    | ----- | ----: | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |---- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
    | **Q2** |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | |  |  |  |  |  |  |  |  |  |  |  |  |  |
    | **Q1** |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | |  |  |  |  |  |  |  |  |  |  |  |  |  |
    | **Q0** |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | |  |  |  |  |  |  |  |  |  |  |  |  |  |
    | **Tiempo** | 0 | 1 | 2 | 3 | 4 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30  |

  * A partir de la tabla anterior, dibuje el diagrama de Gantt donde se ilustre el uso de la CPU por parte de cada proceso.  
  * Teniendo en cuenta la información del punto b, llene la siguiente tabla:
   
    | Process | *Tarrival*  | *Tfirstrun*  | *Tcompletion* | *Tturnaround* | *Tready* |
    | :---- | :---- | :---- | :---- | :---- | :---- |
    | **P1** |  |  |  |  |  |
    | **P2** |  |  |  |  |  |
    | **P3** |  |  |  |  |  |
    | **P4** |  |  |  |  |  |
    |  |  |  | **Promedio** |  |  |
  
  **Simulación**

  * Empleando el simulador [mlfq.py](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/cpu-sched-mlfq/mlfq.py), realizar para este problema la simulación pasando los parámetros de acuerdo al enunciado. Para conocer cómo pasar estos usar este simulador consulte el siguiente [link](https://github.com/remzi-arpacidusseau/ostep-homework/tree/master/cpu-sched-mlfq). No olvide comparar los resultados y sacar conclusiones.

## Referencias

* [http://cpuburst.com/](http://cpuburst.com/)  
* [https://cpu-scheduling-algorithm-visualiser.netlify.app/](https://cpu-scheduling-algorithm-visualiser.netlify.app/)  
* [https://process-scheduler.vercel.app/app](https://process-scheduler.vercel.app/app)  
* [https://cobweb.cs.uga.edu/\~maria/classes/x730-Spring-2018/project4-scheduler.html](https://cobweb.cs.uga.edu/~maria/classes/x730-Spring-2018/project4-scheduler.html)  
* [https://cobweb.cs.uga.edu/\~maria/classes/1730-2023-Spring/\#](https://cobweb.cs.uga.edu/~maria/classes/1730-2023-Spring/#)  
* [https://cobweb.cs.uga.edu/\~maria/classes/x730-Spring-2020/index.html](https://cobweb.cs.uga.edu/~maria/classes/x730-Spring-2020/index.html)


  

