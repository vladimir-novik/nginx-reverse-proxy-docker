FROM nginx:1.25-alpine

# удалить дефолтный конфиг
RUN rm /etc/nginx/conf.d/default.conf

# создать пользователя
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# изменить права на нужные директории
RUN chown -R appuser:appgroup /var/cache/nginx /var/run /var/log/nginx

# переключиться на пользователя
USER appuser

COPY nginx.conf /etc/nginx/nginx.conf
