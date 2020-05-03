FROM rocker/r-ver:3.4.0

RUN apt-get update

# Install external dependencies
RUN apt-get update -qq \
  && apt-get install -y --no-install-recommends \
    apt-utils \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    git \
    zlib1g-dev \
    qpdf \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/ \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds

#Install r dependencies
RUN install2.r --error \
  devtools \
  testthat \
  dplyr \
  ggplot2 \
  Hmisc \
  lubridate \
  ggthemes \
  gridExtra

RUN rm -rf /tmp/downloaded_packages/
