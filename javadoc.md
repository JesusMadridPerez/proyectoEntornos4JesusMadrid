## Generación de código para java con javadoc

### Índice

1. [¿Qué es javadoc?](#1-qué-es-javadoc)
2. [¿Que se debe incluir en la documentación de una clase?](#2-que-se-debe-incluir-en-la-documentación-de-una-clase)
3. [¿Cómo hacer un comentario javadoc?](#3-cómo-hacer-un-comentario-javadoc)
4. [¿De que está compuesto un comentario javadoc?](#4-de-que-está-compuesto-un-comentario-javadoc)
5. [Etiquetas javadoc](#5-etiquetas-javadoc)
6. [Otras etiquetas](#6-otras-etiquetas)

### 1. ¿Qué es javadoc?

Javadoc es una utilidad incluida en el JDK de java para la generación de documentación de APIs en formato HTML.
Javadoc es el estándar para documentar clases en java y la gran mayoría de sus IDEs lo incluyen

### 2. ¿Que se debe incluir en la documentación de una clase?

- Nombre de la clase, descripción general, número de versión, nombre de autores.
- Documentar cada constructor o método incluyendo su nombre, descripción, tipo de return, nombre y tipo de
los parámetros (si los tiene), descripción del valor que devuelve

### 3. ¿Cómo hacer un comentario javadoc?

Los comentarios javadoc se hacen de la siguiente forma

```java
/**
* Esto es un comentario javadoc
*/

```

### 4. ¿De que está compuesto un comentario javadoc?

Un comentario javadoc está formado por una descripción del método o clase y debajo una serie de etiquetas 
sobre su funcionamiento

### 5. Etiquetas javadoc

- etiquetas para documentar clases

	- `@author` para documentar el autor o autores de una clase
	- `@version` para documentar la versión actual de la clase
	- `@since` para documentar en qué versión se introdujo la clase
Ejemplo:	
```java
/**
 *Esta clase define cómo debe comportarse un vehiculo acuatico hereda de la clase abstracta Vehículo
 *y implementa las interfaces AMotor y AVela 
 * 
 * @author Jesus Madrid Perez
 * @version 1.0
 * @since 1.0
 */
```

- etiquetas para constructores y métodos

	- `@param` para documentar los parámetros de un método o constructor
	- `@return` para documentar qué es lo que devuelve el método
	- `@exception` ó `@throws` para indicar que el método produce una excepción 
Ejemplo:
```java
 /**
     * Sobreescritura del método acelerar de la clase abstracta Vehiculos. Comprueba que la velocidad
     * actual más la velocidad que se quiere sumar no sea superior a la velocidad máxima y acelera la velocidad
     * @param sumarVelocidad Velocidad que se quiere añadir
     * @return velocidad actual despues de la aceleracion
     */
   @Override
    protected int acelerar(int sumarVelocidad) {
	// ...
```

### 6. Otras etiquetas

- `@deprecated` se usa para indicar que una clase no debe de usarse
- `@see package.class#member texto` se usa para crear un enlace a una parte de la documentación por ejemplo para ir la documentación de
la clase String seria `@see String`
- `@see referencia` añade una descripción
- `@see <a href="URL#value">label</a>` añade un enlace
- `@sereal` se usa para declarar variables serializables
- `@serealField` se usa para documentar un componente ObjectStreamField
- `@serealData` se usa para describir métodos con un writeObject



[Volver a README](README.md)
