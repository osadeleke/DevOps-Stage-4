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
# RUN pip3 install -r requirements.txt
RUN pip3 install redis==2.10.6 py_zipkin==0.11.0 requests


# Copy the rest of the application code
COPY . .

# Expose port 5000
EXPOSE 5000

# Run the application
CMD ["python", "main.py"]
