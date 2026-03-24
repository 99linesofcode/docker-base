# docker-base

A collection of services and containers pulled in and shared with my programming language specific environments. It is pulled into those repositories as a git submodule and expanded upon using [Docker Compose Extend](https://docs.docker.com/compose/how-tos/multiple-compose-files/extends/).

## How to use

1. Pull into your docker configuration using `git submodule add https://github.com/99linesofcode/docker-php.git base`;
1. Use the services relevant to your environment through `service.extends`;

Almost all the relevant configuration is done in/from the `docker-compose.yaml` file. Take a look at [docker-php](https://github.com/99linesofcode/docker-php) if you want an example of how to correctly work with this repository.

## Contributing

Please review the [Contribution Guidelines](https://github.com/99linesofcode/.github/blob/main/.github/CONTRIBUTING.md).

## Code of conduct

In order to ensure that the community is welcoming to all, please review and abide by the [Code of Conduct](https://github.com/99linesofcode/.github?tab=coc-ov-file).

## Security vulnerabilities

Please review [the security policy](https://github.com/99linesofcode/.github?tab=security-ov-file) on how to report security vulnerabilities.

## License

This software is open source and licensed under the [MIT license](https://github.com/99linesofcode/docker-base?tab=MIT-1-ov-file).
