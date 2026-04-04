# DevOps Test Task

## Описание

Простое веб-приложение, доступное через nginx (reverse proxy), развернутое с помощью Docker и Docker Compose.

Схема работы:

User → nginx → backend

- nginx принимает HTTP-запросы на порт 80
- nginx проксирует запросы на backend-сервис
- backend — простой HTTP-сервер на Python
- backend доступен только внутри Docker-сети

---

## Как запустить проект

1. Убедитесь, что установлены:
   - Docker
   - Docker Compose

2. Клонируйте репозиторий:
```bash
	git clone <https://github.com/vladimir-novik/nginx-reverse-proxy-docker>
	cd nginx-reverse-proxy-docker
```

3. Запустите проект:
```bash
	docker-compose up --build
```

---

## Как проверить результат

После запуска выполните команду: 
```bash
	curl http://localhost
```

Также можно открыть в браузере: http://localhost
Ожидаемый ответ: Hello from Effective Mobile!

---

## Как работает схема nginx -> backend

1. Пользователь отправляет запрос на localhost:80
2. Запрос попадает в nginx
3. nginx проксирует запрос на backend (внутри Docker-сети)
4. backend обрабатывает запрос и возвращает ответ
5. nginx возвращает ответ пользователю
