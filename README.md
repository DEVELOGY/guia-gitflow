# Flujo de trabajo GitFlow
## ¿Qué es Git?
Git es un sistema de control de versiones más usado por los desarrolladores de software

## ¿Qué es git-flow?
Git Flow es un modelo, una estrategia y también un workflow muy utilizado por los equipos de desarrollo y programación. Este se destaca por ayudar en la organización de la versión de un código

## ¿Por qué usar git-flow en mis proyectos?
* Aumenta la velocidad de entrega de código terminado al equipo de pruebas
* Disminuyen los errores humanos en la mezcla de las ramas.
* Elimina la dependencia de funcionalidades al momento de entregar código para ser puesto en producción

## ¿Cuáles son los primeros pasos?
El proceso de instalación de git-flow es sencillo. algunos paquetes, estan dispoibles en varios sistemas operativos, 
asegurate de tener instalado *git bash*.

[Link de Descarga -> Git Bash](https://git-scm.com/downloads)

Para comprobar que tengas instalado la extención abre una terminal de `git bash` y ejecuta lo siguiente:


```console
git flow
```
Esto desplegará una lista de comandos disponibles para utilizar.

## Como iniciar con Git Flow
Para iniciar a utilizar `git flow` deberás ubicarte en la carpeta raíz de tu proyecto.
utilizaremos como ejemplo el siguiente directorio. `C:/xampp/htdocs/pruebas`

1. Iniciar con la extensión

```bash
git flow init
```
Este comando mostrará las ramas que se crearán para el desarrollo del proyecto

```console
Which branch should be used for bringing forth production releases?
   - master
Branch name for production releases: [master]
Branch name for "next release" development: [develop]

How to name your supporting branch prefixes?
Feature branches? [feature/]
Bugfix branches? [bugfix/]
Release branches? [release/]
Hotfix branches? [hotfix/]
Support branches? [support/]
Version tag prefix? []

```
#### Ramas de función
Todas las funciones nuevas deben residir en su propia rama, que se puede enviar al rapositorio central para copia de seguridad/colaboración.
Pero en lugar de ramificarse de [master], las ramas `feature` utilizan la rama `develop` como rama primaria. Los cambios no deben interactuar nunca directamente con la rama [master]

1. **feature**: Administrar ramas de características (nuevas funcionalidades).
    Ejemplo: Crear una nueva rama de característica llamada "login":

    ```console
        git flow feature start login
    ```

2. **bugfix**: Administrar ramas de correcciones de errores.
    Ejemplo: Crear una nueva rama de corrección de errores para solucionar un bug llamado "bug123":

    ```console
        git flow bugfix start bug012
    ```

3. **release**: Administrar ramas de lanzamiento de versiones.
    Ejemplo: Crear una nueva rama de lanzamiento para preparar la versión 1.2.0:

    ```console
        git flow release start 1.2.0
    ```

4. **hotfix**: Administrar ramas de correcciones rápidas.
    Ejemplo: Crear una nueva rama de corrección rápida para solucionar un bug crítico llamado "hotfix123":
    
    ```console
        git flow hotfix start hotfix-1.2.5
    ```

5. **support**: Administrar ramas de soporte a largo plazo.
    Ejemplo: Crear una nueva rama de soporte para mantener una versión anterior durante un período prolongado:

    ```console
        git flow support start v1.x
    ```

6. **log**: Mostrar el registro que se desvía de la rama base.
    Ejemplo: Mostrar el historial de commits en la rama de características "login":

    ```console
    git flow log feature/login
    ```
---

## Ejemplo de uso Git Flow

### Crear una rama de función

> las ramas feature suelen crearse a partir de la última rama `develop`
> Ubica tu rama actual en develop, si no estas seguro en que rama te encuentras puedes usar `git branch`

1. PASO 1: Crear una Rama de una nueva funcionalidad como "login":

    ```console
        git flow feature start login
    ```

Este código creará una rama como: `feature/login`

---

### Em momento de Codificar 🤓
> Sigue trabajando como normalmente lo harias, aquí es momento de implementar todo tu código

---

### Al finalizar el desarrollo tu código

2. PASO 2: Guardar los Cambios y Publicarlos en el repositorio.
Antes de finalizar la rama de característica, asegúrate de que estás en la rama de característica que deseas finalizar. Puedes verificarlo con el siguiente comando:

    ```console
        git branch
    ```

3. PASO 3. Realizar los Cambios y Commit.
Trabaja en los cambios necesarios para la característica y realiza commits en la rama de característica (feature). Por ejemplo:

    ```console
        git add .

        git commit -m "feat(app):creación de nuevo login"
    ```
> Utiliza la nomenclaruta de nombrar commit's, utiliza nuestra guía
[Nombra tus Commit's de Manera Pro -> Link](https://github.com/DEVELOGY/guia_github#nombrar-commits)

4. Finalizar la Rama de Característica:
Una vez que hayas completado todos los cambios y estás listo para finalizar la rama de característica, utiliza el siguiente comando:

    ```console
    git flow feature finish feature/login
    ```

> Esto fusionará tus cambios en la rama develop, eliminará la rama de característica (feature/login) y te llevará de vuelta a la rama develop.

### Subir cambios al repositorio

5. PASO 5. Subir los Cambios a la Rama develop:
Después de finalizar la rama de característica, asegúrate de subir los cambios a la rama develop en el repositorio remoto:

```console
git push origin develop
```

> para realizar acciones como relase, bugs, etc. los pasos son los mismos como el ejemplo anterior


--- 
## REFERENCIAS 


* [Git Flow](https://www.atlassian.com/es/git/tutorials/comparing-workflows/gitflow-workflow)
* [Aprende Git con Biubucket](https://www.atlassian.com/es/git/tutorials/learn-git-with-bitbucket-cloud)
* [Aprende sobre ramas](https://www.atlassian.com/es/git/tutorials/learn-branching-with-bitbucket-cloud)
* [Tutoriales avanzados de Git](https://www.atlassian.com/es/git/tutorials/advanced-overview)
* [Qué es Git](https://www.atlassian.com/es/git/tutorials/what-is-git)
