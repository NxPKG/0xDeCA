FROM continuumio/miniconda3:4.9.2

LABEL maintainer="NxPKG (https://github.com/nxpkg)"
LABEL org.label-schema.vendor="nxpkg"
LABEL org.label-schema.url="https://github.com/nxpkg/0xDeCA/tree/main/simulation"
LABEL org.label-schema.vcs-url="https://github.com/nxpkg/0xDeCA/tree/main/simulation"

EXPOSE 5006

ENV LC_ALL C.UTF-8

RUN conda create --quiet --channel conda-forge --name deca-simulation --yes python=3.8 bokeh mkl mkl-service numpy pandas phantomjs scikit-learn scipy tensorflow

RUN conda init bash
RUN echo "conda activate deca-simulation" >> ~/.bashrc

WORKDIR /root/workspace/0xDeCA/simulation
COPY setup.py .

RUN conda run --name deca-simulation pip install -e .[test]

CMD ["bash"]
