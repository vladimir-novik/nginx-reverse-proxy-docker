FROM nginx:1.25-alpine

# Удаляем дефолтный конфиг nginx
RUN rm -f /etc/nginx/conf.d/default.conf

# Копируем свой конфиг
COPY nginx.conf /etc/nginx/nginx.conf
