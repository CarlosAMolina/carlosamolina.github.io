Nota. Palabras en mayúsculas precedidas por el símbolo $ indica que deben sustituirse por el valor deseado. Ejm: $USER_NAME

**Índice**

- [Configuración inicial](#configuracioninicial)
- [Crear repositorio remoto desde el repositorio local](#remotodesdelocal)
- [Cambiar nombre de un repositorio](#cambiarnombrerepositorio)
- [Staging area](#stagingarea)
- [Volver a un commit anterior](#commitanterior)
- [Continous integration](#continousintegration)
- [SSH](#ssh)
- [Osint](#osint)
  - [Email de quién realizó el commit](#emailcommit)

<a name="configuracioninicial"></a>
# Configuración inicial

```bash
git config --global user.name "$USER_NAME"
git config --global user.email $USER_EMAIL
git config --global http.sslVerify false
```

Nota. Indicar que no se verifique el certificado SSL es un error de seguridad, en lugar de añadirlo a la configuración global, puede indicarse cada vez que se utilice el comando git añadiendo alguna de las siguientes opciones:

```bash
git -c http.sslVerify false
```

```bash
git -c http.sslVerify=False
```

<a name="remotodesdelocal"></a>
# Crear repositorio remoto desde un repositorio local 

https://docs.gitlab.com/ee/gitlab-basics/create-project.html

https://georgik.rocks/common-mistake-when-creating-new-git-repo

https://docs.gitlab.com/ee/api/namespaces.html

Paso 1. Hacer un commit local para crear el branch master. Este aparece en .git/config como [branch "master"].

Paso 2. Hacer push. Ejm:

```bash
git push --set-upstream https://$DOMINIO/$USER/$REPOSITORY_NAME.git master
```

<a name="cambiarnombrerepositorio"></a>
# Cambiar nombre de un repositorio 

## Gitlab

https://docs.gitlab.com/ee/user/project/settings/

Ir a configuración del repositorio: https://domain/user/project/edit

Advanced settings > Rename repository: cambiar project name y path.

<a name="stagingarea"></a>
# Staging area

https://git-scm.com/about/staging-area

Subir archivo(s) a la zona de index (staging area):

```bash
# Un archivo.
git add NOMBRE_ARCHIVO

# Todos los archivos.
git add .
```

Subir de la zona de index al repositorio local.

```bash
git commit -m "$MENSAJE_PARA_EL_COMMIT"
```

<img src="https://git-scm.com/images/about/index1@2x.png" alt="" width="300">

<a name="commitanterior"></a>
# Volver a un commit anterior

https://stackoverflow.com/questions/4114095/how-to-revert-a-git-repository-to-a-previous-commit/4114122

```bash
# Al último commit.
git reset --hard HEAD

# A un commit específico.
git reset --hard $COMMIT_ID
```

<a name="continousintegration"></a>
# Continous integration

Ver runner en una máquina:

```bash
ps -ef | grep runner
```

<a name="ssh"></a>
# SSH

El protocolo SSH nos permite ejecutar los comandos de git en el servidor remoto sin tener que indicar nuestro usuario y contraseña.

Los pasos para realizar la configuración pueden consultarse en los siguientes enlaces:

https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

https://docs.gitlab.com/ee/ssh/

## Consideraciones

Para poder utilizar el protocolo SSH y no introducir nuestras credenciales, el repositorio con el que estemos trabajando debe haberse descargado del siguiente modo:

```bash
git clone git@$SERVIDOR:$USUARO/$REPOSITORIO
# Ejm: git clone git@github.com:psf/requests
```

## Error authentication failed

En caso de tener error de autenticación al utilizar los comandos de git, puede ser debido a tener activado el doble factor de autenticación; en este caso, hay que utilizar como credenciales un token.

Los pasos para tener este token están explicado en el siguiente enlace:

https://mycyberuniverse.com/how-fix-fatal-authentication-failed-for-https-github-com.html

<a name="osint"></a>
# Osint

<a name="emailcommit"></a> 
## Email de quién realizó el commit 

Opción 1.

Añadir '.patch' al final del ID del commit. Ejm:

```bash
https://github.com/$USER/$REPOSITORY_NAME/commit/$COMMIT_ID.patch
```

Opción 2.

Buscar el ID del commit:

```bash
https://api.github.com/repos/$USER/$REPOSITORY_NAME/commits
```

Ver info del commit

```bash
https://api.github.com/repos/$USER/$REPOSITORY_NAME/git/commits/$COMMIT_ID
```

Nota. Es posible configurar que se oculte el mail de quien realizó el commit, pero los commits realizados antes de esta configuración seguirán mostrando el email (https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address).
