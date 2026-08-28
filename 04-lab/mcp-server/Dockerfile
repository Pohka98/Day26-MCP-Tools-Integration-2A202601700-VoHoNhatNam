# Use Python 3.12 slim image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy dependency files
COPY pyproject.toml ./

# Install dependencies
RUN pip install --no-cache-dir -e .

# Copy application code
COPY weather.py ./

# Khớp với cổng mặc định trong weather.py: int(os.getenv("PORT", 8085)).
# Cloud Run tự đặt biến PORT nên sẽ ghi đè giá trị này khi deploy.
EXPOSE 8085

# Set environment variables
ENV PYTHONUNBUFFERED=1

# Run the application
CMD ["python", "weather.py"]
