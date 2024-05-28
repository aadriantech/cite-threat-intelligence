# Use the official Python image from the Docker Hub
FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements file from the docker/python directory into the container
COPY docker/python/requirements.txt .

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code from the docker/python directory into the container
COPY docker/python/ .

# Command to keep the container running
CMD ["tail", "-f", "/dev/null"]
