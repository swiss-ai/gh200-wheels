FROM nvcr.io/nvidia/pytorch:25.06-py3

ENV SRC_DIR=/workspace/src \
    WHL_DIR=/workspace/src/wheels

COPY ./*.whl ${WHL_DIR}/

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y python3.10-venv && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --no-deps --no-cache-dir --force-reinstall ${WHL_DIR}/torch_memory_saver*.whl
