  Parcial de Programación II

Agustín Hernández
	1) Composición
para caracterizar la composición es que "un objeto solo puede ser parte de una relación de composición". Además de esta característica definitoria de una composición (para tenerexclusivo, ono compartible, partes), una composición también puede vienen con una dependencia de ciclo de vida entre el compuesto y sus componentes. De hecho, hay dos tipos de tales dependencias:
1.	Siempre que un componentesiempre debe estar conectadoa un compuesto, o, en otras palabras, cuando tiene uncompuesto obligatorio, como se expresa por la multiplicidad "exactamente una" en el lado compuesto de la línea de composición, entonces debe reutilizarse (o unirse a) otro compuesto, o destruirse, cuando se destruye su compuesto actual. Esto se ejemplifica por la composición entre Persony Heart, que se muestra en el diagrama a continuación. Un corazón es destruido o trasplantado a otra persona, cuando su dueño ha muerto.
2.	Siempre que un componenteno se puede separarde su compuesto, o, en otras palabras, cuando esinseparable, entonces, y solo entonces, el componente tiene que ser destruido, cuando su compuesto es destruido. 
 
En resumen, las dependencias del ciclo de vida solo se aplican a casos específicos de composición, pero no en general, por lo tanto no son una característica definitoria.
La especificación UML indica: "Una parte puede eliminarse de una instancia compuesta antes de que se elimine la instancia compuesta y, por lo tanto, no se elimine como parte de la instancia compuesta". En el ejemplo de una composición Car-Engine, como se muestra en el siguiente diagrama, es evidente que el motor se puede desmontar del automóvil antes de que se destruya el automóvil, en cuyo caso el motor no se destruye y puede reutilizarse . Esto está implícito encero o unomultiplicidad en el lado compuesto de la línea de composición.
 
Elmultiplicidaddel final de asociación de una composición en el lado compuesto es 1 o 0..1, dependiendo del hecho de si los componentes tienen un compuesto obligatorio (debe estar unido a un compuesto) o no. Si los componentes son inseparables, esto implica que tienen un compuesto obligatorio.
2) Agregación
Una agregación es otra forma especial de asociación con el significado previsto de una relación parte-todo, donde las partes de un todo se pueden compartir con otros conjuntos. Por ejemplo, podemos modelar una agregación entre las clases DegreeProgram y Course, como se muestra en el siguiente diagrama, ya que un curso es parte de un programa de grado y un curso puede ser compartido entre dos o más programas de grado (por ejemplo, un grado de ingeniería podría compartir Un curso de programación en C con un título en informática.
 
Sin embargo, el concepto de agregación con partes compartibles no significa mucho, en realidad, por lo que no tiene ninguna implicación en la implementación y, por lo tanto, muchos desarrolladores prefieren no usar el blanco. mediamante en sus diagramas de clase, pero simplemente modela una asociación simple en su lugar. La especificación UML dice: "La semántica precisa de la agregación compartida varía según el área de aplicación y el modelador".
El multiplicidad del final de la asociación de una agregación en todo el lado puede ser cualquier número (*) porque una parte puede pertenecer, o compartida entre, cualquier número de wholes.
En términos de código, la composición generalmente sugiere que el objeto que contiene es responsable de crear instancias del componente *, y el objeto que contiene tiene las únicas referencias de larga duración. Por lo tanto, si el objeto primario se elimina de la referencia y se recolecta la basura, también lo hará el hijo.
así que este código ...
Class Order
   private Collection<LineItem> items;
   ...
   void addOrderLine(Item sku, int quantity){
         items.add(new LineItem(sku, quantity));
   }
}
sugiere que LineItem es un componente de Order - LineItems no tiene existencia fuera de su orden de contención. Pero los objetos del artículo no se construyen en el pedido, se pasan según sea necesario y continúan existiendo, incluso si la tienda no tiene pedidos. Así que están asociados, en lugar de componentes.
* n.b. el contenedor es responsable de instanciar el componente, pero puede que en realidad no se convierta en nuevo ... () en sí mismo. Esto es Java, ¡por lo general, hay una fábrica o dos por delante!

Polimorfismo 
 En programación orientada a objetos, polimorfismo es la capacidad que tienen los objetos de una clase en ofrecer respuesta distinta e independiente en función de los parámetros (diferentes implementaciones) utilizados durante su invocación. Dicho de otro modo el objeto como entidad puede contener valores de diferentes tipos durante la ejecución del programa.
En JAVA el término polimorfismo también suele definirse como ‘Sobrecarga de parámetros’, que así de pronto no suena tan divertido pero como veremos más adelante induce a cierta confusión. En realidad suele confundirse con el tipo de poliformismo más común, pero no es del todo exacto usar esta denominación.
Ejemplo de Polimorfismo
Un ejemplo clásico de poliformismo es el siguiente. Podemos crear dos clases distintas: Gato y Perro, que heredan de la superclase Animal. La clase Animal tiene el método abstracto makesound() que se implementa de forma distinta en cada una de las subclases (gatos y perros suenan de forma distinta). Entonces, un tercer objeto puede enviar el mensaje de hacer sonido a un grupo de objetos Gato y Perro por medio de una variable de referencia de clase Animal, haciendo así un uso polimórfico de dichos objetos respecto del mensaje mover.
class Animal {
  public void makeSound() {
    System.out.println("Grr...");
  }
}
class Cat extends Animal {
  public void makeSound() {
    System.out.println("Meow");
  }
}
class Dog extends Animal {
  public void makeSound() {
    System.out.println("Woof");
  }
}

Como todos los objetos Gato y Perro son objetos Animales, podemos hacer lo siguiente
public static void main(String[ ] args) {
  Animal a = new Dog();
  Animal b = new Cat();
}

Creamos dos variables de referencia de tipo Animal y las apuntamos a los objetos Gato y Perro. Ahora, podemos llamar a los métodos makeSound().
a.makeSound();
//Outputs "Woof"

b.makeSound();
//Outputs "Meow"


Como decía el polimorfismo, que se refiere a la idea de "tener muchas formas", ocurre cuando hay una jerarquía de clases relacionadas entre sí a través de la herencia y este es un buen ejemplo.
Por lo general diremos que existen 3 tipos de polimorfismo:
•	Sobrecarga: El más conocido y se aplica cuando existen funciones con el mismo nombre en clases que son completamente independientes una de la otra.
•	Paramétrico: Existen funciones con el mismo nombre pero se usan diferentes parámetros (nombre o tipo). Se selecciona el método dependiendo del tipo de datos que se envíe.
•	Inclusión: Es cuando se puede llamar a un método sin tener que conocer su tipo, así no se toma en cuenta los detalles de las clases especializadas, utilizando una interfaz común.
En líneas generales en lo que se refiere a la POO, la idea fundamental es proveer una funcionalidad predeterminada o común en la clase base y de las clases derivadas se espera que provean una funcionalidad más específica.

























