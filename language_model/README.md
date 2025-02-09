# 📖 Modelo de Trigramas com Método de Shannon

## 📌 Introdução
Este exercício implementa um **modelo de linguagem baseado em trigramas**, inspirado no método de **visualização de Shannon**. O objetivo é gerar frases a partir de um corpus de texto, analisando probabilidades de palavras com base nas duas palavras anteriores.

## 🔬 O que é o Método de Shannon?
Claude Shannon, considerado o "pai da teoria da informação", propôs que a linguagem poderia ser modelada estatisticamente, onde a probabilidade de uma palavra aparecer depende das palavras anteriores. Esse método permite gerar textos que imitam padrões linguísticos de um conjunto de dados fornecido.

## 📑 O que são Trigramas?
Trigramas são sequências de três palavras consecutivas. Nesse modelo, analisamos:
- Os dois primeiros termos são o **prefixo**.
- O terceiro termo é a **palavra prevista**.
- A **probabilidade condicional** de uma palavra aparecer é calculada com base nas ocorrências dentro do corpus.

## 🛠️ Tecnologias e Decisões do Projeto
- **Bibliotecas usadas**:
  - `nltk` para tokenização e stopwords.
  - `pandas` para manipulação de dados.

### 💡 Por que a escolha de algumas ferramentas?
**Os dados dos prompts estão em inglês**, então utilizamos:
   - `punkt` para tokenização correta das palavras.
   - `PorterStemmer()` pois é um stemmer mais adequado para a língua inglesa.

## 🚀 Exemplo de saída visual
O código gera uma visualização da estrutura dos trigramas:

```
(Prefixo) -> (Palavra Prevista) [Probabilidade]
('the', 'cat') -> 'sat' [0.30]
('cat', 'sat') -> 'on' [0.50]
```

## ✍️ Geração de Texto
O modelo pode gerar frases aleatoriamente a partir dos trigramas extraídos. Para isso, ele escolhe um par de palavras inicial e prevê a próxima palavra com base nas probabilidades calculadas.

### Exemplo de saída gerada pelo modelo:
```
come need help provid depth review includ pro con featur comparison technolog
```

O texto gerado pode variar conforme os dados de entrada e o modelo probabilístico treinado.