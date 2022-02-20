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
![Post show](TEXTO)

* RandomForest nos da uma uma acuracia de 95% mas para saber se realmente é uma info valida temos que validar
## Entendendo o que temos com a primeira visualização:
* Violinplot é uma boa maneira de saber qual exame é o melhor, se distribuimos separando maligno e beligno, sabemos que o exame com a melhor distribuição (uma    crista distante da outra) é o exame que é capaz de diagnosticar deixando menos duvida.

![Post show](TEXTO)

* Uma observação é que algumas colunas tem valores constantes, por isso elas seram excluidas para as analises posteriores

### Matriz de correlação
![Post show](TEXTO)
* Para entendermos uma heatmap de correlação temos que saber que as cores mais claras indicão maior correlação, ignorando a diagonal(pois é a correlação da variável pela própria variável). Pensando nisso temos um problema, pois quando usamos treinar um modelo, utilizando "dados parecidos" (correlacionados) acabamos colocando um certo peso maior, deixando o modelo tendencioso. Por isso o ideal é retirar as features com maior correlação e treinar novamente para ter uma acurácia melhor.

### Tratamento refinado do nosso dataset: 
  
<center>  Como observamos na matriz de correlação algumas colunas, se deixadas no dataset, poderá viciar nosso treinamento, por isso vamos identificá-las e excluir uma de cada.
  
  ![Post show](TEXTO) 
  
  ![Post show](TEXTO)
 
  * TEXTO.
  
  ![Post show](TEXTO) 
</center>

### Matriz de confusão: 



### Matriz de confusão RFE: 



### Matriz de confusão RFECV: 


### Visualização: 



### Visualização PCA:


### Visualização TSNE:

## Links
  - Perfil do Linkedin : https://www.linkedin.com/in/paulo-de-freitas-calanca-109906174/
    - Caso você encontre algum erro ou tenha alguma observação, entre em contato.


  ## Autor

  * **Paulo de Freitas Calanca** 

  Please follow github and join us!
  Thanks to visiting me and good coding!
