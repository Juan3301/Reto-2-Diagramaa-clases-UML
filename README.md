# Reto-2-Diagramaa-clases-UML

Elija un problema de la vida real (sistema de gestión de biblioteca, negocio de compra-venta, automóvil, etc) que se pueda modelar a través de objetos y clases. Plantee las relaciones de clases, composiciones, propiedades y comportamientos del sistema en uno más diagramas tipo UML.

Me basé en un sistema de liga de futbol en general de cualquier pais del mundo, representado en diagrama UML, utilizando Mermaid.

classDiagram

    Persona <|-- Jugador
    Persona <|-- Entrenador
    Persona <|-- Arbitro


    Liga "1" *-- "1..*" Equipo
    Liga "1" *-- "1" Tabla_de_Posiciones
    Tabla_de_Posiciones "1" *-- "1..*" Posicion_en_la_tabla 
    Equipo "1" *-- "1..*" Jugador
    Equipo "1" *-- "1" Entrenador
    Equipo "1" *-- "1" Estadio

    
    Liga "1" --> "0..*" Partido
    Equipo "1" --> "1" Posicion_en_la_tabla
    Partido "1" --> "2" Equipo
    Partido "1" --> "1" Estadio
    Partido "1" --> "4" Arbitro



    class Persona{
        +Nombre: string
        +edad: int
    }

    class Jugador{
        +Numero: int
        +Posicion: int
        +entrenar()
        +jugar()
    }

    class Entrenador{
        +Recorrido: string
        +dirigir()
        +planear()
        +cambiarEstrategia()
    }

    class Liga{
        +Nombre: string
        +Pais: string
        +Temporada: string
        +agregarEquipo()
        +programarPartido()
        +sortearFinales()
    }

    class Equipo{
        +Nombre: string
        +ciudad: string
        +agregarJugador()
        +echarJugador()
        +jugarPartido()
    }

    class Estadio{
        +Nombre: string
        +Capacidad: int
        +Ciudad: string
    }

    class Partido{
        +fecha: int
        +goleslocal: int
        +golesvisitante: int
        +iniciar()
        +finalizar()
    }

class Tabla_de_Posiciones {
        +ordenar()
        +actualizar()
    }

class Posicion_en_la_tabla {
        +Puntos: int
        +Partidos_jugados: int
        +victorias: int
        +empates: int
        +derrotas: int
        +goles_a_favor: int
        +goles_contra: int
        +dif_goles: int
    }

class Arbitro {
    +Rol: string
    +pitar()
    +aplicarReglasFIFA()

    }
