# 🚀 Documentação da Implantação – **Wenda**

## 🌍 1. Visão Geral da Implantação

A implantação do sistema de **Aprendizado de Máquina da Wenda** tem como objetivo **disponibilizar modelos treinados e pipelines de dados de forma escalável, segura e monitorável**, integrando-os à plataforma principal (web e mobile).

O processo de deployment foi projetado para garantir:

* **Disponibilidade contínua** dos serviços de recomendação e previsão.
* **Integração transparente** entre o backend CRUD (Next.js + FastAPI) e o backend de ML (Python).
* **Escalabilidade horizontal**, permitindo o aumento de carga conforme a demanda de usuários.
* **Monitoramento e versionamento** dos modelos e dados em tempo real.

---

## 🧱 2. Arquitetura de Implantação

A arquitetura de implantação da Wenda segue um modelo modular, dividido em camadas independentes, interconectadas por APIs REST.

### 🧩 Componentes Principais

| Camada                       | Tecnologia                                         | Função                                                        |
| ---------------------------- | -------------------------------------------------- | ------------------------------------------------------------- |
| **Frontend Web**             | Next.js + TailwindCSS                              | Interface para administradores e operadores turísticos.       |
| **App Mobile**               | React Native + Expo                                | Aplicativo para visitantes e viajantes.                       |
| **Backend CRUD**             | Python (FastAPI) + PostgreSQL                      | Gerencia entidades (usuários, destinos, reservas, feedbacks). |
| **Backend ML**               | Python (Flask/FastAPI) + Scikit-learn + MLflow     | Servidor responsável pelas predições e recomendações.         |
| **Banco de Dados**           | PostgreSQL + PostGIS                               | Armazenamento de dados estruturados e geoespaciais.           |
| **Armazenamento de Modelos** | MLflow + DVC + Google Cloud Storage                | Versionamento e armazenamento seguro de modelos e datasets.   |
| **Infraestrutura de Deploy** | Docker + Docker Compose + Nginx + Google Cloud Run | Containerização e execução em ambiente escalável.             |
| **Monitoramento**            | Prometheus + Grafana                               | Coleta de métricas e monitoramento de performance.            |

---

## ⚙️ 3. Pipeline de Implantação

O processo de deployment segue uma abordagem **CI/CD (Integração e Entrega Contínua)**, garantindo automação desde o commit até o deploy final.

### 🔄 Etapas do Pipeline

1. **Desenvolvimento e Treinamento Local**

   * Desenvolvimento e testes de modelos localmente.
   * Treinamento com notebooks e scripts versionados.

2. **Versionamento e Testes**

   * Armazenamento dos modelos e métricas no MLflow.
   * Testes unitários automáticos (pytest).
   * Validação de integridade dos dados com DVC.

3. **Containerização**

   * Criação de imagens Docker para cada serviço (backend CRUD e ML).
   * Teste local com Docker Compose.

4. **Deploy em Produção**

   * Deploy dos containers no **Google Cloud Run**.
   * Configuração de Nginx como proxy reverso.
   * Integração contínua via GitHub Actions.

5. **Monitoramento e Logs**

   * Monitoramento de uso e performance (Prometheus + Grafana).
   * Alertas de falhas ou lentidão.
   * Logging centralizado via Google Cloud Logging.

---

## 🔐 4. Segurança e Acesso

### 🧱 Mecanismos Implementados

* Autenticação e autorização via JWT (JSON Web Tokens).
* Criptografia SSL/TLS entre todos os serviços.
* Controle de permissões em endpoints sensíveis.
* Armazenamento seguro de chaves e segredos com Google Secret Manager.

---

## 🧩 5. Integração entre os Módulos

### 🔁 Fluxo de Comunicação

1. O **frontend web** envia requisições para o **backend CRUD** (FastAPI).
2. O backend CRUD chama o **serviço de ML** via API REST para obter predições e recomendações.
3. O **backend ML** processa a requisição, carrega o modelo versionado mais recente (via MLflow) e retorna o resultado.
4. O **frontend mobile** exibe as recomendações personalizadas para o usuário.

### 🌐 Exemplo de Fluxo de API

```
Frontend → Backend CRUD → Backend ML → Modelo → Backend CRUD → Frontend
```

---

## 🧠 6. MLOps e Monitoramento

Para garantir a confiabilidade e evolução contínua dos modelos, a Wenda adota práticas de **MLOps (Machine Learning Operations)**:

| Área                         | Ferramenta           | Função                                               |
| ---------------------------- | -------------------- | ---------------------------------------------------- |
| **Versionamento de Modelos** | MLflow               | Rastreia experimentos, métricas e versões.           |
| **Versionamento de Dados**   | DVC                  | Mantém histórico e integridade de datasets.          |
| **CI/CD**                    | GitHub Actions       | Automatiza build, testes e deploy.                   |
| **Monitoramento**            | Prometheus + Grafana | Monitora desempenho e uso dos modelos.               |
| **Feedback Loop**            | API Logs + Banco     | Coleta dados reais de interação para re-treinamento. |

---

## 🧩 7. Plano de Manutenção e Atualização

### 🕒 Frequência

* **Semanal:** checagem de integridade de dados e logs.
* **Mensal:** reavaliação de performance dos modelos.
* **Trimestral:** re-treinamento dos modelos com novos dados.

### 🔄 Processo de Atualização

1. Atualização dos datasets.
2. Novo treinamento e validação.
3. Registro de nova versão no MLflow.
4. Deploy automatizado com rollback disponível.

---

## 🧭 8. Considerações Finais

A implantação da Wenda foi estruturada para garantir **confiabilidade, escalabilidade e adaptabilidade**.
O uso de **Docker, MLflow e CI/CD** permite uma integração fluida entre a ciência de dados e o ambiente de produção, transformando o aprendizado de máquina em **valor real para o ecossistema turístico angolano**.

A arquitetura final é **moderna, modular e sustentável**, pronta para evoluir com novas fontes de dados, modelos mais avançados e integração com APIs governamentais ou privadas no futuro.

---