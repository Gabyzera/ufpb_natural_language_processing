# 🎭 Classificação de Textos com TF-IDF e Naive Bayes

## 🎢 Introdução
Essa atividade implementa um classificador de textos utilizando **TF-IDF** para transformação dos dados textuais e **Naive Bayes** para classificação. O objetivo é prever a categoria de um texto com base na frequência e relevância das palavras.

## 🗣️ Explicando melhor o modelo Naive Bayes
O **Naive Bayes** é um modelo probabilístico baseado no **Teorema de Bayes**, assumindo que as variáveis são independentes entre si.

### Como funciona?
1. Calcula a probabilidade de uma palavra aparecer em cada categoria com base no conjunto de treinamento.
2. Para um novo texto, multiplica-se as probabilidades das palavras presentes no documento para estimar a categoria mais provável.
3. Retorna a classe com maior probabilidade condicional.

## 🏛️ Como funciona o modelo?

### 🔹 TfidfVectorizer()

O **TF-IDF (Term Frequency - Inverse Document Frequency)** transforma textos em vetores numéricos considerando:
- **TF (Frequência do Termo):** quantas vezes uma palavra aparece no documento.
- **IDF (Frequência Inversa do Documento):** reduz a relevância de palavras muito comuns.

### 🔹 vectorizer.fit_transform(X_train)

- `fit_transform(X_train)`: aprende o vocabulário e estatística IDF dos textos no conjunto `X_train` e os transforma em uma matriz TF-IDF.
- A matriz gerada representa os textos de forma numérica, onde cada linha é um documento e cada coluna representa um termo ponderado pelo TF-IDF.

### 🔹 MultinomialNB()

- Modelo de **Naive Bayes**, amplamente utilizado para classificação de textos.
- Assume que as features (termos vetorizados pelo TF-IDF) seguem uma distribuição multinomial.

### 🔹 model.fit(X_train_vectorizer, y_train)

- Treina o modelo com os vetores TF-IDF (`X_train_vectorizer`) e os rótulos (`y_train`).
- Aprende padrões nos textos para classificar novas amostras.

## ⚙️ Como Executar o Projeto

1. Certifique-se de que o arquivo `B2W-Reviews01.csv` está no diretório correto.
2. Instale as dependências necessárias:
3. Execute o notebook no **Jupyter Notebook** ou **Google Colab**.