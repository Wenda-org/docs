**1. Machine Learning Backend (serviço de IA)**

Objetivo: treinar, atualizar e servir modelos preditivos e de recomendação.

| **Tecnologia**                      | Função

| **Python 3.x**                      | Linguagem principal do projeto — usado tanto no backend CRUD quanto no ML. 
| **FastAPI**                         | Framework para expor modelos treinados via endpoints REST e servir previsões em produção. 
| **scikit-learn**                    | Biblioteca para modelos clássicos (regressão, árvores, clustering) e pipelines. 
| **XGBoost / LightGBM**              | Modelos gradient boosting para previsão tabular e séries temporais. 
| **TensorFlow / PyTorch (opcional)** | Redes neurais (LSTM, Transformers) para previsões complexas e deep learning. 
| **pandas + numpy**                  | Manipulação, limpeza e transformação de dados para treino e inferência. 
| **Prophet / statsmodels**           | Modelos estatísticos e de séries temporais (ARIMA, Prophet) para forecasting. 
| **SHAP**                            | Interpretabilidade — explicar a contribuição das variáveis nas previsões. 
| **joblib / pickle**                 | Serialização/carregamento de modelos treinados para uso pela API. 

## ⚙️ **2. Backend CRUD e API principal**

### 👉 Objetivo: gerenciar os dados do sistema (usuários, destinos, eventos, avaliações, etc.) e integrar com o backend de ML.

| **Tecnologia** | Função |

| **Python 3.x** | Mesma linguagem para padronizar o stack e facilitar manutenção. |
| **FastAPI** | Framework para criar o backend principal (CRUD + autenticação + endpoints públicos). |
| **SQLAlchemy / Prisma (versão Python: Prisma Client Python)** | ORM para mapear modelos Python ↔️ tabelas SQL (ex: User, Destination Visit, etc.).
| **PostgreSQL** | Banco de dados principal — armazena usuários, locais, histórico, previsões e logs. |
| **PostGIS (extensão do PostgreSQL)** | Adiciona suporte geoespacial (coordenadas, distâncias, rotas). Essencial para turismo. |
| **Alembic** | Controle de migrações do banco de dados. |
| **Pydantic** | Validação de dados nas requisições e respostas das APIs. |
| **Redis (opcional)** | Cache de previsões e recomendações, para respostas rápidas. |
| **Celery + Redis** | Agendamento e execução assíncrona de tarefas (ex: reentreinar modelo, enviar notificações). |
| **Docker / Docker Compose** | Empacotar e rodar todos os serviços (DB, APIs, etc.) facilmente. |
| **Pytest / pytest-asyncio** | Testes automatizados das APIs e dos modelos. |

---

## 💻 **3. Painel Web (Frontend administrativo)**

### 👉 Objetivo: painel interativo para o governo, agências e gestores turísticos.

| Tecnologia | Função |
| ----------------------------- | -------------------------------------------------------------------------------- |
| **Next.js (React framework)** | Framework para o frontend web — traz SSR, rotas automáticas e otimização de SEO. |
| **TypeScript** | Segurança de tipos e manutenção mais fácil. |
| **Tailwind CSS** | Estilização rápida e moderna, com design responsivo. |
| **Recharts / Chart.js** | Visualização de dados e previsões (gráficos, séries, comparações). |
| **Leaflet / Mapbox GL JS** | Mapas interativos com POIs, calor de turistas e rotas. |
| **Axios / Fetch API** | Comunicação com o backend FastAPI. |
| **Next Auth (ou JWT)** | Autenticação e proteção de rotas do painel. |
| **Framer Motion (opcional)** | Animações suaves para UI moderna. |

---

## 📱 **4. Aplicativo Mobile (para turistas)**

### 👉 Objetivo: app de recomendação e exploração turística em tempo real.

| Tecnologia | Função |
| ----------------------------------- | ----------------------------------------------------------------------------- |
| **React Native (Expo)** | Framework para criar o app mobile (Android e iOS) usando o mesmo código base. |
| **TypeScript** | Tipagem e integração com APIs segura. |
| **Axios / Fetch** | Consome a API principal (FastAPI). |
| **React Navigation** | Navegação entre telas. |
| **MapView (react-native-maps)** | Exibir mapas e locais turísticos. |
| **AsyncStorage / SQLite** | Armazenamento local de favoritos, cache offline. |
| **Tailwind (NativeWind)** | Estilização responsiva e moderna no app. |
| **Firebase / OneSignal (opcional)** | Push notifications para eventos e promoções. |

---

## 🧩 **5. Infraestrutura e DevOps**

| Tecnologia | Função |
| --------------------------------------------- | -------------------------------------------------- |
| **Docker & Docker Compose** | Containerizar os serviços (APIs, DB, ML). |
| **NGINX** | Proxy reverso e balanceamento de carga. |
| **Git + GitHub / GitLab** | Versionamento de código. |
| **GitHub Actions / GitLab CI** | CI/CD para build, testes e deploy automático. |
| **Render / Railway / DigitalOcean / AWS EC2** | Hospedagem da aplicação e banco de dados. |
| **MLflow (opcional)** | Rastreamento de experimentos e versões de modelos. |
| **Prometheus + Grafana (opcional)** | Monitoramento de desempenho da API e do ML. |

---

## 🔐 **6. Segurança e autenticação**

| Tecnologia | Função |
| -------------------------------- | ------------------------------------------------------ |
| **JWT (JSON Web Token)** | Autenticação de usuários (turistas, admins, agências). |
| **OAuth2 / Google Sign-in** | Login rápido via contas externas. |
| **HTTPS (SSL)** | Comunicação segura entre cliente e servidor. |
| **CORS, Rate Limiting, Logging** | Boas práticas para proteger a API pública. |

---

## 🌐 **7. Dados e Geoinformação**

| Fonte / Tecnologia | Função |
| ------------------------------------ | --------------------------------------------------- |
| **INE Angola** | Dados oficiais sobre chegadas, ocupação, destinos. |
| **OpenStreetMap (via Overpass API)** | Pontos turísticos, rotas, coordenadas e categorias. |
| **GeoPandas / Shapely** | Manipulação e análise de dados geográficos. |
| **Google Places API (opcional)** | Dados complementares de locais e reviews. |
