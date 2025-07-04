# Hitobito Development 👩🏽‍💻

New here? Install our docker development [setup](doc/setup.md)!

> [!IMPORTANT]
> For an easy to use quick start solution you can use [devcontainers and codespaces][devcontainers].

[devcontainers]: doc/Devcontainer.md

## Development

Start developing by editing files locally with your preferred editor in the `app/hitobito/*` folders.
Those directories are mounted inside the containers. So every saved file is instantly available inside the containers.

:bulb: If you don't know where to begin changing something, have a look at our hitobito cheatsheet in [English](./doc/hitobito-cheatsheet-en.pdf) and [German](./doc/hitobito-cheatsheet.pdf).

### Usage

To initialize the `hit` command, run the following in your console:

```bash
bin/dev-env.sh
```

To start the development environment, run:

```bash
# This command might take a very long time on the first run, as the database needs to be seeded…
hit up
```

Access hitobito via http://localhost:3000

Get a list of available commands with:

```bash
hit help
```

### Running tests

#### Open a test shell

When using this for the first time, once daily or after assets changed run the prep command:

```bash
hit test prep
```

Get a shell to run core or wagon specs:

```bash
hit test
```

#### Run desired tests

Either, to run all tests:

```bash
rspec
```

or, to run specific tests:

```bash
rspec spec/models/person_spec.rb
```

### HTTP request debugging with pry

For debugging with pry during a HTTP request, you can attach to the running docker container (detach with Ctrl+c):

```bash
hit rails attach
```

### Access Development Database

```bash
hit db console
```

### Rerunning seeds

Useful when adding new seeds

```bash
hit rails seed
```

### Gemfile.lock

Since the wagon gem is always causing changes in Gemfile.lock we do not want to check in to core repo, changes to this file are ignored. If you updated gems you need to manually copy the Gemfile.lock from `docker/rails/Gemfile.lock` to the core repo.

### Shutdown

🍺 finished work ? execute `hit down` to shut down all running containers
