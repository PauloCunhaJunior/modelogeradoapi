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
```
## Funcionamento do Projeto

O projeto funciona em duas etapas principais.
Na primeira etapa, é realizado o treinamento da Rede Neural Convolucional com a base CIFAR-10. Após o treinamento, o modelo é salvo no arquivo:

modelo_cifar10.h5

Na segunda etapa, esse modelo é carregado por uma API desenvolvida com Flask. A API recebe uma imagem enviada pelo usuário, redimensiona a imagem para 32x32 pixels, normaliza os valores dos pixels e envia esses dados para o modelo treinado realizar a previsão.

## Fluxo de Funcionamento da API

Imagem enviada → API Flask → Pré-processamento → Modelo CNN (.h5) → Resultado da previsão
Estrutura Básica
modelo_cifar10.h5       # Modelo treinado
imagens/                # Pasta com imagens para teste
notebook.ipynb          # Código executado no Google Colab
README.md               # Documentação do projeto

## Como Executar no Google Colab

Abrir o projeto no Google Colab.
Executar a célula responsável por treinar o modelo CNN.
Salvar o modelo no formato .h5.
Executar a célula da API Flask.
Testar a API enviando uma imagem.
Verificar o resultado retornado pela API.

## Rota Principal

A rota principal da API apenas informa que o serviço está funcionando.

## GET /

Exemplo de retorno:
<h6>API CIFAR-10</h6>
<p>API funcionando!</p>

## Rota de Previsão

A rota /prever é responsável por receber a imagem e retornar a previsão feita pelo modelo.

POST /prever

A imagem deve ser enviada no campo:

imagem

## Exemplo de Retorno da API
{
  "classe_numero": 9,
  "classe_nome": "caminhão",
  "confianca": 0.91
}

## Teste com Várias Imagens

Também foi criado um código para percorrer todas as imagens de uma pasta e enviar cada uma delas automaticamente para a API.

Exemplo de funcionamento:
Imagem enviada: automóvel1.jpeg
{
  "classe_numero": 9,
  "classe_nome": "caminhão",
  "confianca": 0.9006
}

Esse processo permite testar várias imagens de uma vez, sem precisar enviar manualmente uma por uma.

## Observação sobre os Resultados

O modelo pode cometer erros de classificação, principalmente porque as imagens do CIFAR-10 possuem baixa resolução, com tamanho de 32x32 pixels. Além disso, imagens externas podem ter características diferentes das imagens usadas no treinamento.
Por exemplo, uma imagem chamada automóvel1.jpeg pode ser classificada como caminhão caso o modelo identifique características mais próximas dessa classe.
Isso não significa que a API está errada. A API apenas recebe a imagem, processa os dados e retorna a previsão feita pelo modelo treinado.

## Conclusão

Este projeto demonstra como uma Rede Neural Convolucional treinada com a base CIFAR-10 pode ser integrada a uma API em Python. A aplicação permite que imagens sejam enviadas para o modelo por meio de requisições HTTP, retornando a classe prevista e o nível de confiança da classificação.
Com isso, o projeto apresenta uma aplicação prática de Inteligência Artificial, unindo treinamento de modelo, salvamento em arquivo .h5, criação de API e consumo do serviço para reconhecimento de imagens.
