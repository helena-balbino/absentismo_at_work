# Absenteeism at Work — Classificação Preditiva

## 📌 Descrição
Este projeto investiga o **absenteísmo no trabalho** utilizando o dataset público **Absenteeism at Work** (UCI Repository).  
O objetivo foi desenvolver um modelo de **Regressão Logística Multiclasse** capaz de classificar níveis de ausência (Nenhuma, Moderada, Alta) a partir de variáveis organizacionais, pessoais e laborais.

O estudo envolveu:  
- **Análise Exploratória (EDA):** compreensão da distribuição das ausências, padrões sazonais e correlações entre variáveis;  
- **Pré-processamento:** recategorização de motivos de ausência, normalização e codificação das variáveis;  
- **Modelagem:** comparação entre cenários com dados originais desbalanceados e dados balanceados via **SMOTE**;  
- **Avaliação:** uso de métricas como acurácia, precisão, recall, F1-score e matriz de confusão para cada classe.  

---

## 📊 Resultados
- O modelo inicial (dados originais, `class_weight=balanced`) apresentou acurácia de **59,5%**, com bom desempenho na classe **Moderada**, mas baixa precisão na classe **Nenhuma**.  
- Com o **SMOTE**, a acurácia global chegou a **61%**, e houve melhora nas classes minoritárias:  
  - Classe 0 (No Absence): F1 = 0,27, Recall = 0,67  
  - Classe 1 (Moderate Absence): F1 = 0,67  
  - Classe 2 (High Absence): F1 = 0,68  
- A comparação de acertos/erros evidenciou ganhos em todas as classes após o balanceamento.  

**Tabela comparativa (Original vs Balanceado):**

| Classe | Acertos (Original) | Erros (Original) | Acertos (Balanceado) | Erros (Balanceado) |
|--------|---------------------|------------------|-----------------------|--------------------|
| 0 (No Absence)   | 7   | 2  | 6  | 3  |
| 1 (Moderate)     | 45  | 38 | 48 | 35 |
| 2 (High)         | 36  | 20 | 37 | 19 |

---

## 📌 Conclusão
- A **Regressão Logística Multiclasse** mostrou-se eficaz e **interpretável**, ainda que com acurácia moderada.  
- O uso de **SMOTE** foi decisivo para melhorar o desempenho em classes menos representadas.  
- Apesar das limitações, o modelo fornece **insights acionáveis para gestão de pessoas**, permitindo identificar padrões de ausência e apoiar estratégias organizacionais.
