# Human_Classifier

## Equipe

- Luiz Henrique da Silva de Oliveira - 8127120431
- Felipe Cavalcante Lacerda - 8126841665
- Renan Laba Bott - 8125569279
- Pedro Henrique Mazzeu Sá - 8125856022

# Objetivo do classificador de imagem

- Identificar se a imagem de entrada é uma pessoa ou não

# Método utilizado

- O código acima implementa uma rede neural convolucional (CNN) utilizando a biblioteca Keras para classificar imagens em duas classes.

# Construção da CNN:
A CNN é construída usando a classe Sequential do Keras, que permite construir uma sequência de camadas.
Duas camadas convolucionais (Conv2D) são adicionadas, seguidas de camadas de normalização (BatchNormalization) e camadas de max pooling (MaxPooling2D).
Depois das camadas convolucionais, há uma camada de achatamento (Flatten) para converter os mapas de características em um vetor unidimensional.
Em seguida, duas camadas densas (Dense) são adicionadas com funções de ativação ReLU e dropout para evitar overfitting.
A última camada densa possui uma única unidade com função de ativação sigmoid, adequada para problemas de classificação binária.

#Compilação do modelo:
O modelo é compilado utilizando o otimizador Adam e a função de perda binary_crossentropy, uma vez que é um problema de classificação binária.
A métrica de avaliação escolhida é a accuracy (acurácia).

#Pré-processamento dos dados:
O ImageDataGenerator é utilizado para realizar o pré-processamento das imagens, aplicando várias transformações como rotação, espelhamento horizontal, cisalhamento, deslocamento de altura e zoom.
As imagens também são redimensionadas para o tamanho 128x128 e normalizadas para o intervalo [0, 1].

#Carregamento dos dados:
Os dados são carregados usando o método flow_from_directory, que permite carregar imagens diretamente de diretórios.
O diretório '/content/drive/MyDrive/retrato_outro' contém as imagens para treinamento e teste.
As imagens são carregadas com tamanho 128x128, em lotes de tamanho 20, e são classificadas em duas classes (binary).
A opção subset='training' é utilizada para carregar o conjunto de treinamento, enquanto subset='validation' é utilizada para carregar o conjunto de teste.

#Treinamento do modelo:
O modelo é treinado utilizando o método fit, onde são especificados o conjunto de treinamento (base_treinamento), o número de épocas (5), o conjunto de validação (base_teste) e o tamanho do lote (10).
