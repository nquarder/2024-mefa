FROM rocker/rstudio:latest

RUN sudo apt-get update && sudo apt-get install -y libmagick++-dev

RUN R -e "install.packages(c('devtools', 'languageserver', 'jpeg', 'purrr', 'magick', 'lubridate', 'ggplot2', 'pals', 'maps', 'plotly'))"

RUN R -e "install.packages('phenocamr')"

RUN R -e "remotes::install_github('PhenoCamNetwork/phenocamapi')"

# Expose the RStudio Server port
EXPOSE 8787

# Set environment variables for RStudio
ENV PASSWORD=password
# ENV USER=mefa

# # Add a non-root user for RStudio
# RUN useradd -m ${USER} && \
#     echo "${USER}:${PASSWORD}" | chpasswd && \
#     adduser ${USER} sudo
