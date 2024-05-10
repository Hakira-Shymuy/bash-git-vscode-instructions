## En el Ordenador

Decide la ubicación de la carpeta para los proyectos.
Abre la carpeta, o abre la terminal Bash y navega a esa carpeta.

Navega a la ubicación deseada:
```bash
cd destination
```

Crea una carpeta para el proyecto:
```bash
mkdir myproject
```

Navega a la carpeta del proyecto:
```bash
cd myproject
```
Abre VSCode:
```bash
code .
```

Ahora tenemos el proyecto abierto en VSCode.

## En VSCode
Inicia un repositorio git **localmente**:
```bash
git init
```
Ahora hemos iniciado un repositorio git.
La primera rama puede llamarse master, para renombrarla a main podemos hacer:
```bash
git branch -m master main
```

### Creando algunos archivos

Con el comando ```touch``` podemos crear archivos, da un nombre y la extensión, vamos a crear un archivo index.html:
```bash
touch index.html
```
Crea un archivo CSS:
```bash
touch style.css
```

Si necesitamos organizar los archivos podemos crear una carpeta, por ejemplo:
```bash
mkdir css
```
El comando anterior creará una carpeta llamada css, y ahora podemos mover el archivo css dentro de esa carpeta con:
```bash
mv style.css css
```

## Creando una plantilla html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

Una vez que hemos creado lo necesario como la **BASE** para nuestro proyecto, podemos hacer un commit de la base de este proyecto.

## Añadiendo, haciendo commit, creando un repositorio desde la línea de comandos o VSCode
Como ya hicimos ```git init``` al principio, ahora podemos añadir y hacer commit, pero todavía necesitamos crear un repositorio en github.com.

Los pasos
para añadir todo:
```bash
git add .
```
o para añadir solo un archivo específico:
```bash
git add index.html
```
Luego hacemos commit de nuestros cambios:
```bash
git commit -m "La descripción que queramos"
```
Ahora necesitamos crear nuestro repositorio para poder subir nuestros cambios.

**Creando un repositorio desde el ordenador/ vscode**

Necesitamos tener instalado el CLI de Git para poder hacer esto.
Una vez instalado, podemos usar el siguiente comando para crear un repositorio en línea:

```bash
gh repo create name
```
Esta es la primera parte del comando.
Llama a github ```gh``` y repositorio ```repo``` para crear y le damos un nombre a nuestro repositorio ```name```.

También necesitamos decirle a github si queremos que el repositorio sea **PÚBLICO** o **PRIVADO**, así como una descripción para nuestro repositorio.

Podemos hacerlo con banderas en el comando que tenemos arriba:

- ```--public``` establece el repositorio como público.
- ```--private``` establece el repositorio como privado.
- ```--description "texto"``` establece la descripción del repositorio.

El comando **COMPLETO** debería verse así:
```bash
gh repo create myproject --public --description "Mi Repositorio de Proyecto"
```
Ahora podríamos necesitar añadir el origen remoto, esto significa, estamos diciendo a Git en nuestro ordenador, dónde vive el repositorio en github:

```bash
git remote add origin https://github.com/nuestro-usuario/nombre-de-nuestro-repo.git
```

Ahora que hemos iniciado el repositorio, añadido el origen remoto, podemos ahora subir nuestros cambios a nuestro repositorio en línea de github con el comando:
```bash
git push -u origin main
```
- NOTA: ```main``` en nuestro caso es el nombre de la rama a la que estamos subiendo el código.

Las próximas subidas serían un simple:
```bash
git push
```

## Ramas diferentes
Cuando creamos una nueva rama, y hemos terminado con el código, y si necesitamos subir el código a github antes de hacer ```merge```
Necesitamos establecer un nuevo ```Origen```
Así que repetimos los pasos de añadir y hacer commit de nuestros cambios:
```bash


git add .
git commit -m "Nuestro mensaje"
```
y luego establecemos un **Nuevo Origen**:
```bash
git push --set-upstream origin nombre-de-la-rama
```

Después de completar este paso, podemos libremente ```push``` cambios en el futuro sin la necesidad de establecer el upstream, con el comando:
```bash
git push
```