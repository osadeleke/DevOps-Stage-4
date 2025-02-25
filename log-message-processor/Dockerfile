# Use an official Python runtime as the base image
FROM python:3.8

# Set the working directory
WORKDIR /app

# Install some system dependencies
RUN apt update && apt install -y \
    build-essential \
    python3-dev \
    gcc \
    && rm -rf /var/lib/apt/lists/*

# Copy requirements.txt
COPY requirements.txt .

# Install dependencies
RUN pip install -r requirements.txt

# Copy the rest of the application code
COPY . .

# Expose port 5000
EXPOSE 5000

# Run the application
CMD ["python", "main.py"]
