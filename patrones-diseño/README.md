# Patrones de diseño

Los patrones de diseño son estructuras normalizadas (generalmente de POO) creadas con el fin de facilitar y estandarizar determinadas operaciones que son comunes al diseño de software en general (creación de objetos, patrones de comportamiento, patrones de desacople de sistemas...).

## Patrones creacionales

Los patrones creacionales se encargan de abstraer cómo crear una instancia de una clase.

<details>

<summary>Abstract Factory (GO4)</summary>

### Introducción

Provee de una interfaz para crear objetos relacionados o dependientes entre sí, sin especificar sus clases concretas.

### Diagrama

```mermaid
classDiagram
    direction RL
    class AbstractFactory {
        <<interface>>
        +createObject1()
        +createObject2()
    }

    class AbstractFactoryImpl1 {
        +createObject1()
        +createObject2()
    }

    class AbstractFactoryImpl2 {
        +createObject1()
        +createObject2()
    }

    class ItemA {
        <<interface>>
    }

    class ItemAImpl1
    class ItemAImpl2

    class ItemB {
        <<interface>>
    }

    class ItemBImpl1
    class ItemBImpl2


    AbstractFactory <|.. AbstractFactoryImpl1
    AbstractFactory <|.. AbstractFactoryImpl2

    ItemA <|.. ItemAImpl1
    ItemA <|.. ItemAImpl2

    ItemB <|.. ItemBImpl1
    ItemB <|.. ItemBImpl2

    AbstractFactoryImpl1 ..> ItemAImpl1 : creates
    AbstractFactoryImpl1 ..> ItemBImpl1 : creates

    AbstractFactoryImpl2 ..> ItemAImpl2 : creates
    AbstractFactoryImpl2 ..> ItemBImpl2 : creates
```

</details>
