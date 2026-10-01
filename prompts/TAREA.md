# Tarea: Mi prompt avanzado

## Tarea elegida

Diseñar las clases de un sistema de notas para estudiantes en Java.

## Version 1: prompt basico

```text
Diseña las clases de un sistema de notas para estudiantes en Java.
```

### Resultado simulado

La IA propuso algunas clases como `Estudiante`, `Curso` y `Nota`, pero la respuesta fue general y no indicó claramente qué atributos debía tener cada clase ni cómo organizar el sistema.

### Qué faltaba

Faltaba indicar el rol de la IA y un formato específico para organizar mejor la respuesta.

---

## Version 2

### Técnica agregada: Role prompting

```text
Actúa como desarrollador Java que trabaja en un proyecto académico para estudiantes de programación.

Diseña las clases de un sistema de notas para estudiantes en Java.

Indica para cada clase sus atributos y tipos de datos.
```

### Resultado simulado

La IA respondió de forma más enfocada y propuso clases como `Estudiante`, `Curso` y `Nota`, indicando atributos como nombre, código y calificación.

### Qué mejoró

El rol hizo que la respuesta se enfocara en Java y en un proyecto académico. Además, pedir los atributos y tipos de datos hizo que la respuesta fuera más específica.

---

## Version 3: prompt final

### Técnicas agregadas: Descomposición, few-shot y autocrítica

```text
<rol>
Actúa como desarrollador Java encargado de diseñar un sistema académico sencillo para estudiantes.
</rol>

<contexto>
Necesito diseñar las clases de un sistema de notas para estudiantes en Java.
El sistema debe permitir registrar estudiantes, cursos y calificaciones.
</contexto>

<ejemplo>
Clase Estudiante:
- codigo: String
- nombre: String
</ejemplo>

<tarea>
Divide el trabajo en estos pasos:

1. Identifica las clases principales del sistema.
2. Para cada clase indica sus atributos y tipos de datos.
3. Indica brevemente para qué sirve cada clase.
4. Propón las relaciones principales entre las clases.
5. Revisa tu propuesta y señala si falta alguna clase o atributo importante.
</tarea>

<formato>
Responde usando una tabla con las columnas:
Clase | Atributos y tipos | Función | Relación con otras clases

Después de la tabla, agrega una sección llamada "Revisión final" con las mejoras o elementos que hayas agregado.
</formato>
```

### Resultado simulado

La IA propuso las clases `Estudiante`, `Curso` y `Nota`.

| Clase      | Atributos y tipos                                   | Función                  | Relación con otras clases    |
| ---------- | --------------------------------------------------- | ------------------------ | ---------------------------- |
| Estudiante | codigo: String, nombre: String                      | Representa al estudiante | Se relaciona con Nota        |
| Curso      | codigo: String, nombre: String                      | Representa el curso      | Se relaciona con Nota        |
| Nota       | valor: double, estudiante: Estudiante, curso: Curso | Guarda la calificación   | Relaciona Estudiante y Curso |

En la revisión final, la IA comprobó que las clases propuestas permitieran relacionar estudiantes, cursos y notas, y señaló que se podrían agregar métodos posteriormente.

### Qué mejoró

La respuesta final fue más organizada y completa. La descomposición permitió dividir el trabajo en pasos, el ejemplo indicó el nivel de detalle esperado y la revisión final permitió comprobar si faltaban elementos.

---

## Técnicas usadas en el prompt final

| Técnica             | Parte del prompt                                           | Para qué se utilizó                                     |
| ------------------- | ---------------------------------------------------------- | ------------------------------------------------------- |
| Role prompting      | `<rol>`                                                    | Definir un rol específico relacionado con Java.         |
| Few-shot            | `<ejemplo>`                                                | Mostrar a la IA el formato y nivel de detalle esperado. |
| Descomposición      | `<tarea>` con 5 pasos                                      | Dividir el diseño en partes pequeñas y ordenadas.       |
| Autocrítica         | "Revisa tu propuesta..."                                   | Comprobar si faltaban clases o atributos.               |
| Prompt estructurado | `<rol>`, `<contexto>`, `<ejemplo>`, `<tarea>`, `<formato>` | Separar claramente las instrucciones.                   |

## Evaluación del resultado

| Criterio                                        | Cumple (Sí / No) |
| ----------------------------------------------- | ---------------- |
| ¿Tiene un rol específico?                       | Sí               |
| ¿Utiliza al menos tres técnicas?                | Sí               |
| ¿Tiene un formato de respuesta definido?        | Sí               |
| ¿Incluye un ejemplo para orientar la respuesta? | Sí               |
| ¿Divide la tarea en pasos?                      | Sí               |
| ¿Incluye una revisión final?                    | Sí               |

## Por qué elegí estas técnicas

Elegí estas técnicas porque la tarea consiste en diseñar varias clases y puede resultar desordenada si se solicita todo de una sola vez. El role prompting ayuda a enfocar la respuesta en Java, el few-shot muestra el nivel de detalle esperado, la descomposición permite trabajar el diseño por etapas y la autocrítica ayuda a revisar si falta algún elemento. Elegí estas técnicas porque se adaptan directamente a una tarea de diseño de software.
