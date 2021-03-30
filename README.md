# dob (Docker Odoo Bootstrap)

YAML based Odoo deployment tool using Docker. Docker sets up the environment
Odoo will be built into, installs Debian, NPM, and Python packages. The further
tooling is done by the `dob.py` script. See the usage. For a documentation of
the main YAML structure see the [Further configuration](docs/configuration.md).

## Usage

Use `-f docker-compose.yaml -f mailhog.yaml` after `docker-compose` if a
mailsink is needed.

```
# To be able to use the git keys of the current user
$ ./setup.sh
# Build, initialization and start up
$ docker-compose build
$ docker-compose run --rm odoo odoo init
$ docker-compose run --rm odoo odoo update
$ docker-compose up
```

## Configuration

Minimal `.env` configuration file is generated by `setup.sh`. For production
it's recommended to set the value of `DB_VERSION` to a recent/supported one of
postgresql. Best is to use major versions with `-alpine` suffix.
[Further configuration](docs/configuration.md).

## Available commands

See [Commands](docs/command.md).

## Environment variables of `.env`

See [Docker Environment](docs/environment.md).

## Credits

This project is inspired by the following projects:

- [Tecnativa doodba](https://github.com/Tecnativa/doodba)
- [camptocamp Odoo Docker](https://github.com/camptocamp/docker-odoo-project)
