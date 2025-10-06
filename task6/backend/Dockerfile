FROM python:3.11-slim

# Рабочая директория
WORKDIR /app

# Копируем зависимости
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt || echo "No requirements.txt"

# Копируем код приложения
COPY . .

# Открываем порт 8081
EXPOSE 8081

# Запуск приложения
CMD ["python", "app.py"]
