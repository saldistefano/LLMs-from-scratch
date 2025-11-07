# Install PyTorch
FROM  --platform=arm64 pytorch/pytorch:latest

# Install Ubuntu packages
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y rsync git curl ca-certificates && \
    rm -rf /var/lib/apt/lists/*

# Install uv
ADD https://astral.sh/uv/install.sh /uv-installer.sh
RUN sh /uv-installer.sh && rm /uv-installer.sh
ENV PATH="/root/.local/bin/:$PATH"

# Install Python packages
COPY requirements.txt requirements.txt
RUN uv pip install --system --no-cache -r requirements.txt
