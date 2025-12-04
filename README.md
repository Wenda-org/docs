# 🌍 Wenda — Smart Tourism Platform in Angola

**Wenda** is a digital platform that leverages **Machine Learning** and **geospatial data analysis** to strengthen the tourism industry in Angola.
The name **Wenda** comes from *Umbundu* and means *“journey”*.

The project’s mission is to **boost the tourism sector** by supporting **public managers, businesses, and travelers** with insights, forecasts, and personalized recommendations.

---

## 🚀 Overview

Wenda combines technology, data, and artificial intelligence to:

* **Predict tourism demand** across different regions of the country
* **Help managers and agencies** make data-driven decisions
* **Provide personalized recommendations** to travelers through a mobile app
* **Centralize information** about destinations, events, and tourism services

The platform is divided into three main components:

| Component                           | Description                                                                                                                |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Web Dashboard (Wenda Dashboard)** | Administrative interface for government and tourism operators — displays charts, forecasts, interactive maps, and reports. |
| **Mobile App (Wenda App)**          | App for tourists to discover attractions, generate smart itineraries, and receive AI-driven recommendations.               |
| **Backend Services (APIs)**         | Set of Python-based APIs — one focused on CRUD operations and another dedicated to Machine Learning.                       |

---

## 🧱 Platform Structure

```
wenda/
│
├── docs/                      # Current repository: technical and functional documentation
│   ├── README.md              # Project overview
│   ├── report_english.pdf     # Project report (english version) for submission (20th)
│   ├── report_portuguese.pdf  # Project report (portuguese version) for submission (20th)
│   ├── deployment.md          # Describes how Wenda's machine learning system will be implemented and put into production (24th)
│   ├── api-design.md          # API structure and endpoints
│   ├── data-model.md          # Data model and database schema
│   ├── machine-learning.md    # Machine Learning Project Documentation (24th)
│   └── roadmap.md             # Development roadmap and milestones
│
├── backend-core/              # Main backend (CRUD, authentication, public APIs)
├── backend-ml/                # Machine Learning service (predictions and recommendations)
├── web/                       # Web dashboard (Next.js)
├── mobile/                    # Mobile app (React Native)
└── docker-compose.yml         # Containers and service configuration
```

---

## 🧠 Tech Stack

**Backend (Python)**

* FastAPI • SQLAlchemy • PostgreSQL + PostGIS
* pandas • scikit-learn • XGBoost • SHAP
* Celery • Redis (asynchronous tasks)
* Docker • Alembic • Pytest

**Web Frontend**

* Next.js (React) • TypeScript • Tailwind CSS
* Recharts • Leaflet • NextAuth

**Mobile App**

* React Native (Expo) • TypeScript • NativeWind
* Axios • react-native-maps

**Infrastructure & DevOps**

* Docker & Docker Compose
* NGINX • GitHub Actions (CI/CD)
* Render / Railway / DigitalOcean

---

## 📊 Data & Sources

Wenda integrates multiple data sources to generate insights, forecasts, and recommendations:

* **INE Angola** — Tourism Statistical Yearbook (official arrival and occupancy data)
* **OpenStreetMap** — Tourist attractions, roads, and coordinates
* **GeoPandas / Shapely** — Geospatial data processing
* **External APIs (optional)** — Google Places, events, flights, and hotels

---

## 🧩 Technical Documentation

| Document                                 | Description                                              |
| ---------------------------------------- | -------------------------------------------------------- |
| [`architecture.md`](./architecture.md)   | System structure and component diagrams                  |
| [`api-design.md`](./api-design.md)       | REST endpoints and authentication flows                  |
| [`data-model.md`](./data-model.md)       | Entity structure and database relationships              |
| [`ml-models.md`](./ml-models.md)         | Description of ML models for forecasting and recommender |
| [`roadmap.md`](./roadmap.md)             | Development timeline and milestones                      |
| [`ui-wireframes.md`](./ui-wireframes.md) | Interface wireframes and design guidelines               |

---

## 🌱 Main Objectives

1. Forecast tourism demand by province and season
2. Identify visitor profiles and behavior patterns
3. Provide smart, personalized recommendations to travelers
4. Support public policy and strategic planning for tourism

---

## 🤝 Team

| Role                         | Name         |
| ---------------------------- | ------------ |
| Technical Lead / Backend ML  | (Add member) |
| Technical Lead / Backend API | (Add member) |
| Web Frontend Developer       | (Add member) |
| Mobile Developer             | (Add member) |
| Data & Research              | (Add member) |
| Design & UX                  | (Add member) |

---

## 📅 Project Status

* [x] Concept definition and architecture
* [x] Tech stack planning
* [x] Data collection and structuring
* [x] Backend service development
* [x] Web dashboard prototype
* [x] Mobile app prototype
* [x] ML model training
* [ ] Deployment and integration testing

---

## 📫 Contact

For questions, suggestions, or collaborations:
📧 **[equipa.wenda@gmail.com](mailto:equipa.wenda@gmail.com)**
🌐 *Coming soon: [wenda.ao](https://wenda.ao)*

---
