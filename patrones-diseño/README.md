# Patrones de diseño

Los patrones de diseño son estructuras normalizadas (generalmente de OOP) creadas con el fin de facilitar y estandarizar determinadas operaciones que son comunes al diseño de software en general (creación de objetos, patrones de comportamiento, patrones de desacople de sistemas...).

||Patrón|
|---|---|
|:green_circle:|Abstract Factory|
|:red_circle:|Adapter|
|:red_circle:|Bridge|
|:red_circle:|Builder|
|:red_circle:|Chain of Responsibility|
|:red_circle:|Command|
|:red_circle:|Composite|
|:red_circle:|Decorator|
|:red_circle:|Facade|
|:red_circle:|Factory Method|
|:red_circle:|Flyweight|
|:red_circle:|Interpreter|
|:red_circle:|Iterator|
|:red_circle:|Mediator|
|:red_circle:|Memento|
|:red_circle:|Observer|
|:red_circle:|Prototype|
|:red_circle:|Proxy|
|:red_circle:|Singleton|
|:red_circle:|State|
|:red_circle:|Strategy|
|:red_circle:|Template Method|
|:red_circle:|Visitor|

## Patrones creacionales

Los patrones creacionales se encargan de abstraer cómo crear una instancia de una clase.

<details>

<summary>Abstract Factory (Go4)</summary>

### Introducción

Provee de una interfaz para crear objetos relacionados o dependientes entre sí, sin especificar sus clases concretas.

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![AbstractFactory](./assets/img/abstract-factory.jpg)
</details>

### Partes

- `Abstract Factory`: interfaz que define las operaciones que generan los objetos (Item).
- `ConcreteFactory[0-9]`[^1]: implementaciones de la factoría. Depende de las implementaciones de los items.
- `Some[A-Z]`[^2]: interfaces de las clases a construir.
- `Some[A-Z][0-1]`: implementaciones de las diferentes interfaces de clases a construir. En algunos contextos, existen familias que implementan `Some[A-Z]` de forma coherente entre sí.
- `APP`: aplicación que utilizará las interfaces, agnóstica de las implementaciones.

### Pros

- Aísla clases concretas: como se crean instancias de las clases que maneja la Abstract Factory es desconocido para el que la esté utilizando.
- Es fácil cambiar entre diferentes "familias" de ítems: cambiar de familias de implementaciones de los mismos items consiste simplemente en cambiar la factoría concreta que se esté utilizando.
- Promueve la consistencia entre ítems: las diferentes familias trabajan juntas con más cohesión, ya que la implementación de una sola familia es manejada por una factoría concreta.

### Contras

- Ampliar nuevos ítems puede ser difícil: para añadir nuevos ítems a una familia, hay que modificar tanto el contrato como las diferentes implementaciones de la factoría.  
Solucionar este problema no es especialmente complicado: si no se puede acceder a la implementación de la factoría, podemos simplemente extenderla y usar dicha extensión como nueva factoría (aunque no es una solución muy elegante).

### Notas

- Es común que una implementación de AbstractFactory sea un Singleton.
- Es común que las diferentes implementaciones de los ítems a su vez implementen un Factory Method u otro patrón de creación.

### Ejemplo

Interfaces de las clases a crear:

```java
public interface SomeA {
    //methods...
}

------------------------------

public interface SomeB {
    //methods...
}
```

Implementaciones *1*

```java
public class SomeA1 implements SomeA {
    //attributes and methods implementation...
}

------------------------------

public class SomeB1 implements SomeB {
    //attributes and methods implementation...
}
```

Implementaciones *2*

```java
public class SomeA2 implements SomeA {
    //attributes and methods implementation...
}

------------------------------

public class SomeB2 implements SomeB {
    //attributes and methods implementation...
}
```

Interfaz de la factoría abstracta

```java
public interface AbstractFactory {
    SomeA createSomeA();
    SomeB createSomeB();
    //...
}
```

Implementaciones de la interfaz para los conjuntos *1* y *2* de clases `Some[A-Z]`

```java
public class ConcreteFactory1 implements AbstractFactory {
    @Override
    public SomeA createSomeA() {
        SomeA1 someA1 = //create some SomeA1 object with any method
        return someA1;
    }

    @Override
    public SomeB createSomeB() {
        SomeB1 someB1 = //create some SomeB1 object with any method
        return someB1;
    }
    //...
}

------------------------------

public class ConcreteFactory2 implements AbstractFactory {
    @Override
    public SomeA createSomeA() {
        SomeA2 someA2 = //create some SomeA2 instance with any method
        return someA2;
    }

    @Override
    public SomeB createSomeB() {
        SomeB2 someB2 = //create some SomeB2 instance with any method
        return someB2;
    }
    //...
}
```

Nuestra APP utiliza la factoría para construir los objetos

```java
public class App {

    private AbstractFactory factory = new ConcreteFactory2();

    void makeSomething() {
        SomeA someA = factory.createSomeA();
        //very interesting code
    }
}
```

</details>

---

<details>

<summary>Builder (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Factory Method (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Prototype (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Singleton (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

## Patrones estructurales


<details>

<summary>Adapter (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Bridge (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Composite (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Decorator (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Facade (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Flyweight (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Proxy (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

## Patrones de comportamiento

<details>

<summary>Chain of Responsibility (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Command (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Interpreter (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Iterator (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Mediator (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Memento (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Observer (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>State (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Strategy (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Template Method (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

<details>

<summary>Visitor (Go4)</summary>

### Introducción

### Diagrama

<details> 

<summary>Ver diagrama</summary>

![patron](link)
</details>

### Partes

- `Parte1`: parte1

### Pros

- Pro

### Contras

- Contra

### Notas

- Una nota

### Ejemplo

</details>

---

[^1]: `[0-9]` es intercambiable por cualquier número, haciendo así referencia a algún objeto|clase|interfaz.
[^2]: `[A-Z]` es intercambiable por cualquier número, haciendo así referencia a algún objeto|clase|interfaz.
