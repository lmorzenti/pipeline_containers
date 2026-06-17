FROM mambaorg/micromamba:latest

USER root
RUN apt-get update && apt-get install -y procps && rm -rf /var/lib/apt/lists/*
USER $MAMBA_USER

RUN micromamba install -y -n base \
    --channel conda-forge \
    --channel bioconda \
    multiqc && \
    micromamba clean --all --yes

ENV PATH="$MAMBA_ROOT_PREFIX/bin:$PATH"