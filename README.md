# Calculadora de probabilidades para oposiciones // exámenes donde los temas se extraigan por sorteo

**Para utilizar la calculadora de probabilidades**: [Pinchar aquí](https://colab.research.google.com/github/Daalma7/ProbabilidadOposiciones/blob/main/CalculadoraProbabilidadesOposiciones.ipynb)

¡Hola! Este es un pequeño proyecto donde podrás calcular la probabilidad de que aparezca al menos 1 tema estudiado en un exámen donde haya un determinado número de temas y se extraigan un subconjunto de ellos para desarrollar.

Para que tú puedas calcular dicha probabilidad, dejo aquí la fórmula. Habiendo $N$ temas, extrayendo $n$ bolas y habiéndote estudiado $x$ temas, la probabilidad de que al menos salga uno es:

$$P[\text{Al menos uno}]= 1-\prod_{i=0}^{n-1} \frac{N-x-i}{N-i} $$

Como ejemplo, si hay 100 temas, estudias 20 y se extraen 4 bolas, la probabilidad sería:

$$P[\text{Al menos uno}]= 1-\prod_{i=0}^{4-1} \frac{100-20-i}{100-i}=1-\prod_{i=0}^{3} \frac{80-i}{100-i}=1-\left(\frac{80}{100}\times \frac{79}{99}\times \frac{78}{98}\times \frac{77}{97} \right)\approx 0.5967 \text{ (Un 59.67\\%) }$$  


Además, en el código también se calcula una cantidad "óptima" de temas a estudiar. Esta cantidad, también llamada "punto de rodilla" o "knee point" es la cantidad de temas a partir de la cual, si se estudia un tema más, se consigue un incremento en la probabilidad menor a la proporción que supone estudiar dicho tema.  

Por ejemplo, si tenemos $N=100$ temas, estudiar un tema supone estudiar un $1\\%$ del total de temas. La cantidad de temas óptima de temas a estudiar será aquella que al estudiar un tema más (estudiando un $1\\%$ más de temas) suponga un incremento en la probabilidad de que aparezca al menos un tema de los estudiados menor a un $1\\%$.

AVISO: Esta cantidad "óptima" de temas no es la "mejor". A más temas estudies, más probabilidades tendrás de no salir con el examen en blanco siempre ;)

Ejemplos de resultados:

<div align="center">
    <img src="other/scatter_po_algorithm_adult.png" width="412px"/> 
    <img src="other/scatter_po_algorithm_compas.png" width="412px"/> 
</div>

**Créditos**: David Villar Martos ([Link a Github](https://github.com/Daalma7))
