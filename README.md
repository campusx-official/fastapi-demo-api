# Learning FastAPI 🚀

A sandbox repo where I follow tutorials, build mini-projects, and capture my notes while exploring **[FastAPI](https://fastapi.tiangolo.com/)**.

## Why FastAPI?

- **Speed to code**: automatic input validation (Pydantic) & instant interactive docs (Swagger UI / ReDoc).
- **Performance**: Starlette + Uvicorn under the hood (ASGI, async all the way).
- **Modern ecosystem**: SQLAlchemy, async ORMs, OAuth2/JWT, Celery/Redis, Docker/Kubernetes—works out of the box.

## Why FastAPI *feels* fast

| Reason | What it means |
|--------|---------------|
| **Automatic validation** | Declare a Pydantic model once and FastAPI takes care of type-checking every request & response. |
| **Built-in docs** | Swagger UI & ReDoc are generated automatically via OpenAPI. |
| **Modern ecosystem** | Plays nicely with ML/DL libs, SQLAlchemy, Docker, K8s, etc. |

## Getting started

```bash
git clone https://github.com/campusx-official/fastapi-demo-api.git
cd learning-fastapi
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
