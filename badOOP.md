Muchos de los errores comunes que se producen en la programación en Java vienen por un mal uso de la Programación Orientada a Objetos. Entre ellos podemos destacar:

  * Falta total de orientación a objetos y uso de enfoque procedural: posiblemente desencadena en la falta de encapsulación y alto acoplamiento. Pocas clases con métodos muy largos.

  * Mala aplicación del encapsulamiento: una clase debería ser la única responsable del acceso a sus métodos y atributos. Una mala encapsulación puede permitir un mal uso de la clase y producir comportamientos inesperados (importante sobre todo cuando son clases que se exponen al uso por terceras personas):
    1. [Ejemplo de mala encapsulación](badEncapsulation.md)
    1. [Ejemplo de buena encapsulación](goodEncapsulation.md)

  * Excesivo uso de herencia que degenera en un código demasiado complejo y difícil de mantener. La herencia ha de usarse cuándo esté justificada y su uso facilite la reutilización de código.

  * Diseño incorrecto de las clases, ya sea por falta de granularidad (pocas clases con demasiada funcionalidad) o por exceso (muchas clases con funcionalidad muy reducida).

  * Mal uso del polimorfismo: el excesivo uso de **instanceof** puede ser un indicador de un mal diseño de clases o mal uso de la herencia.