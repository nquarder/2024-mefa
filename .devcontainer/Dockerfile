FROM rocker/rstudio:latest

RUN R -e "install.packages(c('devtools', 'phenocamr', 'jpeg', 'purrr', 'magick', 'lubridate', 'ggplot2', 'pals', 'maps', 'plotly'), repos='http://cran.rstudio.com/')"

RUN R -e "remotes::install_github('PhenoCamNetwork/phenocamapi')"

# Expose the RStudio Server port
EXPOSE 8787

# Set environment variables for RStudio
ENV PASSWORD=password
ENV USER=mefa

# Add a non-root user for RStudio
RUN useradd -m ${USER} && \
    echo "${USER}:${PASSWORD}" | chpasswd && \
    adduser ${USER} sudo

COPY . /home/${USER}
RUN rm -rf .git .devcontainer
