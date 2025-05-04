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

![Imagen areas git](/proyectoEntornos4JesusMadrid/Imagenes/git-areas1.png)

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




