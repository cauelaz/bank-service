# 💰 Bank Service API

API de gerenciamento bancário desenvolvida com FastAPI, PostgreSQL, Alembic e Docker.

---

## 🚀 Tecnologias

- [FastAPI](https://fastapi.tiangolo.com/)
- [SQLAlchemy](https://www.sqlalchemy.org/)
- [Alembic](https://alembic.sqlalchemy.org/)
- [Databases](https://www.encode.io/databases/)
- [Docker](https://www.docker.com/)
- [PostgreSQL](https://www.postgresql.org/)
- [Pydantic v2 + pydantic-settings](https://docs.pydantic.dev/latest/)

---

## 🗂️ Estrutura do Projeto

```BASH
bank-service/
├── alembic/ # Migrations
├── src/
│ ├── controllers/ # Rotas
│ ├── models/ # Modelos ORM
│ ├── schemas/ # Pydantic schemas
│ ├── services/ # Lógica de negócios
│ ├── views/ # Integrações externas ou front
│ ├── config.py # Configuração via .env
│ ├── database.py # Engine e metadata
│ └── main.py # Entry point da aplicação
├── .env # Configs de produção
├── .env.homolog # Configs para homologação SQLite
├── alembic.ini
├── requirements.txt
├── docker-compose.yml
└── Dockerfile
```


---

## ⚙️ Variáveis de Ambiente

### Produção 

```env
database_url=postgresql://usuario:senha@db:5432/nome_db
environment=production
```
### Homologação

```.env
database_url=sqlite:///homolog.db
environment=homolog
```
## 🐳 Docker

Subindo a aplicação com Docker:
```bash
docker-compose up --build
```
A API estará acessível em:
```bash
http://localhost:8000
```

### 📦 Migrations com Alembic

Criar nova migration:
```bash
ENV_FILE=.env alembic revision --autogenerate -m "mensagem"
```
Aplicar migrations:
```bash
ENV_FILE=.env alembic upgrade head
```

### 📚 Documentação da API

Após subir o serviço, acesse:
```bash
http://localhost:8000/docs
```