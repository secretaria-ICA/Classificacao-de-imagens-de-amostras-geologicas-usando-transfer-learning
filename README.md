# Classificação de imagens de amostras geológicas usando a técnica de transfer learning aplicada na resNet50.

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

Nessa monografia, será apresentado um estudo sobre a aplicação de transfer learning utilizando a ResNet50 para a classificação de imagens de amostras geológicas. Serão descritas as etapas do pré-processamento de dados, treinamento e teste da rede neural, além da análise dos resultados obtidos. A importância da escolha dos parâmetros de treinamento e a avaliação da performance da rede serão discutidas em detalhes.

Por fim, serão apresentadas as conclusões sobre a eficácia da técnica de transfer learning utilizando a ResNet50 para a classificação de imagens de amostras geológicas, bem como as possibilidades de aplicação em outras áreas da geologia e ciências da terra.


### 2. Modelagem

O trabalho foi criado em python usando a paltaforma de google colab. 

Primeiramente, foi necessário preparar o conjunto de dados de amostras geológicas, provenientes do repositório de [*geological image similarity*](https://www.kaggle.com/datasets/tanyadayanand/geological-image-similarity) do kaggle para alimentar a rede neural.

Usou-se uma utilidade de processamento de dados do keras chamada "*image_dataset_from_directory*". Esta ferramenta pega as imagens desde o diretório, as ordena por pastas (que representam classes), redimensiona as imagens. Tem como saida tensores com tamanhos de batch especificos prontos para fazer treinamento e validação.

As 29998 imagens de amostras geológicas estão separadas em 6 classes, cada uma em sua propria pasta:

*   Andesite 
*   Gneiss 
*   Marble 
*   Quartzite 
*   Rhyolite 
*   Schist


Em seguida, foi usada a ResNet50 pré-treinada como base da rede, removendo a camada de classificação final e adicionando uma nova camada de classificação personalizada para o conjunto de dados de amostras geológicas. Neste caso foi adicionada uma camada de 1024 neuronios Dense e uma camada de saida Danse de 6 neuronios representando cada uma uma classe de rocha. 

Após a configuração da rede, é possível realizar o treinamento utilizando o conjunto de dados de amostras geológicas. Durante o treinamento, é importante monitorar as métricas de desempenho da rede, como acurácia e perda. Para isto foram usados os callbacks *EarlyStopping* e *ReduceLROnPlateau* para deneter o treinamento no momento de ter ganhos não significativos junto com o *ModelCheckpoint* que permite salvar o modelo com melhor eficiencia. 

Finalmente foram criadas figuras para a avaliação do modelo.


### 3. Resultados


### 4. Conclusões


---

Matrícula: 211.101.340

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
