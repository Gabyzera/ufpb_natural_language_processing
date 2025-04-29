# 👩‍⚕️ Classificador de Sintomas

## 📌 Introdução  
Este projeto implementa um **classificador de texto** que recebe descrições de sintomas médicos em linguagem natural e sugere a especialidade médica mais adequada. Usamos técnicas de NLP (tokenização, padding e one-hot) e o modelo CNN 1D para aprender padrões estatísticos em sequências de palavras.

---

## 🚧 Problema  
- **Entrada**: texto livre com queixa do paciente.  
- **Saída**: rótulo de especialidade médica (exemplo: Cardiology, Dermatology, …).  
- **Desafios**:  
  - Classes de frequência muito desigual (long tail) 
  - Vocabulário médico variado e ambíguo  
  - Frases curtas sendo necessário o uso de OOV (out-of-vocabulary)  

---

## 📑 Pipeline do Projeto  

1. **Carregamento e Limpeza**  
   - Leitura do CSV (`medquad.csv`)  
   - Descarte de registros com valores nulos  
2. **Agrupamento de Classes Raras**  
   - Classes com < 7 exemplos → `Other speciality`  
3. **Pré-processamento de Texto**  
   - Lowercase + remoção de pontuação  
   - Remoção de stopwords (NLTK)  
4. **Tokenização e Padding**  
   - Vocabulário: 50 000 tokens mais frequentes
   - OOV token
   - Sequência fixada em 100 tokens (padding/truncamento)  
5. **Codificação de Rótulos**  
   - `LabelEncoder` → inteiros  
   - `to_categorical` → one-hot vectors  
6. **Modelo CNN 1D**  
   - Embedding (100d) → Conv1D (128 × 5) → GlobalMaxPooling → Dense(64) → Dropout → Softmax  
   - Otimizador: Adam; Loss: categorical_crossentropy  
   - Callbacks: EarlyStopping (patience=3)  
7. **Avaliação e Visualização**  
   - Curvas de treino vs. validação (loss & accuracy)  
   - Classification report & Matriz de Confusão (top-10 classes)  
8. **Predição Interativa**  
   - Função `predizer(prompt)` retorna top-3 especialidades com maior  probabilidade de condizer com o sintoma médico do paciente

---

## 🧩 Tecnologias e Dependências  
- **NLP**: `nltk` (stopwords, tokenização)  
- **Pré-processamento**: `numpy`, `pandas`  
- **Deep Learning**: `tensorflow` / `keras`  
- **Visualização**: `matplotlib`, `seaborn`  
- **Balanceamento**: `imblearn` (SMOTE, ADASYN)  