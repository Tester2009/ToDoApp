# Use an official Python runtime as a parent image
FROM python:3.9.0-slim

# Set metadata for the image
LABEL maintainer="Hakase <tester2009.hakase@gmail.com>"
LABEL version="1.0"
LABEL description="A simple Python application"

# Set the working directory in the container
WORKDIR /api-flask

# Copy the necessary files and directories into the container
COPY app.py /api-flask/
COPY requirements.txt /api-flask/
COPY .env /api-flask/

# Upgrade pip and install Python dependencies
RUN python -m pip install --upgrade pip && python -m pip install --no-cache-dir -r requirements.txt

# Expose port 8080
EXPOSE 8080

# Run app.py when the container launches
CMD ["python", "app.py"]