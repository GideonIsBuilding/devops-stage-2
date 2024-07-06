# Use the official Python image from the Docker Hub
FROM python:3.9

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container
COPY pyproject.toml poetry.lock ./

# Install poetry
RUN pip install poetry

# Install dependencies
RUN poetry install

# Copy the rest of the application code into the container
COPY . .

# Make sure the prestart script is executable
RUN chmod +x /app/prestart.sh

# Expose port 8000 to the outside world
EXPOSE 8000

# Run the prestart script and then start the FastAPI application
CMD ["./prestart.sh", "&&", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
