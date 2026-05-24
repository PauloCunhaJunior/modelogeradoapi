# modelogeradoapi
# API de Reconhecimento de Imagens com CNN e CIFAR-10

Este projeto foi desenvolvido como atividade prática da disciplina de Inteligência Artificial, com o objetivo de utilizar uma Rede Neural Convolucional (CNN) treinada com a base de dados CIFAR-10 e criar uma API em Python para realizar a previsão de imagens.

A proposta do trabalho é treinar um modelo de classificação de imagens, salvar esse modelo no formato `.h5` e depois utilizá-lo em uma API criada com Flask. A API recebe uma imagem, realiza o pré-processamento necessário e retorna a classe prevista pelo modelo.

## Objetivo do Projeto

O objetivo principal é criar uma API capaz de carregar um modelo CNN treinado e utilizá-lo para reconhecer imagens pertencentes às classes do conjunto CIFAR-10.

O modelo foi treinado no Google Colab, pois o ambiente já possui suporte às principais bibliotecas utilizadas em Inteligência Artificial, como TensorFlow e Keras.

## Tecnologias Utilizadas

- Python
- Google Colab
- TensorFlow
- Keras
- Flask
- NumPy
- Pillow
- Requests
- CIFAR-10

## Base de Dados CIFAR-10

O CIFAR-10 é um conjunto de dados composto por imagens pequenas de 32x32 pixels, divididas em 10 classes diferentes.

As classes utilizadas neste projeto são:

```python
[
    "avião",
    "automóvel",
    "pássaro",
    "gato",
    "cervo",
    "cachorro",
    "sapo",
    "cavalo",
    "navio",
    "caminhão"
]
