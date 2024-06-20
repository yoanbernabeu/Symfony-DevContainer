# Symfony DevContainer

Effortlessly set up a Symfony development environment using DevContainers.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) or similar container runtime (e.g. Podman, OrbStack)
- [Compose](https://docs.docker.com/compose/install/) or similar container orchestration tool (e.g. Podman Compose)
- [Visual Studio Code](https://code.visualstudio.com/)
- [DevContainers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Usage

1. Copy the `.devcontainer` folder into root of your Symfony project.
2. Open the project in Visual Studio Code.
3. Click on the green icon in the bottom left corner and select `Reopen in Container`.
4. ... Profit!

## Ports forwarding

By default, the containers forward the following ports:

- The `dev` service in the `compose.yml` file forwards the `8000` port from the PHP container to the host machine. You can change the port by modifying the `ports` field in the `dev` service.

- The `mailer` service forwards the `8025` port from the Mailer container to the host machine. You can change the port by modifying the `ports` field in the `mailer` service.

## Features

Symfony DevContainer comes with tree containers:

- PHP 8.3 (from official Docker image php:8.3-cli) with
  - Composer
  - Symfony CLI
  - Some PHP extensions (e.g. xdebug, intl, pdo_pgsql)
- PostgreSQL 16 (from official Docker image postgres:16-alpine)
- Mailer (from axllent/mailpit)

## Customization

You can customize the containers by editing the `.devcontainer/compose.yml` file.

If you need to install additional PHP extensions or specific versions of software :
- Modify the `Dockerfile`, build and push the image to your Docker registry.
- Update the `image` field in the `dev` service in the `compose.yml` file.

## Contributing

This project is not open to contributions at the moment. 

I'ts a personal project for my own use and i don't have the time to maintain it.

**Feel free to fork the project and make your own changes.**

## Author

- **[Yoan Bernabeu](https://github.com/yoanbernabeu)**

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.