FROM rocker/binder:4.0.0

ARG NB_USER
ARG NB_UID

USER root

# install dependencies
RUN install2.r statmod \
  && Rscript -e 'BiocManager::install("edgeR", update=FALSE)' \
  && rm -rf /tmp/downloaded_files

# copy files
COPY ./differential-expression-analysis/data ${HOME}/data/
COPY ./enrichment-analysis/data ${HOME}/data/
COPY ./enrichment-analysis/index.Rmd ${HOME}/data/

RUN chown -R ${NB_USER} ${HOME}

USER ${NB_USER}
