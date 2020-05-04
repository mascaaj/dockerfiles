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

RUN mkdir /home/src

WORKDIR /home/src

RUN git clone https://github.com/mascaaj/covid-analysis.git
RUN git clone https://github.com/nytimes/covid-19-data.git
RUN git clone https://github.com/ishaberry/Covid19Canada.git
RUN git clone https://github.com/imdevskp/covid-19-india-data.git

#RUN cd covid-analysis
#RUN Rscript scripts/main.R

CMD cd covid-analysis \
  && git checkout develop \
  && R -e "source('scripts/main.R')"

#mkdir ~/Documents/mydocker/results
#docker run -v ~/Documents/mydocker/results:/home/src/covid-analysis/results
