# Use the official R image from the Docker Hub
FROM r-base:4.0.5

# Set the working directory inside the container
WORKDIR /app

# Copy the R script and any other necessary files from the docker/r directory into the container
COPY docker/r/ .

# Install any needed R packages
# This example installs the ggplot2 package
RUN R -e "install.packages('ggplot2', repos='http://cran.rstudio.com/')"

# Command to keep the container running
CMD ["tail", "-f", "/dev/null"]
