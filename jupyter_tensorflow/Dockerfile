# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG BASE_CONTAINER=jupyter/scipy-notebook
FROM $BASE_CONTAINER

ENV TZ Asia/Tokyo

LABEL maintainer="Jupyter Project contact us <qiulongquan19851234@gmail.com>"

USER root

# Install Tensorflow
RUN pip install --quiet --no-cache-dir \
    'tensorflow==2.2.0' && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"

# Expose ports 22: ssh,  jupyter nb: 8080, django: 8000
EXPOSE 22
EXPOSE 80
EXPOSE 8000
EXPOSE 8080

# Changing work directory to workspace
WORKDIR /work
# COPY requirements.txt /work/
# RUN pip install -r requirements.txt

COPY . /work/
# using CMD command to run, page contents will automatic show on the web page

# Commands
# 使用jupyter不能加入下面的命令，否则jupyter不能正常启动
# CMD [ "/bin/bash" ]