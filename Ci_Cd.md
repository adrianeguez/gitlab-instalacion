# DevOps

## Instalacion

Para instalar debemos de dirigirnos a la pagina oficial: [AQUI](https://docs.gitlab.com/runner/install/linux-repository.html)

## Registrar un  runner (shared, de grupo o proyecto)

Para registrar un runner necesitamos la `url` de la instancia y el `token`. Despues de tener esto seguir con estos comandos:

```
$ sudo gitlab-runner register

Please enter the gitlab-ci coordinator URL (e.g. https://gitlab.com )
> URL_GITLAB

Please enter the gitlab-ci token for this runner
> TOKEN

Please enter the gitlab-ci description for this runner
> Descripcion

Please enter the gitlab-ci tags for this runner (comma separated):
> etiqueta-1,etiqueta-2

Please enter the executor: ssh, docker+machine, docker-ssh+machine, kubernetes, docker, parallels, virtualbox, docker-ssh, shell:
> docker

Please enter the Docker image (eg. ruby:2.1):
> node:4.2.2

```
