# Reconhecimento de Atividades Humanas com Redes Neurais

---

#### Prova da Unidade 3 — Redes Neurais Artificiais
**Professora:** [Rosana Cibely](https://github.com/roscibely)  
**Instituição:** UFERSA — Campus Pau dos Ferros

---

## Sobre o projeto

Este projeto desenvolve modelos de redes neurais recorrentes para classificar atividades humanas a partir de dados de sensores de movimento. Foram implementadas e avaliadas duas arquiteturas: **BiLSTM (Bidirectional LSTM)** e **GRU (Gated Recurrent Unit)**.

## Base de dados

Foi utilizado o conjunto **Human Activity Recognition Using Smartphones (UCI HAR)**, disponibilizado no repositório da UCI:

[Human Activity Recognition Using Smartphones — UCI](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)

Os dados foram coletados por meio dos sensores de acelerômetro e giroscópio de smartphones. O problema contempla seis atividades:

| Classe | Atividade |
|---|---|
| 1 | WALKING |
| 2 | WALKING_UPSTAIRS |
| 3 | WALKING_DOWNSTAIRS |
| 4 | SITTING |
| 5 | STANDING |
| 6 | LAYING |

## Modelos implementados

### BiLSTM

A arquitetura utiliza duas camadas LSTM bidirecionais, com camadas Dropout para reduzir o overfitting, uma camada densa intermediária e uma camada de saída com ativação Softmax.

- Camadas recorrentes: BiLSTM com 64 e 32 unidades.
- Regularização: Dropout de 0,3.
- Otimizador: Adam.
- Taxa de aprendizado: 0,001.
- Função de perda: Sparse Categorical Crossentropy.
- Total de parâmetros: 87.750.

**Resultados no conjunto de teste:**

| Métrica | Resultado |
|---|---:|
| Acurácia | 89,41% |
| Loss | 0,4312 |
| Precisão (macro) | 90,23% |
| Recall (macro) | 89,16% |
| F1-score (macro) | 89,38% |

### GRU

A arquitetura é composta por duas camadas GRU, intercaladas com Dropout, uma camada densa intermediária e uma camada de saída Softmax para as seis classes.

- Camadas recorrentes: GRU com 64 e 32 unidades.
- Regularização: Dropout de 0,3.
- Otimizador: Adam.
- Taxa de aprendizado: 0,001.
- Função de perda: Sparse Categorical Crossentropy.
- Entrada do modelo: sequências com dimensão 128 × 9.
- Total de parâmetros: 25.062.

**Resultados no conjunto de teste:**

| Métrica | Resultado |
|---|---:|
| Acurácia | 90,13% |
| Loss | 0,3174 |
| Precisão (macro) | 90,22% |
| Recall (macro) | 90,37% |
| F1-score (macro) | 90,26% |

## Avaliação

O desempenho dos modelos foi analisado por meio de métricas de classificação e matrizes de confusão. Também foram gerados gráficos de acurácia e perda durante o treinamento e a validação.

Com os resultados obtidos nos notebooks, a GRU apresentou a maior acurácia no teste (90,13%), enquanto a BiLSTM alcançou 89,41%. Os resultados correspondem às configurações e aos procedimentos de cada implementação.

## Arquivos

| Arquivo | Descrição |
|---|---|
| `human_activity_bilstm.ipynb` | Implementação e avaliação do modelo BiLSTM |
| `human_activity_GRU.ipynb` | Implementação e avaliação do modelo GRU |

## Tecnologias utilizadas

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

## Como executar

1. Abra um dos notebooks no Google Colab.
2. Execute as células na ordem apresentada.
3. Realize o download e o processamento da base de dados conforme indicado no notebook.
4. Treine o modelo e visualize as métricas, os gráficos e a matriz de confusão.

## Equipe

- [Francisca Lorrayne de Lima Santos](https://github.com/franciscalorraynes)
- [Samira Aquino](https://github.com/samirafq)

---

**Disciplina:** Redes Neurais Artificiais  
**Avaliação:** Prova da Unidade 3
