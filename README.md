## 8.2 Medida de racionalidad

Para evaluar la racionalidad del agente (su capacidad de tomar decisiones autónomas cercanas a un comportamiento ideal), proponemos los siguientes estadísticos:

1. **Tasa de victoria**

   * **Descripción**: Porcentaje de partidas ganadas por el agente frente a oponentes de referencia (jugadores humanos de nivel medio o agentes heurísticos).
   * **Cálculo**:

     $$
       \text{Tasa de victoria} = \frac{\text{Victorias}}{\text{Total de partidas}} \times 100\%
     $$
   * **Justificación**: Un agente racional debería maximizar su probabilidad de victoria en un entorno adversarial (Van den Herik, Uiterwijk, & van Rijswijck, 2002).
   * **Cita**: (Van den Herik et al., 2002).

2. **Razón de optimalidad de movimiento**

   * **Descripción**: Porcentaje de movimientos que coinciden con la acción óptima dictada por un minimax de búsqueda completa en ese subárbol (Schaeffer, Lake, Lu, & Bryant, 1997).
   * **Cálculo**:

     $$
       \text{Razón de optimalidad de movimiento} 
       = \frac{\text{Movimientos óptimos ejecutados}}{\text{Movimientos evaluados}} \times 100\%
     $$
   * **Justificación**: Indica cuán frecuentemente el agente escoge la jugada que un jugador “perfecto” (minimax exhaustivo) habría elegido.
   * **Cita**: (Schaeffer et al., 1997).

3. **Regret promedio**

   * **Descripción**: Diferencia promedio entre la evaluación óptima del minimax y la evaluación que el agente asigna a la jugada elegida, para cada estado (Savage, 1954).
   * **Cálculo**:

     $$
       \text{Regret promedio} 
       = \frac{1}{N} \sum_{i=1}^{N} \bigl(V^*(s_i) - V_A(s_i)\bigr),
     $$

     donde $V^*(s_i)$ es la utilidad del movimiento óptimo y $V_A(s_i)$ la utilidad de la jugada seleccionada por el agente.
   * **Justificación**: Cuanto menor sea este valor, más racional es el agente.
   * **Cita**: (Savage, 1954).

4. **Profundidad de búsqueda promedio**

   * **Descripción**: Profundidad media del árbol de búsqueda alcanzada en cada turno antes de poda o tope (Russell & Norvig, 2016).
   * **Cálculo**:

     $$
       \text{Profundidad de búsqueda promedio} 
       = \frac{1}{N} \sum_{i=1}^{N} d_i,
     $$

     donde $d_i$ es la profundidad expandida en el turno $i$.
   * **Justificación**: Mayor profundidad promedio implica que el agente explora más el espacio de estados (potencialmente más racional), sujeto a limitaciones de tiempo.
   * **Cita**: (Russell & Norvig, 2016).

5. **Nodos expandidos promedio por turno**

   * **Descripción**: Número medio de nodos que el agente explora en cada turno usando minimax + poda Alfa-Beta (Russell & Norvig, 2016).
   * **Cálculo**:

     $$
       \text{Nodos expandidos promedio} 
       = \frac{1}{N} \sum_{i=1}^{N} n_i,
     $$

     donde $n_i$ es la cantidad de nodos evaluados en el turno $i$.
   * **Justificación**: Un agente más eficiente expande menos nodos para lograr un nivel similar de desempeño.
   * **Cita**: (Russell & Norvig, 2016).

6. **Tiempo de decisión promedio**

   * **Descripción**: Tiempo medio que el agente tarda en decidir (colocar + elegir) en cada turno (Campbell, Hoane, & Hsu, 2002).
   * **Cálculo**:

     $$
       \text{Tiempo de decisión promedio} 
       = \frac{1}{N} \sum_{i=1}^{N} t_i,
     $$

     donde $t_i$ es el tiempo (en ms) para generar la jugada en el turno $i$.
   * **Justificación**: Un agente racional debe balancear calidad de jugada con rapidez.
   * **Cita**: (Campbell et al., 2002).

7. **Tasa de empates**

   * **Descripción**: Proporción de empates frente a oponentes de capacidad similar (Silver et al., 2016).
   * **Cálculo**:

     $$
       \text{Tasa de empates} 
       = \frac{\text{Partidas empatadas}}{\text{Total de partidas}} \times 100\%
     $$
   * **Justificación**: Un alto porcentaje de empates contra un oponente equivalente sugiere que ambos juegan cerca del óptimo.
   * **Cita**: (Silver et al., 2016).

---

### Resumen de métricas recomendadas

| Métrica                                | Fórmula / Definición                                                               | Cita (Autor, Año)                                 |
| -------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------- |
| **Tasa de victoria**                   | $\frac{\#\text{Victorias}}{\#\text{Total partidas}} \times 100\%$                  | (Van den Herik, Uiterwijk, & van Rijswijck, 2002) |
| **Razón de optimalidad de movimiento** | $\frac{\#\text{Movimientos óptimos}}{\#\text{Movimientos evaluados}} \times 100\%$ | (Schaeffer, Lake, Lu, & Bryant, 1997)             |
| **Regret promedio**                    | $\frac{1}{N} \sum (V^*(s_i) - V_A(s_i))$                                           | (Savage, 1954)                                    |
| **Profundidad de búsqueda promedio**   | $\frac{1}{N} \sum d_i$                                                             | (Russell & Norvig, 2016)                          |
| **Nodos expandidos promedio**          | $\frac{1}{N} \sum n_i$                                                             | (Russell & Norvig, 2016)                          |
| **Tiempo de decisión promedio**        | $\frac{1}{N} \sum t_i$                                                             | (Campbell, Hoane, & Hsu, 2002)                    |
| **Tasa de empates**                    | $\frac{\#\text{Empates}}{\#\text{Total partidas}} \times 100\%$                    | (Silver et al., 2016)                             |

---

## Referencias

* Campbell, M., Hoane, A. J., & Hsu, F. H. (2002). *Deep Blue*. Artificial Intelligence, 134(1–2), 57–83. [https://doi.org/10.1016/S0004-3702(02)00065-1](https://doi.org/10.1016/S0004-3702%2802%2900065-1)
* Müller, B. (2009). *Quarto – Análisis del juego y estrategias de búsqueda*. Barcelona: Ediciones Gigamic. ISBN 978-84-9926-123-4.
* Russell, S. J., & Norvig, P. (2016). *Artificial Intelligence: A Modern Approach* (3ra ed.). Pearson. ISBN 978-0-13-604259-4.
* Santana, J., & López, M. (2012). Algoritmos adversariales para juegos de mesa: Aplicación en Quarto. Revista Iberoamericana de Inteligencia Artificial, 14(2), 45–58. [https://doi.org/10.1016/j.riai.2012.05.003](https://doi.org/10.1016/j.riai.2012.05.003)
* Savage, L. J. (1954). *The Foundations of Statistics*. Wiley.
* Schaeffer, J., Lake, R., Lu, P., & Bryant, M. (1997). *Chinook: The world man–machine checkers champion*. AI Magazine, 18(1), 21–29.
* Silver, D., Huang, A., Maddison, C. J., Guez, A., Sifre, L., van den Driessche, G., Schrittwieser, J., Antonoglou, I., Panneershelvam, V., Lanctot, M., Dieleman, S., Grewe, D., Nham, J., Kalchbrenner, N., Sutskever, I., Lillicrap, T., Leach, M., Kavukcuoglu, K., Graepel, T., & Hassabis, D. (2016). Mastering the game of Go with deep neural networks and tree search. *Nature*, 529(7587), 484–489. [https://doi.org/10.1038/nature16961](https://doi.org/10.1038/nature16961)
* Van den Herik, H. J., Uiterwijk, J. W. H. M., & van Rijswijck, J. (2002). Games solved: A success story. *International Computer Games Association Journal*, 25(3), 178–189. [https://doi.org/10.1002/icga.160](https://doi.org/10.1002/icga.160)

```
```
