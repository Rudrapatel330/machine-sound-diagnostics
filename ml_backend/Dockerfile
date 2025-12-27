
FROM python:3.9

# Install system dependencies for audio (libsndfile is required by librosa)
RUN apt-get update && apt-get install -y \
    libsndfile1 \
    ffmpeg \
    && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /code

# Copy requirements first to cache installation
COPY requirements.txt .

# Install dependencies
# We pin version numbers to ensure compatibility
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir \
    flask \
    tensorflow==2.13.0 \
    numpy<2.0 \
    librosa \
    scikit-learn \
    gunicorn

# Copy all files
COPY . .

# IMPORTANT: Create a non-root user (Hugging Face requirement)
RUN useradd -m -u 1000 user
USER user
ENV HOME=/home/user \
    PATH=/home/user/.local/bin:$PATH

# Expose port (Hugging Face expects 7860)
EXPOSE 7860

# Command to run the application using Gunicorn
CMD ["gunicorn", "-b", "0.0.0.0:7860", "src.server_app:app"]
