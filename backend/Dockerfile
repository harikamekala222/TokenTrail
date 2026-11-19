
FROM python:3.12-slim

WORKDIR /app/backend

# Install uv package manager
RUN pip install --no-cache-dir uv

# Copy backend including the local SDK workspace
COPY backend/ ./

# Install application dependencies
RUN uv sync --frozen --no-dev

# Backend port
EXPOSE 8000

# Start FastAPI
CMD ["uv", "run", "--no-sync", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
