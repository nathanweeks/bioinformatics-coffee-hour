FROM jupyter/minimal-notebook:76402a27fd13

RUN conda install -c conda-forge -c bioconda \
  bash_kernel \
  bwa \
  fastp \
  samtools \
  && conda clean --all -f -y

COPY --chown=${NB_USER}:${NB_GID} unix-pipes/ .

RUN rm -rf binder
