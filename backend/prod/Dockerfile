# Use official Python base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy requirements first to leverage Docker cache
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application
COPY . .

# Environment variables
ENV FLASK_APP=app.py
ENV FLASK_ENV=production

# Expose port
EXPOSE 3002

# Run the application using Gunicorn for production
RUN pip install gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:3002", "app:app"]
