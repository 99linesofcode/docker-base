# docker-base

The base tier of my Docker environments: a collection of shared services
(meilisearch, mysql, nodejs, phpmyadmin, redis) and the Ubuntu-LTS devcontainer.
A programming-language wrapper (`docker-php`, `docker-ruby`) pulls this
repository in as a submodule named `base` and expands upon it using
[Docker Compose Extend](https://docs.docker.com/compose/how-tos/multiple-compose-files/extends/).

## How to use

This repository is not consumed by a project directly. A language wrapper adds
it as `base`:

1. From a wrapper repository, add the base as a submodule: `git submodule add https://github.com/99linesofcode/docker-base.git base`;
1. Extend the services you need with Compose `extends` (`file: ./base/docker-compose.yaml`).

Almost all the relevant configuration is done in/from the `docker-compose.yaml` file. Take a look at [docker-php](https://github.com/99linesofcode/docker-php) if you want an example of how to correctly work with this repository.

## Contributing

Please review the [Contribution Guidelines](https://github.com/99linesofcode/.github/blob/main/.github/CONTRIBUTING.md).

## Code of conduct

In order to ensure that the community is welcoming to all, please review and abide by the [Code of Conduct](https://github.com/99linesofcode/.github?tab=coc-ov-file).

## Security vulnerabilities

Please review [the security policy](https://github.com/99linesofcode/.github?tab=security-ov-file) on how to report security vulnerabilities.

## License

This software is open source and licensed under the [MIT license](https://github.com/99linesofcode/docker-base?tab=MIT-1-ov-file).
