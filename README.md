# Simple Metrics

Example application to post and visualize metrics.

## Structure

### Docker environment

This repository contains the Docker configuration to run the project.

### Frontend (Expo)

The Application shows the metrics in a Timeline.

The code is in a separated repository: [App](https://github.com/jferrer/simple-metrics-app)

URL: `http://0.0.0.0:7080`

### Backend (Rails API-only)

The API persists the metrics and provides endpoints to create and fetch them.

The code is in a separeted repository: [API](https://github.com/jferrer/simple-metrics-api)

URL: `http://0.0.0.0:7080/api`

## How to run the project

This project builds automatically using Docker and Docker Compose.

Clone repository with submodules:

```
git clone --recursive https://github.com/jferrer/simple-metrics.git
```

Enter the project:

```
cd simple-metrics
```

Run to configure:

```
docker-compose run api bin/setup
docker-compose run app yarn
```

Run to download dependencies, build the images & start Docker environment:

```
docker-compose up -d
```

Run tests for API:

```
docker-compose exec api bin/rails t
```

Stop the Docker environment:

```
docker-compose stop
```

## Pending improvements
- Different `Compose` file for production deployment
- CI for E2E tests
