# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install system dependencies needed for OpenCV
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx \
    libglib2.0-0

# Upgrade pip to the latest version
RUN pip install --no-cache-dir --upgrade pip

# Install the required Python packages
RUN pip --default-timeout=100 install --no-cache-dir opencv-python flask

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define environment variable for Flask app
ENV FLASK_APP=Flask_FacialRecognition_WebService.py

# Run the Flask app when the container launches
CMD ["flask", "run", "--host=0.0.0.0"]

