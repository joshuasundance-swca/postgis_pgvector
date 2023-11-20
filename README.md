# postgis_pgvector

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[![Push to Docker Hub](https://github.com/joshuasundance-swca/postgis_pgvector/actions/workflows/docker-hub.yml/badge.svg)](https://github.com/joshuasundance-swca/postgis_pgvector/actions/workflows/docker-hub.yml)
[![postgis_pgvector on Docker Hub](https://img.shields.io/docker/v/joshuasundance/postgis_pgvector?label=postgis_pgvector&logo=docker)](https://hub.docker.com/r/joshuasundance/postgis_pgvector)
[![Docker Image Size (tag)](https://img.shields.io/docker/image-size/joshuasundance/postgis_pgvector/latest)](https://hub.docker.com/r/joshuasundance/postgis_pgvector)

[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
![Known Vulnerabilities](https://snyk.io/test/github/joshuasundance-swca/postgis_pgvector/badge.svg)


🤖 This `README` was written by GPT-4. 🤖

## Introduction
This project focuses on creating a Docker image that combines the functionalities of `PostGIS` and `pgvector`, offering an easy-to-use solution for working with spatial data and vector similarity in PostgreSQL. It is designed to be as simple as integrating any other PostgreSQL Docker image into your workflow.

## Components
- `PostGIS`: An extension to PostgreSQL that allows it to store spatial data and perform spatial operations.
- `pgvector`: An extension for PostgreSQL designed for efficient similarity search in high dimensional vector spaces.


### Dockerfile
The `Dockerfile` starts with the `postgis/postgis:13-3.4` image and installs essential packages including build tools, PostgreSQL server development tools, and `git`. It then clones and installs pgvector. The Dockerfile is optimized to reduce the layer size by cleaning up after installations.

### docker-compose.yml
`docker-compose.yml` sets up two services:

- `postgis_pgvector`: Builds the Docker image from the provided Dockerfile and sets up a volume for data persistence. It also configures the environment for PostgreSQL.
- `pgadmin`: Uses the `dpage/pgadmin4:7.8` image for database management through a web interface. It also sets up a volume for pgAdmin data.

## Usage
- **Build and Run**: Use `docker compose up` to build the image and run the containers.
- **Accessing pgAdmin**: Navigate to http://localhost:80 in your web browser. Default credentials are set in the `docker-compose.yml` file but can be overridden with environment variables.
- **Connecting to the Database**: Connect to your PostGIS-pgvector database using standard PostgreSQL connection methods. Default database details are provided in the `docker-compose.yml`.

## Customization
- **Environment Variables**: Set `POSTGRES_PASSWORD`, `POSTGRES_DB`, `PGADMIN_DEFAULT_EMAIL`, and `PGADMIN_DEFAULT_PASSWORD` in your environment or directly in the `docker-compose.yml`.
- **Ports and Volumes**: Modify ports and volume bindings in `docker-compose.yml` as per your requirements.

## Notes
- Ensure Docker and Docker Compose are installed on your system.
- The image can be customized further by modifying the Dockerfile and `docker-compose.yml` as needed.
- This image is currently intended for development and testing purposes.
- For production use, consider securing your database and pgAdmin with stronger passwords and appropriate network settings.

## Contributing
Your contributions are welcome! To contribute, please follow the standard fork and pull request workflow.

## License
This project is licensed under the MIT License.
