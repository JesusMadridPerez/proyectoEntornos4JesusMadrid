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
- **Clase grande:** clase que ha crecido mas de la cuenta y seria conveniente dividirla en varias
- **Envidia de caracteristicas:** una clase que usa excesivamente métodos de otra clase

### 2. Analisis del codigo

Existen dos tipos de analisis:

- **Analisis dinamico:** se analiza el código en ejecución para identificar problemas de rendimiento, memoria o algun
comportamiento inesperado. Un ejemplo de esto son los unit test de java que vimos en el tema anterior

- **Analisis estatico:** se realiza sin ejecutar el código para detectar errores de sintaxis, seguridad o calidad del codigo
se analiza mediante linters o web de inspección continua 

#### Linters
Los linters son herramientas de que buscan errores de sintaxis, estilo y calidad de vida sin nesesidad de ejecutar
el código. Algunos ejemplos son:
		- **C**: lint
		- **java**: sonar
		- **JavaScript**: JSLint , ESLint

####  Continuous Inspection o Continuous Analysis

Se refiere a la inspección continua del código durante el desarrollo para detectar errores,vulnerabilidades y mejorar el codigo
Este servicio lo realizan sitios web como:

##### Scrutinizer

- Soporta PHP, Python y Ruby.
![Scrutinizer](Imagenes/scrutinizer.jpg)

##### SonarQube

- Soporta mas de 20 lenguajes
![SonarQube](Imagenes/sonarqube.png)

### 3. Refactorización del código

Es el proceso de reformular el código fuente para hacerlo mas eficiente, legible y mantenible eliminando redundancias

**Algunas tecnicas utilizadas son:**

- Renombrar variables: dar nombres claros para hacer mas legibles las variables
- Pasar código duplicado a funciones: se usa para eliminar redundancia de código
- Eliminación de código inalcanzable: eliminar codigo que nunca se ejecuta
- Eliminación de código redundante: se usa para suprimir lineas innesesarias de código
- Eliminación de código muerto: elimina código que ha dejado de usarse


