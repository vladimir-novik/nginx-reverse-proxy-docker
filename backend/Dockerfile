FROM python:3.11-slim

WORKDIR /app

# не root пользователь
RUN useradd -m appuser
USER appuser

# копируем только нужное
COPY app.py .

# документируем порт
EXPOSE 8000

# healthcheck
HEALTHCHECK --interval=30s --timeout=3s CMD python -c "import urllib.request; urllib.request.urlopen('http://localhost:8000/')"

CMD ["python", "app.py"]
