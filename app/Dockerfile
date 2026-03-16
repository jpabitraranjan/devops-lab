# Use lightweight Python base image
FROM python:3.12-slim

# Set working directory inside container
WORKDIR /app

# Copy application code
COPY . .

# Install dependencies
RUN pip install --no-cache-dir flask redis gunicorn

# Environment variable for Redis host (Docker Compose will override)
ENV REDIS_HOST=redis

# Expose Flask port
EXPOSE 8000

# Run the application using Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "app:app"]