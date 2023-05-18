# Classificacao_de_Imagens_de_Amostras_Geologicas_Usando_a_Tecnica_de_Transfer_Learning_Aplicada_na_resNet50.

#### Aluno: [Fredy Giovany Osorio Gutiérrez](https://github.com/fr3dyos).
#### Orientador: [Leonardo Forero Mendonza](https://github.com/leofome8).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Link para o código](TL_geological_image_similarity_com_ResNet50.ipynb).

---
### Resumo

Este projeto tem como foco a aplicação da técnica de transfer learning utilizando a ResNet50 na classificação de amostras geológicas por meio de imagens. O objetivo principal é avaliar a eficácia e precisão da rede neural pré-treinada na identificação de diferentes tipos de rochas, minerais e materiais geológicos. O estudo busca fornecer conclusões relevantes sobre a aplicação de inteligência artificial em geologia e ciências da terra.

### 1. Introdução

A inteligência artificial tem sido amplamente aplicada em diversas áreas, incluindo a geologia. A classificação de imagens de amostras geológicas é uma tarefa importante para identificar e caracterizar diferentes tipos de rochas, minerais e outros materiais geológicos. No entanto, essa tarefa pode ser desafiadora devido à grande variedade de características e texturas presentes nas imagens geológicas.

Uma técnica eficiente para a classificação de imagens é o uso de transfer learning, que consiste em utilizar uma rede neural já pré-treinada em uma grande quantidade de dados e adaptá-la para uma tarefa específica. A ResNet50 é uma rede neural profunda que obteve excelentes resultados em tarefas de classificação de imagens em geral.

Nesta monografia, será apresentado um estudo sobre a aplicação de transfer learning utilizando a ResNet50 para a classificação de imagens de amostras geológicas. Serão descritas as etapas do pré-processamento de dados, treinamento e teste da rede neural, além da análise dos resultados obtidos. A importância da escolha dos parâmetros de treinamento e a avaliação da performance da rede serão discutidas em detalhes.

Por fim, serão apresentadas as conclusões sobre a eficácia da técnica de transfer learning utilizando a ResNet50 para a classificação de imagens de amostras geológicas, bem como as possibilidades de aplicação em outras áreas da geologia e ciências da terra.


### 2. Modelagem

O trabalho foi criado em python usando a plataforma de google colab. 

Primeiramente, foi necessário preparar o conjunto de dados de amostras geológicas, provenientes do repositório de [*geological image similarity*](https://www.kaggle.com/datasets/tanyadayanand/geological-image-similarity) do kaggle para alimentar a rede neural.

Usou-se uma utilidade de processamento de dados do keras chamada "*image_dataset_from_directory*". Esta ferramenta pega as imagens desde o diretório, as ordena por pastas (que representam classes), redimensiona as imagens. Tem como saida tensores com tamanhos de batch específicos prontos para fazer treinamento e validação.

As 29998 imagens de amostras geológicas estão separadas em 6 classes, cada uma em sua propria pasta:

*   Andesite 
*   Gneiss 
*   Marble 
*   Quartzite 
*   Rhyolite 
*   Schist


Em seguida, foi usada a ResNet50 pré-treinada como base da rede, removendo a camada de classificação final e adicionando uma nova camada de classificação personalizada para o conjunto de dados de amostras geológicas. Neste caso foi adicionada uma camada de 1024 neurônios *Dense* e uma camada de saída Danse de 6 neurônios representando cada uma uma classe de rocha. 

Após a configuração da rede, é possível realizar o treinamento utilizando o conjunto de dados de amostras geológicas. Durante o treinamento, é importante monitorar as métricas de desempenho da rede, como acurácia e perda. Para isto foram usados os callbacks *EarlyStopping* e *ReduceLROnPlateau* para detener o treinamento no momento de ter ganhos não significativos junto com o *ModelCheckpoint* que permite salvar o modelo com melhor eficiência. 


### 3. Resultados

Foi criada a figura de matriz de confusão para avaliar o modelo. Ela mostra como cada classe foi classificada pelo modelo.

Podemos observar que a maioria das amostras foi classificada corretamente, com exceção de algumas amostras de schist e gneiss que foram classificadas como andesite (38 e 11 amostras respectivamente), e algumas amostras de andesite que foram classificadas como schist (17 amostras).


A partir da matriz de confusão, podemos calcular as métricas de desempenho, como a acurácia, recall e F1-score para avaliar o desempenho geral do modelo. Ao calcular estas métricas encontramos um valor igual para todas de 0.978, o que representa que acima do 97% das amostras no dataset de validação foram classificadas corretamente pelo modelo proposto.

### 4. Conclusões

O modelo tem um desempenho geral muito bom: a acurácia de 0,978 indica que o modelo classifica corretamente a maioria das amostras. Com exceção de algumas amostras de andesite e quartzite que foram classificadas incorretamente.

A partir da matriz de confusão podemos concluir que algumas classes têm melhor desempenho do que outras, como marble e gneiss, que tiveram um desempenho excelente, com quase todas as amostras sendo classificadas corretamente. Por outro lado, outras classes, como andesite e schist, tiveram um desempenho um pouco pior, com algumas amostras sendo classificadas incorretamente, o que podem nos levar à conclusão a que são classes muito parecidas, porém, o valor alto da acurácia sugere que o modelo funciona da maneira apropriada na grande maioria dos casos.

A técnica de Transfer Learning é um método de aprendizado de máquina que permite reutilizar modelos de redes neurais pré-treinados em outras tarefas, com o objetivo de economizar tempo e recursos no processo de treinamento. Ao utilizar a ResNet50 como uma rede neural pré-treinada, o modelo pode aproveitar o conhecimento adquirido em treinamentos anteriores e ajustá-lo para resolver problemas de classificação específicos, como o de amostras geológicas.

Além disso, a utilização de Transfer Learning permitiu que o modelo reduzisse o consumo de recursos computacionais disponíveis, tornando-o mais eficiente e acessível. Isso é particularmente importante em aplicações de aprendizado de máquina que exigem grande capacidade de processamento e armazenamento, como é o caso de muitos modelos de visão computacional.

Por fim, a capacidade do modelo de classificar com sucesso amostras geológicas demonstra a sua relevância e eficácia como uma ferramenta poderosa no mundo moderno. O uso de modelos de inteligência artificial pode ser benéfico em diversas áreas, incluindo a análise de imagens, diagnóstico médico e previsão de tendências de mercado, entre outras aplicações.




---

Matrícula: 211.101.340

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*


