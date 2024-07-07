FROM python:3.9 AS build

ENV PYTHON_ENV=production

WORKDIR /app/backend

COPY pyproject.toml poetry.lock ./

RUN pip install poetry

RUN poetry install

COPY . .

RUN chmod +x /app/backend/prestart.sh

EXPOSE 8000

CMD ["./prestart.sh", "&&", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
