FROM jupyter/minimal-notebook:76402a27fd13

USER root

RUN apt update && apt install -y --no-install-recommends \
  bwa \
  htop \
  samtools \
  && rm -rf /var/lib/apt/lists/*

USER ${NB_USER}

RUN conda install -c conda-forge -c bioconda \
  bash_kernel \
  fastp \
  && conda clean --all -f -y

COPY --chown=${NB_USER}:${NB_GID} unix-pipes/ .
