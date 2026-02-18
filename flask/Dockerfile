# Use official Python image
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy requirements first (better caching)
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy rest of the application
COPY . .

# Expose port
EXPOSE 5000

# Start with Gunicorn
CMD ["gunicorn", "app:app", "--bind", "0.0.0.0:5000"]
