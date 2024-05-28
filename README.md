# Multi-Container Docker Environment for Python and R

This project sets up a multi-container Docker environment to run Python and R applications. Each service is defined in its own Dockerfile, and Docker Compose is used to manage the containers.

## Directory Structure

The project directory should be structured as follows:

project-root/
├── docker-compose.yml
├── docker/
│ ├── python/
│ │ ├── Dockerfile
│ │ ├── requirements.txt
│ │ └── your_script.py
│ ├── r/
│ ├── Dockerfile
│ └── your_script.R


- `docker-compose.yml`: Docker Compose configuration file.
- `docker/python/`: Directory for the Python Dockerfile and related files.
- `docker/r/`: Directory for the R Dockerfile and related files.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine.
- [Docker Compose](https://docs.docker.com/compose/install/) installed on your machine.

## Usage

### Building and Running the Containers

1. **Navigate to the project root directory**:

    ```sh
    cd /path/to/project-root
    ```

2. **Build and start the containers**:

    ```sh
    docker-compose up --build
    ```

    This command will build the Docker images and start the containers for both the Python and R applications. The containers will remain running indefinitely.

### Running Your Scripts

Once the containers are running, you can execute your scripts inside the containers using the `docker exec` command.

1. **Run the Python script**:

    ```sh
    docker exec -it python-app-container python /app/your_script.py
    ```

2. **Run the R script**:

    ```sh
    docker exec -it r-app-container Rscript /app/your_script.R
    ```

### Stopping the Containers

To stop the running containers, use the following command:

```sh
docker-compose down

This command will stop and remove the containers, but the images will remain cached.

Customizing the Environment

Python Requirements: Add any Python dependencies to docker/python/requirements.txt.
R Packages: Modify the RUN R -e "install.packages(...)" line in docker/r/Dockerfile to include additional R packages.
Troubleshooting
Ensure Docker and Docker Compose are installed and running properly on your system.
Verify that the directory structure matches the expected layout.
License
This project is licensed under the MIT License.


This `README.md` provides a clear and concise guide on how to set up, run, and manage your Dockerized Python and R environments using Docker Compose. Adjust the paths and script names as needed for your specific project setup.
