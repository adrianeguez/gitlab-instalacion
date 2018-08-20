# Gitlab

## Instalacion de Gitlab 

Para instalar gitlab se debe de seguir el siguiente tutorial: [AQUI](https://linuxconfig.org/how-to-install-gitlab-on-ubuntu-18-04-bionic-beaver)

## Instalacion de Gitlab con Docker

Para instalar gitlab se debe de seguir el siguiente tutorial: [AQUI](https://docs.gitlab.com/omnibus/docker)




# Comandos

## Rails console

Para iniciar una consola de rails con gitlab usamos:

```
$ sudo gitlab-rails console
```

## Correo

Para configurar el correo debemos de abrir el archivo `/etc/gitlab/gitlab.rb` y luego de editarlo correr el comando:

```
$ gitlab-ctl reconfigure
```

### Configuracion mailgun

La configuracion para mailgun es la siguiente:

 ```ruby
 
gitlab_rails['gitlab_email_from'] = 'gitlab@example.com'
gitlab_rails['gitlab_email_reply_to'] = 'noreply@example.com'

gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.mailgun.org"
gitlab_rails['smtp_port'] = 587
gitlab_rails['smtp_authentication'] = "plain"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['smtp_user_name'] = "postmaster@sandboxb94bb6a00890468980cbb5fb4ee60dc2.mailgun.org"
gitlab_rails['smtp_password'] = "8b6ffrmle180"
gitlab_rails['smtp_domain'] = "sandboxb94bb6a00890468980cbb5fb4ee60dc2.mailgun.org"
 
 ```
Finalmente para probarlo podemos mandar un correo con la `Consola de Rails de Gitlab`:

```
$ irb(main):003:0> Notify.test_email('destination_email@address.com', 'Message Subject', 'Message Body').deliver_now
```

## Instalacion con docker

```
$ sudo docker run --detach --hostname gitlab.example.com --publish 8085:443 --publish 8086:80 --publish 8087:22 --name gitlab --restart always --volume /Users/adrianeguez/Documents/GitlabDocker/Configuration:/etc/gitlab --volume /Users/adrianeguez/Documents/GitlabDocker/Logs:/var/log/gitlab --volume /Users/adrianeguez/Documents/GitlabDocker/Data:/var/opt/gitlab gitlab/gitlab-ce:latest
```

```
$ sudo docker run --detach --hostname gitlab.example.com --publish 8095:443 --publish 8096:80 --publish 8097:22 --name gitlabee --restart always --volume /Users/adrianeguez/Documents/GitlabDockerEE/Configuration:/etc/gitlab --volume /Users/adrianeguez/Documents/GitlabDockerEE/Logs:/var/log/gitlab --volume /Users/adrianeguez/Documents/GitlabDockerEE/Data:/var/opt/gitlab gitlab/gitlab-ee:latest
```


