# Aprendizado de máquina para diagnóstico de câncer co multi classificações.
Importante salientar que esses dados foram obtidos durante o curso da Alura https://cursos.alura.com.br/course/reducao-dimensionalidade .

## Sobre o algoritmo
* O desafio é fazer um modelo que reduz o número de exames necessários para o diagnóstico de câncer, com essa ideia iremos pegar dados fictícios, mas que poderiam ser reais. O mais importante são as técnicas e métodos utilizados para fazer isso acontecer.

* A explicação detalhada linha por linha você encontra aqui (https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/ML_diagnostico_MD.ipynb)



## Tecnologias  

Tecnologias usadas no projeto.

* Python
* Pandas
* Numpy
* Sklearn
* Matplotlib
* Seaborn

## Observação 
* NDA
  
# Usamos varias técnicas e comparamos uma com a outra para ver um modelo com boa acurácia e uma boa visualização.
 ### RandomForest
* Aplicar um RandomForest foi a priemira ideia de teste para sabermos nossa baseline.
![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/rdforest.png)

* RandomForest nos da uma acurácia de 95%, mas para saber se realmente é uma info valida temos que validar.
## Entendendo o que temos com a primeira visualização:
* Violinplot é uma boa maneira de saber qual exame é o melhor, se distribuímos separando maligno e benigno, sabemos que o exame com a melhor distribuição (uma    crista distante da outra) é o exame que consegue diagnosticar deixando menos duvida.

![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/violin.png)

* Uma observação é que algumas colunas têm valores constantes, por isso elas serão excluídas para as análises posteriores.

### Matriz de correlação
![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/heatmap.png)
* Para entendermos uma heatmap de correlação temos que saber que as cores mais claras indicão maior correlação, ignorando a diagonal(pois é a correlação da variável pela própria variável). Pensando nisso temos um problema, pois quando usamos treinar um modelo, utilizando "dados parecidos" (correlacionados) acabamos colocando um certo peso maior, deixando o modelo tendencioso. Por isso o ideal é retirar as features com maior correlação e treinar novamente para ter uma acurácia melhor.

### Tratamento refinado para nosso dataset: 
  
<center>  Como observamos na matriz de correlação algumas colunas, se deixadas no dataset, poderá viciar nosso treinamento, por isso vamos identificá-las e excluir uma de cada.
  
  * Primeiro vamos ver as colunas cujo a correlação esta acima de 0.99.
 
 ![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/tratamento1.png) 
  ---
 ![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/tratamento2.png)
  
  
  * Sabendo que pelo menos uma linha tem o valor 1 na matriz de correlação, somando as colunas onde tem valores acima de 0.99, temos somente os exames com maior correlação do dataset.
 
 ![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/tratamento3.png) 
  
  * Todos acima de 1 já que foram somados, são as nossas colunas que poluem nosso treinamento.
 
  ![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/tratamento4.png) 

</center>

### Matriz de confusão (Vamos ultilizar algumas): 

![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/k_best_con.png)

<center> Aqui podemos entender que de 116 casos de benigno o algoritmo acertou 111, ja os casos maligno de 55 de acertamos 44. </center>

### Matriz de confusão RFE: 

![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/RFE_conf.png)
<center> Seleção com RFE (recursive feature elimination), essa seleção é feita com a comparação de pontos de cada feature, sabendo quanto cada um vale nos descartamos a de menor pontuação, para facilitar imagine um ranking das suas features, a seleção vai eliminar todas ate sobrar apenas o melhor. </center>

### Matriz de confusão RFECV: 

![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/RFECV_conf.png)
<center> O RFECV tem a função de fazer praticamente a mesma coisa que no algoritmo de RFE, mas agora fazendo uma separação por grupos, ou seja, vamos escolher o melhor conjunto de features ao invés uma única melhor. Logo vamos selecionar o melhor grupo de features possível para o treinamento. </center

### Visualização: 

![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/sns_wpca.png)
<center> Mesmo com uma boa acurácia, com o que temos fica difícil ter uma boa visualização, então para poder entender melhor nossos pontos. Vamos aplicar o PCA nos nossos dados e verificar como ficará a visualização. </center>

### Visualização PCA:
![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/PCA.png)
<center> Dessa forma, conseguiremos enxergar de maneira mais clara a separação dos pontos, traçando uma linha que dividirá os cânceres dos tipos maligno ou benigno. </center>

### Visualização TSNE:
![Post show](https://github.com/PFCalanca/ML_diagnostico_MD/blob/master/core/img/TSNE.png)
<center> O t-Distributed Stochastic Neighbor Embedding (TSNE), mapeia os dados multidimensionais para um espaço dimensional inferior e tenta encontrar padrões nos dados identificando clusters observados com base na semelhança de pontos de dados com vários recursos.TSNE é uma técnica usada principalmente em exploração e visualização de dados.. </center>

## Links
  - Perfil do Linkedin : https://www.linkedin.com/in/paulo-de-freitas-calanca-109906174/
    - Caso você encontre algum erro ou tenha alguma observação, entre em contato.


  ## Autor

  * **Paulo de Freitas Calanca** 

  Please follow github and join us!
  Thanks to visiting me and good coding!
