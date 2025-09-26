FROM nvidia/cuda:12.9.1-cudnn-devel-ubuntu24.04

ENV WHL_DIR=/workspace/wheels

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y python3.10-venv && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/flashinfer-ai/flashinfer.git ;\
    cd flashinfer ;\
    git checkout 50319b2e59e94e4e4b6f175e11184a677e0053b2 ;\
    git submodule update --init --recursive ;\
    MAX_JOBS=32 python -m flashinfer.aot 2>&1 | tee ./build_aot.log ;\
    python -m build --wheel --no-isolation --outdir=${WHL_DIR} 2>&1 | tee ./build.log
