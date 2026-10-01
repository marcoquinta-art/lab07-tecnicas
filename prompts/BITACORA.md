# Bitácora de técnicas avanzadas de prompting

## Ejercicio 2: Zero-shot, one-shot y few-shot

**Prompt Zero-shot:**

Clasifica estos comentarios de clientes:

1. Me encanto, llego rapido
2. No lo recomiendo
3. Es aceptable por el precio
4. Pesima atencion, no vuelvo
5. Excelente calidad, lo volveria a comprar

Respuesta:
Comentario Clasificación

1. Me encantó, llegó rápido 🟢 Positivo
2. No lo recomiendo 🔴 Negativo
3. Es aceptable por el precio 🟡 Neutral
4. Pésima atención, no vuelvo 🔴 Negativo
5. Excelente calidad, lo volvería a comprar 🟢 Positivo

**Prompt one-shot:**

Clasifica cada comentario como Positivo, Negativo o Neutral.

Ejemplo: "Me gusto mucho" -> Positivo

Comentarios:

1. Me encanto, llego rapido
2. No lo recomiendo
3. Es aceptable por el precio
4. Pesima atencion, no vuelvo
5. Excelente calidad, lo volveria a comprar

Respuesta:

1. Positivo
2. Negativo
3. Neutral
4. Negativo
5. Positivo

**Prompt few-shot:**

Clasifica cada comentario. Responde solo con el formato de los ejemplos. "Me gusto mucho" -> Positivo
"Que decepcion" -> Negativo
"Esta bien, nada especial" -> Neutral

"Me encanto, llego rapido" -> "No lo recomiendo" ->
"Es aceptable por el precio" -> "Pesima atencion, no vuelvo" ->
"Excelente calidad, lo volveria a comprar" ->

Respuesta:

1. "Me encanto, llego rapido" → **Positivo**
2. "No lo recomiendo" → **Negativo**
3. "Es aceptable por el precio" → **Neutral**
4. "Pesima atencion, no vuelvo" → **Negativo**
5. "Excelente calidad, lo volveria a comprar" → **Positivo**

Cuadro:

| Tipo      | Aciertos (de 5) | Formato de la respuesta   | Todas con el mismo formato (Sí/No) |
| --------- | --------------: | ------------------------- | ---------------------------------- |
| Zero-shot |               5 | Libre / con explicaciones | No                                 |
| One-shot  |               5 | Comentario → etiqueta     | Sí                                 |
| Few-shot  |               5 | Texto → etiqueta          | Sí                                 |

## Ejercicio 3: Chain of Thought

Respuesta Directa:

318.60

Respuesta Paso aPaso:

1. Precio original por unidad: **S/ 120**
2. Descuento del 25 %:
   - 120 × 0.25 = **S/ 30**
   - Precio con descuento: 120 − 30 = **S/ 90**
3. IGV del 18 % sobre S/ 90:
   - 90 × 0.18 = **S/ 16.20**
   - Precio final por unidad: 90 + 16.20 = **S/ 106.20**
4. Por 3 unidades:
   - 106.20 × 3 = **S/ 318.60**
5. Comprobación:
   - 120 × 3 = S/ 360
   - Descuento total: 360 × 25 % = S/ 90
   - Base con descuento: 360 − 90 = S/ 270
   - IGV: 270 × 18 % = S/ 48.60
   - Total: 270 + 48.60 = **S/ 318.60**

**Respuesta final: S/ 318.60**

| Pedido      | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
| ----------- | ------------------ | ------------------------- | ---------------- |
| Directo     | 318.60             | No                        | Sí               |
| Paso a paso | 318.60             | Sí                        | Sí               |

## Ejercicio 4: Role prompting

**Prompt Sin rol:**

Una variable en programación es un espacio donde guardamos un dato para poder usarlo o modificarlo después.

Por ejemplo, en Python:

edad = 20
nombre = "Ana"

Aquí:

edad es una variable que contiene el número 20.

nombre es una variable que contiene el texto "Ana".

Se llaman variables porque su valor puede cambiar:

edad = 20
edad = 21

Ahora edad vale 21.

💡 Puedes imaginar una variable como una caja con una etiqueta: la etiqueta es el nombre de la variable (edad) y lo que hay dentro es su valor (21).

**Prompt Rol docente:**

Una variable en programación es como una caja con un nombre donde podemos guardar un dato para utilizarlo más adelante.

Imagina que tenemos una caja llamada edad y dentro guardamos el número 18:

edad = 18

Aquí ocurren dos cosas:

edad → es el nombre de la variable.

18 → es el valor que estamos guardando.

Lo interesante es que el contenido de una variable puede cambiar. Por ejemplo:

edad = 18
edad = 19

Primero edad contiene 18, pero después pasa a contener 19.

Las variables pueden guardar diferentes tipos de información:

nombre = "Ana"
edad = 18
altura = 1.65
es_estudiante = True

En este ejemplo, nombre guarda texto, edad un número entero, altura un número decimal y es_estudiante un valor de verdadero/falso.

¿Para qué sirven?
Nos permiten recordar información y trabajar con ella. Por ejemplo:

precio = 10
cantidad = 3

total = precio \* cantidad

print(total)

El programa utiliza los valores guardados en precio y cantidad para calcular el resultado:

10 × 3 = 30

Por tanto, una buena definición para recordar es:

Una variable es un nombre que utilizamos para guardar un dato que nuestro programa puede consultar o modificar.

💡 Analogía: piensa en las variables como cajas etiquetadas. La etiqueta te permite encontrar la caja (edad) y dentro de ella está el dato (18).

**Prompt Rol senior:**

Una variable en programación es como una cajita con un nombre donde podemos guardar información.

Por ejemplo, imagina que estás haciendo un programa para una tienda. Necesitas guardar el nombre de un cliente:

nombre = "Carlos"

Aquí:

nombre → es el nombre de la variable.

"Carlos" → es el valor que guardamos.

= → significa que estamos asignando ese valor a la variable.

Después podemos utilizar esa información:

print(nombre)

El programa mostraría:

Carlos

🔄 Una variable puede cambiar
Se llama variable porque su valor puede cambiar durante la ejecución del programa.

edad = 18
edad = 19

Primero edad contiene 18, pero después contiene 19.

Es parecido a una caja etiquetada "edad":

📦 edad → 18

Luego cambiamos lo que hay dentro:

📦 edad → 19

📦 ¿Qué podemos guardar en una variable?
Prácticamente cualquier tipo de información. Por ejemplo:

nombre = "Ana" # Texto
edad = 20 # Número entero
precio = 15.50 # Número decimal
es_estudiante = True # Verdadero o falso

Una forma sencilla de recordarlo es:

Una variable es un nombre que usamos para guardar y posteriormente utilizar un dato en nuestro programa.

Por ejemplo, en un programa de notas:

nombre = "Luis"
nota = 17

print(nombre)
print(nota)

El programa recuerda que nombre vale "Luis" y que nota vale 17, y podemos utilizar esos valores cuando los necesitemos.

| Version        | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo            | A quien le sirve mas              |
| -------------- | ------------------------------ | -------------------------------- | --------------------------------- |
| A. Sin rol     | Sencillo                       | Pocos o ningún ejemplo           | Público general                   |
| B. Rol docente | Sencillo                       | Sí, usa ejemplos y comparaciones | Personas que nunca han programado |
| C. Rol senior  | Técnico                        | Sí, puede incluir código Java    | Programadores con experiencia     |

## Ejercicio 5: Descomposición (dividir la tarea)

PASO 2:

Claro. Para una primera versión sencilla en Java, puedes organizar el sistema con estas clases principales:

1. Producto
   Representa cada artículo de la tienda.

Atributo Tipo
codigo String
nombre String
categoria String
precio double
stock int
stockMinimo int

2. Inventario
   Se encarga de administrar los productos y controlar las existencias.

Atributo Tipo
productos List<Producto>

Responsabilidades: agregar, modificar, eliminar, buscar productos y actualizar el stock.

3. Movimiento
   Representa una entrada o salida de productos.

Atributo Tipo
id int
producto Producto
tipo TipoMovimiento
cantidad int
fecha LocalDateTime

4. TipoMovimiento
   Un enum para distinguir las operaciones de inventario.

public enum TipoMovimiento {
ENTRADA,
SALIDA
}

5. AlertaStock
   Representa una alerta cuando un producto alcanza o baja de su stock mínimo.

Atributo Tipo
producto Producto
mensaje String
fecha LocalDateTime
activa boolean

6. Reporte
   Se encarga de generar información resumida del inventario.

Atributo Tipo
inventario Inventario

Métodos posibles: generarReporteInventario(), generarReporteMovimientos() y generarReporteBajoStock().

7. SistemaInventario
   Puede funcionar como clase principal o como coordinadora del sistema.

Atributo Tipo
inventario Inventario
movimientos List<Movimiento>
alertas List<AlertaStock>
reporte Reporte

Nota de diseño: para un sistema real, convendría usar BigDecimal en lugar de double para los precios, para evitar problemas de precisión con valores monetarios.

PASO 3:

Aquí tienes una implementación sencilla de la clase Producto con sus atributos, constructor y métodos get y set:
public class Producto {

    private String codigo;
    private String nombre;
    private String categoria;
    private double precio;
    private int stock;
    private int stockMinimo;

    // Constructor
    public Producto(String codigo, String nombre, String categoria,
                    double precio, int stock, int stockMinimo) {
        this.codigo = codigo;
        this.nombre = nombre;
        this.categoria = categoria;
        this.precio = precio;
        this.stock = stock;
        this.stockMinimo = stockMinimo;
    }

    // Getters y Setters

    public String getCodigo() {
        return codigo;
    }

    public void setCodigo(String codigo) {
        this.codigo = codigo;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public String getCategoria() {
        return categoria;
    }

    public void setCategoria(String categoria) {
        this.categoria = categoria;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }

    public int getStock() {
        return stock;
    }

    public void setStock(int stock) {
        this.stock = stock;
    }

    public int getStockMinimo() {
        return stockMinimo;
    }

    public void setStockMinimo(int stockMinimo) {
        this.stockMinimo = stockMinimo;
    }

}

| Paso                | ¿Qué entregó la IA?                                                                                     |
| ------------------- | ------------------------------------------------------------------------------------------------------- |
| 1. Requisitos       | Identificó los 5 requisitos principales para un sistema de inventario en Java.                          |
| 2. Diseño de clases | Propuso las clases necesarias y sus atributos con sus respectivos tipos de datos.                       |
| 3. Clase Producto   | Generó el código Java de la clase `Producto`, incluyendo atributos, constructor, métodos `get` y `set`. |
| 4. Mejoras          | Revisó el código y propuso 3 mejoras concretas para hacerlo más completo y adecuado.                    |

**Comparación:** El pedido de una sola vez produjo una respuesta más general y menos organizada. En cambio, al dividir la tarea en pasos, la respuesta fue más específica y permitió construir el sistema progresivamente, haciendo que el código de `Producto` estuviera relacionado con el diseño realizado anteriormente.

## Ejercicio 6: Prompt estructurado y autocrítica

### Evaluación

| Qué revisar                                      | Cumple (Sí / No) |
| ------------------------------------------------ | ---------------- |
| ¿Tiene las 4 columnas pedidas?                   | Sí               |
| ¿Incluye el bloqueo después de 3 intentos?       | Sí               |
| ¿Incluye casos con campos vacíos?                | Sí               |
| ¿Indica qué casos agregó en la autocrítica?      | Sí               |
| ¿Hay algún caso repetido o que no tenga sentido? | No               |

### Prompt estructurado y autocrítica

```text
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>

Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```

### Observación

El prompt estructurado permitió obtener una respuesta más organizada porque separó el rol, el contexto, la tarea y el formato esperado. La autocrítica permitió detectar y agregar casos límite que podían faltar en la primera tabla.

- [Bitacora de tecnicas avanzadas](prompts/BITACORA.md)
