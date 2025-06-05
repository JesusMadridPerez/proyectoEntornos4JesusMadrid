## Optimización del código
En este apartado veremos distintos tipos de optimización del codigo

### Índice

1. [Hediondez del codigo](#1-hediondez-del-codigo)
2. [Analisis del codigo](#2-analisis-del-codigo)
3. [Refactorización del código](#3-refactorización-del-código)

### 1. Hediondez del codigo
La hediondez del codigo o *code smell* en ingles, se refiere a sintomas del código fuente que no implican que no funcione 
correctamente el programa pero si hacen que funcione mas lento
Algunos ejemplos de esto son:

- **Código duplicado:** código que tiene una copia identica o casi identica en otro lado
~~~java
public class Calculadora {
    public int sumar(int a, int b) {
        return a + b;
    }

    public int sumarTresNumeros(int a, int b, int c) {
        return a + b + c;
    }
}

~~~
en este ejemplo el método sumarTresNumeros es redundante ya que para sumar tres numeros podrias simplemente llamar
al primer metodo dos veces para sumar 3 numeros
- **Clase grande:** clase que ha crecido mas de la cuenta y seria conveniente dividirla en varias
- **Envidia de caracteristicas:** una clase que usa excesivamente métodos de otra clase

### 2. Analisis del codigo

Existen dos tipos de analisis:

- **Analisis dinamico:** se analiza el código en ejecución para identificar problemas de rendimiento, memoria o algun
comportamiento inesperado. Un ejemplo de esto son los unit test de java que vimos en el tema anterior
~~~java
import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

public class CalculadoraTest {
    @Test
    public void testSumar() {
        Calculadora calc = new Calculadora();
        int resultado = calc.sumar(2, 3);
        assertEquals(5, resultado, "La suma debería ser 5");
    }
}

~~~

en este ejemplo se comprueba que el método sumar de una clase calculadora funcione correctamente, comprobando que la suma sea
correcta
- **Analisis estatico:** se realiza sin ejecutar el código para detectar errores de sintaxis, seguridad o calidad del codigo
se analiza mediante linters o web de inspección continua 

#### Linters
Los linters son herramientas de que buscan errores de sintaxis, estilo y calidad de vida sin nesesidad de ejecutar
el código. Algunos ejemplos son:
		- **C**: lint
		- **java**: sonar
		- **JavaScript**: JSLint , ESLint
Ejemplo linter js
~~~javaScript
const mensaje = "Hola mundo"
console.log(mensaje)
~~~
Antes de ejecutar el código el linter nos dira que debemos de poner ; al final de cada linea ya que es un error de sintaxis 

####  Continuous Inspection o Continuous Analysis

Se refiere a la inspección continua del código durante el desarrollo para detectar errores,vulnerabilidades y mejorar el codigo
Este servicio lo realizan sitios web como:

##### Scrutinizer


![Scrutinizer](Imagenes/scrutinizer.jpg)

- Soporta PHP, Python y Ruby.


##### SonarQube


![SonarQube](Imagenes/sonarqube.png)

- Soporta mas de 20 lenguajes


### 3. Refactorización del código

Es el proceso de reformular el código fuente para hacerlo mas eficiente, legible y mantenible eliminando redundancias

**Algunas tecnicas utilizadas son:**

- Renombrar variables: dar nombres claros para hacer mas legibles las variables
- Pasar código duplicado a funciones: se usa para eliminar redundancia de código
- Eliminación de código inalcanzable: eliminar codigo que nunca se ejecuta
- Eliminación de código redundante: se usa para suprimir lineas innesesarias de código
- Eliminación de código muerto: elimina código que ha dejado de usarse

Ejemplo de refactorización de código en java
Los metodos mostrar mensaje bienvenida y mostrar mensaje despedida son redundantes y se podrian refactorizar
~~~java
public class Mensaje {
    public void mostrarMensajeBienvenida() {
        System.out.println("Bienvenido a la aplicación");
    }

    public void mostrarMensajeDespedida() {
        System.out.println("Gracias por usar la aplicación");
    }
}

~~~
Refactorización del código
Ahora solo hay un metodo mostrar mensaje que muestra el mensaje que le pases con un string por consola
~~~java
public class Mensaje {
    public void mostrarMensaje(String mensaje) {
        System.out.println(mensaje);
    }
}

~~~

