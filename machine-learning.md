# 🧠 Documentação do Projeto de Aprendizado de Máquina – **Wenda**

## 🏔️ 1. Introdução e Contexto

A **Wenda** é uma plataforma inteligente de turismo que combina **dados, aprendizado de máquina e visualização interativa** para transformar a forma como viajantes e entidades do setor exploram Angola.

O objetivo central do componente de **Aprendizado de Máquina (ML)** é **analisar e prever comportamentos turísticos**, permitindo oferecer **recomendações personalizadas**, **previsões de demanda** e **insights estratégicos** para autoridades e operadores turísticos.

### 🎯 Objetivos principais:

* Criar um **sistema de recomendação** de destinos e experiências personalizadas.
* **Prever fluxos turísticos** com base em clima, eventos e histórico de viagens.
* **Segmentar viajantes** segundo padrões de comportamento e preferências.
* Apoiar **decisores públicos e empresas** na criação de políticas e campanhas baseadas em dados.

---

## 🧩 2. Preparação e Engenharia de Dados

A base de um bom modelo de aprendizado de máquina é um **pipeline de dados sólido, limpo e confiável**.
Nesta etapa, a Wenda implementa uma arquitetura de dados modular, focada em qualidade, rastreabilidade e segurança.

### 🔗 Fontes de Dados

* **Instituto Nacional de Estatística (INE Angola):** estatísticas oficiais de turismo.
* **OpenWeatherMap:** dados meteorológicos em tempo real e históricos.
* **OpenStreetMap:** geolocalização de pontos turísticos e infraestruturas.
* **Google Places API:** avaliações e popularidade de locais.
* **FlightRadar24:** movimentação aérea nacional e internacional.

### ⚙️ Processo de Coleta e Pipeline

O pipeline de dados é dividido em três camadas:

| Camada              | Descrição                                         | Ferramentas                     |
| ------------------- | ------------------------------------------------- | ------------------------------- |
| **Raw Layer**       | Dados brutos coletados de APIs e fontes externas. | Google Cloud Storage            |
| **Processed Layer** | Limpeza, normalização e validação.                | PostgreSQL + PostGIS            |
| **Model Layer**     | Dados transformados e prontos para treino.        | Pandas / Airflow / Scikit-learn |

### 🧰 Qualidade e Segurança

* Validação automática de schema e consistência.
* Versionamento de datasets com DVC.
* Criptografia de dados sensíveis.
* Backups diários e controle de acesso.

---

## 🤖 3. Modelagem e Treinamento

Nesta fase, são aplicadas técnicas de aprendizado supervisionado e não supervisionado para **recomendar destinos**, **prever fluxos turísticos** e **agrupar perfis de viajantes**.

### 🧮 Modelos Utilizados

| Tipo de Modelo            | Objetivo                                         | Técnicas                                         |
| ------------------------- | ------------------------------------------------ | ------------------------------------------------ |
| **Recomendação**          | Sugerir destinos e experiências personalizadas.  | Collaborative Filtering, Content-based Filtering |
| **Previsão de Demanda**   | Estimar o fluxo turístico em regiões e períodos. | Regressão Linear, Random Forest Regressor        |
| **Segmentação de Perfis** | Agrupar viajantes com comportamentos similares.  | K-Means, DBSCAN                                  |

### 🧠 Engenharia de Features

As features mais relevantes incluem:

* Dados climáticos e sazonalidade.
* Localização geográfica e distância média percorrida.
* Tipo de viajante (nacional/internacional).
* Categorias de atração (cultural, ecológica, gastronômica).
* Avaliações e sentimento em comentários.

### 🧬 Pipeline de Treinamento

1. Divisão em **train (70%)**, **validation (15%)** e **test (15%)**.
2. Normalização e encoding de variáveis categóricas.
3. Treinamento e avaliação automática via **MLflow**.
4. Armazenamento dos modelos e métricas para versionamento.

---

## 📊 4. Avaliação e Interpretação dos Resultados

### 📈 Métricas de Desempenho

| Tipo de Modelo   | Métricas                        |
| ---------------- | ------------------------------- |
| **Previsão**     | RMSE, R²                        |
| **Recomendação** | Precision@K, Recall@K, F1-score |
| **Segmentação**  | Silhouette Score                |

### 🔍 Interpretação dos Resultados

* Identificação dos **principais perfis de turistas** (cultural, de negócios, ecológico, gastronômico).
* Correlação entre **condições climáticas** e fluxo turístico.
* Ranking dinâmico das **atrações mais populares e bem avaliadas**.
* Insights visuais para gestores públicos e operadores.

### 💡 Explicabilidade

Para garantir transparência, o modelo inclui:

* Análise de importância de features.
* Visualização com **SHAP Values** e **Feature Importance Charts**.
* Painel interpretativo integrado ao dashboard da Wenda.

---

## 🚀 5. Conclusão e Próximos Passos

A integração de técnicas de aprendizado de máquina na Wenda representa um **avanço estratégico para o turismo angolano**, promovendo inovação, eficiência e melhores decisões baseadas em dados.

### ✅ Resultados Esperados

* Melhoria na experiência do viajante.
* Otimização de estratégias de marketing turístico.
* Apoio à formulação de políticas públicas informadas por dados.

### 🔭 Próximos Passos

1. Ampliar a base de dados para todas as províncias angolanas.
2. Integrar dados de transporte rodoviário e eventos locais.
3. Implementar *feedback loops* com dados reais de usuários.
4. Refinar os modelos com aprendizado contínuo (online learning).

### 🌍 Impacto Esperado

A Wenda torna-se um **sistema nacional de inteligência turística**, conectando dados, tecnologia e pessoas — um passo importante rumo a um ecossistema turístico digital e sustentável.

---
