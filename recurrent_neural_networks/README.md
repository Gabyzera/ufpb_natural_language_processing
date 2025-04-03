# 📰 Classificador de Notícias com RNN

## 📢 Introdução
Este projeto demonstra a criação de um classificador de notícias utilizando uma Rede Neural Recorrente (RNN) implementada em PyTorch. O objetivo é classificar notícias em seis categorias: **business**, **entertainment**, **health**, **politics**, **sports** e **tech**. O dataset utilizado é o `okite97/news-data`.

## 🛠️ Pré-processamento e Preparação dos Dados
- **Conversão dos Rótulos:** As categorias de notícias são mapeadas para valores numéricos para serem usadas durante o treinamento.
- **Tokenização:** Os textos são convertidos para minúsculas e tokenizados utilizando o `nltk`.
- **Vocabulário:** Constrói-se um vocabulário considerando apenas os tokens com frequência mínima de 3 ocorrências e, em seguida, adiciona-se o token especial `<unk>` para palavras desconhecidas.
- **Criação do Dataset:** Uma classe customizada, `NewsDataset`, é definida para facilitar o uso com o `DataLoader` do PyTorch.

## 🏗️ Arquitetura do Modelo
O modelo possui a seguinte estrutura:
- **Camada de Embedding:** Converte os IDs dos tokens em vetores de dimensão 128.
- **RNN:** Uma rede recorrente com 2 camadas e 32 unidades ocultas, que processa as sequências de tokens para capturar informações contextuais.
- **Camada Linear:** Mapeia a última saída da RNN para as 6 classes do problema.

## 🔄 Treinamento e Avaliação
- **Função de Perda:** Utiliza-se a `CrossEntropyLoss` para medir o erro entre as predições e os rótulos.
- **Otimizador:** O otimizador **Adam** é empregado para atualizar os pesos do modelo.
- Durante o treinamento, os valores de loss para treino e teste são registrados e, ao final, são agrupados (por blocos de 1000 steps) para a visualização dos gráficos.