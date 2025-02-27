# Use an official Go runtime as the base image
FROM golang:1.21-alpine

# Set the working directory
WORKDIR /app

# Copy the Go module files
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy the rest of the application code
COPY . .

# Build the Go application
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o auth-api .

# Expose port 8080
EXPOSE 8080

# Run the application
CMD ["./auth-api"]
