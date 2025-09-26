FROM nvidia/cuda:12.9.1-cudnn-devel-ubuntu24.04

ENV WHL_DIR=/workspace/wheels

COPY ./*.whl ${WHL_DIR}/

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y python3.10-venv && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --no-deps --no-cache-dir --force-reinstall ${WHL_DIR}/torch_memory_saver*.whl
