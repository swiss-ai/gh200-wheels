FROM nvcr.io/nvidia/pytorch:24.01-py3

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y python3.10-venv && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*