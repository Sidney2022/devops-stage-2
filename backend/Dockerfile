# Use the official Python image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Install poetry
RUN pip install poetry

# Copy poetry files
COPY backend/pyproject.toml backend/poetry.lock* ./

# Install dependencies
RUN poetry install --no-dev

# Copy the rest of the application
COPY backend .

# Command to run the application
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]

