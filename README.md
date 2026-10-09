# 📊 Segmentação de Clientes e Redução de Dimensionalidade (PCA + K-Means)

Este projeto aplica técnicas avançadas de Ciência de Dados e Aprendizado Não Supervisionado para resolver um desafio clássico de marketing e e-commerce: **segmentar uma base de clientes com alta dimensionalidade para personalizar estratégias de conversão e retenção.**

---

## 🎯 O Problema de Negócio

Uma empresa de e-commerce possui uma base de dados rica com 2.240 registros e dezenas de atributos demográficos, comportamentais e financeiros[cite: 1]. 

* **Desafio:** A quantidade excessiva de atributos gera alta correlação e ruído estatístico, dificultando o agrupamento claro de clientes.
* **Objetivo:** Aplicar **PCA (Principal Component Analysis)** para reduzir o espaço dimensional preservando a maior parte da variância dos dados, e utilizar o algoritmo **K-Means** para definir personas acionáveis de marketing[cite: 5, 8].

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

* **Linguagem:** Python
* **Ambiente:** Jupyter Notebook
* **Manipulação de Dados:** Pandas, NumPy
* **Visualização:** Matplotlib, Seaborn
* **Machine Learning & Estatística:** Scikit-Learn (`StandardScaler`, `PCA`, `KMeans`, `silhouette_score`)

---

## 🚀 Metodologia Executada

1. **Tratamento & Feature Engineering:**
   * Imputação de nulos (`Renda` ajustada pela mediana)[cite: 1].
   * Remoção de atributos sem variância/identificadores (`ID`, `Z_CostContact`, `Z_Revenue`)[cite: 1].
   * Tratamento de outliers em renda e idade[cite: 1].
   * Criação de novas variáveis de negócio: `Idade`, `Idade_conta`, `Total_Gastos`, `Total_Filhos` e `Total_Compras`.
   * Aplicação de **One-Hot Encoding** nas categóricas, totalizando 38 colunas numéricas[cite: 4].

2. **Padronização:**
   * Utilização do `StandardScaler` (Média = 0, Desvio Padrão = 1), garantindo a premissa matemática do PCA[cite: 4].

3. **Redução de Dimensionalidade (PCA):**
   * Análise do **Scree Plot** da variância explicada acumulada[cite: 5].
   * Seleção de **18 Componentes Principais (PCs)**, garantindo a preservação de **80% de toda a variância dos dados** e eliminando a multicolinearidade[cite: 4, 5].

4. **Clustering & Modelagem (K-Means):**
   * Definição da quantidade ideal de grupos utilizando o **Método do Cotovelo (Elbow Method)** e o **Silhouette Score**[cite: 6, 7].
   * Agrupamento em **K = 4 Clusters**, trazendo equilíbrio entre coesão estatística e viabilidade estratégica[cite: 7, 8].

---

## 📈 Resultados & Personas Encontradas

A redução no espaço das componentes principais permitiu identificar 4 perfis bem definidos de consumidores[cite: 8, 9]:

| Cluster | Nome da Persona | Renda Média | Gasto Médio | Filhos | Ação Estratégica Recomendada |
|:---:|:---:|:---:|:---:|:---:|:---|
| **0** | **Massa Econômica**[cite: 9] | R$ 35.019,27[cite: 9] | R$ 94,95[cite: 9] | 1,23[cite: 9] | Cupons de desconto, frete grátis e produtos de entrada[cite: 9]. |
| **1** | **Alto Valor Consolidado**[cite: 9] | R$ 73.160,66[cite: 9] | R$ 1.264,01[cite: 9] | 0,24[cite: 9] | E-mail marketing personalizado e lançamentos de marcas *premium*[cite: 9]. |
| **2** | **Engajados Família**[cite: 9] | R$ 57.124,74[cite: 9] | R$ 712,55[cite: 9] | 1,23[cite: 9] | Programas de cashback e ofertas em pacotes familiares[cite: 9]. |
| **3** | **Champions VIP**[cite: 9] | R$ 81.358,91[cite: 9] | R$ 1.635,31[cite: 9] | 0,17[cite: 9] | Atendimento exclusivo, acesso antecipado e clube de fidelidade fechado[cite: 9]. |

## 📂 Como Executar este Projeto

```bash
# Clonar o repositório
git clone [https://github.com/taymarinho700/portfolio-pca-customer-segmentation.git](https://github.com/taymarinho700/portfolio-pca-customer-segmentation.git)
