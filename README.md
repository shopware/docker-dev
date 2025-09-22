# Shopware Docker Dev

**Shopware/docker-dev** is a meta package and [Symfony Flex](https://flex.symfony.com/) recipe that simplifies local Docker-based development for Shopware projects. It provides a standardized setup to get your Shopware environment running quickly and consistently using Docker and Docker Compose.

This setup is ideal for plugin, app, or core development and ensures your development stack matches Shopware’s best practices and current requirements.

## Features

- **Plug-and-play local Docker development** with ready-to-use Dockerfile and Docker Compose setup
- **Reproducible environment**: Consistent local setup aligned with Shopware’s recommendations
- **Seamless integration**: Adds the Docker configuration to your project via Composer and Symfony Flex
- **Easy updates**: Stay up-to-date with Docker setup improvements simply by updating the package

## Quick Start

1. **Create a new folder**:
    ```
    mkdir my-project
    cd my-project
    ```

2. **Create new Shopware project**:
    ```
    docker run --rm -it -v $PWD:/var/www/html ghcr.io/shopware/docker-dev:php8.3-node22-caddy new-shopware-setup

    # or specific version
    docker run --rm -it -v $PWD:/var/www/html ghcr.io/shopware/docker-dev:php8.3-node22-caddy new-shopware-setup 6.6.10.0
    ```

    This will create a new Shopware project and create configuration files for docker compose.

3. **Start the Docker environment**:
    ```
    make up
    ```

4. **Access your Shopware instance**:
    - By default, your app is available at [http://localhost:8000](http://localhost:8000)


## How It Works

- The recipe will add a pre-configured `Dockerfile` tailored for Shopware and compatible with modern PHP environments.
- Typical steps include building your Shopware project with the [shopware-cli](https://github.com/shopware/shopware-cli) image and serving it with a lightweight PHP/Caddy/NGINX container.
- You can adjust environment variables (PHP version, ports, etc.) by editing the generated Dockerfile or Docker Compose overrides as needed.


## Keeping Your Docker Setup Up-To-Date

Instead of copying Dockerfiles manually, keep your Docker environment current by managing it as a Symfony Flex recipe via Composer.

Run the following to update as needed:

```
composer update shopware/docker
```

This will automatically pull in the latest Docker configuration updates from Shopware.


## Documentation and Help

- [Official Shopware Docker Guide](https://developer.shopware.com/docs/guides/installation/setups/docker.html)

## Contributing

Pull requests, issues, and feedback are welcome! Please see [Shopware's contribution guidelines](https://github.com/shopware/platform/blob/trunk/CONTRIBUTING.md) for more information.
