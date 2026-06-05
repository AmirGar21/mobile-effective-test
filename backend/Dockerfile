FROM python:3.12-slim

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

RUN groupadd --system appgroup && \
    useradd --system \
             --gid appgroup \
             --home-dir /app \
             --shell /usr/sbin/nologin \
             appuser

WORKDIR /app

COPY --chown=appuser:appgroup server.py .

USER appuser

CMD ["python", "server.py"]