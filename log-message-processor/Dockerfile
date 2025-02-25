# Use an official Python runtime as the base image
FROM python:3.8

# Set the working directory
WORKDIR /app

# Install gcc and other necessary build tools
RUN apt-get update && \
    apt-get install -y gcc python3-dev build-essential && \
    apt-get clean

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
