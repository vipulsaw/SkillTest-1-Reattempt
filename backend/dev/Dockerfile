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
ENV FLASK_ENV=development

# Expose port
EXPOSE 3001

# Run the application
CMD ["flask", "run", "--host=0.0.0.0", "--port=3001"]
