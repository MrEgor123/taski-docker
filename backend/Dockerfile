# backend/Dockerfile

FROM python:3.9

WORKDIR /app

# Устанавливаем gunicorn для работы с приложением Django
RUN pip install gunicorn==20.1.0

# Копируем requirements.txt и устанавливаем зависимости
COPY requirements.txt .
RUN pip install -r requirements.txt --no-cache-dir

# Копируем все файлы из текущего каталога в контейнер
COPY . .

# Запускаем Gunicorn для Django приложения
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
