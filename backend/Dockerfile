FROM python:3.12-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .
RUN mkdir -p /app/website/public
RUN cp /app/admin.html /app/website/public/admin.html 2>/dev/null || true
RUN rm -f /app/.env
RUN chmod +x /app/start.sh

CMD ["/bin/sh", "/app/start.sh"]
