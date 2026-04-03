FROM python:3.11-slim

WORKDIR /app

# копируем только нужное
COPY app.py .

# не root пользователь
RUN useradd -m appuser
USER appuser

# документируем порт
EXPOSE 8080

# healthcheck
HEALTHCHECK --interval=30s --timeout=3s CMD python -c "import urllib.request; urllib.request.urlopen('http://localhost:8080/', timeout=2)"

CMD ["python", "app.py"]
