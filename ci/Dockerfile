ARG BASEIMG
FROM $BASEIMG as base

ENV SRC_DIR=/workspace/src \
    WHL_DIR=/workspace/src/wheels

COPY ./*.whl ${WHL_DIR}/

RUN find . -name *.whl | xargs -n1 pip3 install --no-deps --no-cache-dir --force-reinstall  --root-user-action=ignore --break-system-packages
