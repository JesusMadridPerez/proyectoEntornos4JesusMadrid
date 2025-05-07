## Uso de comandos git.
### En este apartado aprenderemos a usar git

En primer lugar hay que resaltar que para hacer uso de git primero hay que instalarlo, 
si estas usando linux solo tienes que escribir en la consola de comandos
`sudo apt install git`, en windows es recomendable descargarlo en [la pagina oficial de
git](https://git-scm.com/downloads/win)

### Configuracion inicial

Una vez instalado git deberas realizar la configuracion inicial del mismo.
  
```bash
git config --global user.email          "corre@example.com"         
git config --global user.name           "Tu nombre y apellidos"
git config --global core.editor         nano
git config --global init.defaultBranch  main
```

- La primera linea se utiliza para configurar tu correo electronico
- La segunda linea para configurar tu nombre de usuario
- La tercera para definir cual sera el editor de texto por defecto en este caso nano
- Y la ultima se utiliza para definir la rama principal en la que se trabajara,
  en este caso usaremos la rama main como rama principal ya que es la que utiliza github

### Creacion de un proyecto

Ahora que git esta configurado podemos empezar a utilizarlo, para ello lo primero que 
haremos sera crear una carpeta en la que inizializaremos nuestro primer proyecto

```bash
mkdir miPrimerProyecto
cd miPrimerProyecto
```
Para inizializar el proyecto es muy sencillo solo hay que usar el comando `git init` 
que creara una carpeta oculta en nuestro proyecto llamada .git

Una vez inicializado el proyecto lo mas recomendable seria crear un archivo README.md
ya que la mayoria de los repositorios de git tienen uno `nano README.md` en el deberas
escribir informacion sobre de que trata tu repositorio

### Registro de commits

Antes de realizar nuestro primer commit es nesesario resaltar que git se dive a groso 
modo en 3 espacios el primero el directorio de trabajo que es en el que estamos ahora
y donde se realizan cambios, el segundo es el area de preparacion que es donde indica
que archivos deben de guardarse sus cambios en el repositorio y por ultimo el 
repositorio donde se guardan todos los commits y sus cambios.



 
1. añadimos un archivo al area de preparacion
```
git add README.md
``` 
2. Añadimos al repositorio
```bash
git commit -m "Primer commit"
```

![Imagen areas git](Imagenes/git-areas1.png)

### Como ver los cambios realizados

Para ello solo hay que usar uno de estos comandos
~~~bash
git log
git log --oneline
git log --oneline --all

~~~
- El primero se usa para obtener informacion detallada de los commits
- El segundo se usa para obtener informacion en una sola linea 
- El tercero se usa para ver todos los commits de todas las ramas

### Como movernos a un commit anterior

Para ello se usa el comando

~~~bash
git checkout 88d2
~~~

El numero del final corresponde con el hash del commit, en tu caso pon el hash de tu commit


Una vez estas en un commit anterior es importante que no modifiques nada, pero si puedes ver
lo que has realizado anteriormente, si modificas algo en un commit podria surgir un conflicto

### Como etiquetar commits

Las etiquetas pueden ser muy utiles porque gracias a ellas podemos hacer referencia a un commit
 sin nesesidad de llamar al hash de dicho commit
~~~bash
git tag -a nombreEtiqueta -m "mensaje" commitAEtiquetar
~~~

### Como ver los cambios introducidos respecto al commit anterior

~~~bash
git show
~~~

### Como ver las diferencias entre varios commits

~~~bash
git diff v1..v2
~~~

### Como subir todos nuestros commit a GitHub

1. Crear un repositorio vacio, completamente vacio y preferiblemente con el mismo nombre
 	que el repositorio local
2. Deberas elegir como quieres asociar tu repositorio local a GitHub si mediante HTTPS o SSH
 en este caso elegiremos HTTPS

![imagen HTTPS](Imagenes/https.png)

3. Asociar el repositorio local a GitHub
	Para ello usaremos `git remote add origin https://github.com/JesusMadridPerez/proyectoEntornos4JesusMadrid/tree/main`
	cambia la direccion https por la de tu repositorio
4. Comprobar si se ha asociado correctamente
`git remote -v`

![git remote -v](Imagenes/gitremotev.png)

5. Subir todos los commits al repositorio local
`git push -u origin main`
6. Por ultimo deberas de exportar al proyecto remoto las etiquetas
`git push --tags`

### Como deshacer cambios en el repositorio local

Si por error has borrado algo que no tenias que borrar no te preocupes si tienes commits anteriores se puede solucionar
Hay dos posibilidades:
	- Si no has creado otro commit despues del error independientemente de que hayas o no hecho git add 
		Debes usar el comando `git reset --hard` que borrara todo lo que se haya realizado despues
		del ultimo commit
	- Si has hecho un commit despues del error debes de usar el comando `git reset --hard~n` cambiando n por el numero
		de commits hacia atras que quieres regresar




