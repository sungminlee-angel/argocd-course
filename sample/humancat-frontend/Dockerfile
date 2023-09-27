FROM python:3.10-slim

ENV PYTHONUNBUFFERED=1
ENV PORT 80
ENV SRC_DIR /opt/gitops
ENV PKG_TMP_DIR /tmp
COPY pip_requirements.txt ${PKG_TMP_DIR}/

RUN pip install --upgrade pip && \
    pip install -r ${PKG_TMP_DIR}/pip_requirements.txt

RUN mkdir -p ${SRC_DIR}
COPY ./gitops ${SRC_DIR}/
WORKDIR ${SRC_DIR}

EXPOSE ${PORT}

ENTRYPOINT ["python"]
CMD ["manage.py", "runserver", "0.0.0.0:80"]