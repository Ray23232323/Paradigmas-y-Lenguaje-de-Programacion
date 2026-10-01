# TP1 / AE2 - Evolución de Arquitectura Orientada a Objetos

Asignatura: Paradigmas y Lenguajes de Programación II  
Carrera: Ingeniería en Sistemas de Información  
Estudiante: Máximo Lautaro Márquez  


* Descripción del Proyecto

Este repositorio contiene la evolución de la aplicación **TP1** hacia la **Actividad Evaluativa 2 (AE2)**. El objetivo principal de la entrega es refinarlas capacidades de diseño orientado a objetos en Java, aplicando pilares del paradigma como la **abstracción**, el **polimorfismo**, el uso de **múltiples interfaces**, criterios de **ordenamiento avanzado**, manejo de **excepciones propias del dominio** y **persistencia de datos** desacoplada.

El dominio del sistema gestiona entidades comerciales como *Clientes*, *Empleados*, *Proveedores*, *Productos*, *Servicios* y la generación de *Ofertas Comerciales* y *Facturas*.


* Requisitos de la AE2 Implementados

1. **Polimorfismo y Clase Abstracta:**
   * Refactorización de la clase base `Persona` a clase `abstract`.
   * Implementación del método abstracto `obtenerTipo()` sobreescrito polimórficamente por `Cliente`, `Empleado` y `Proveedor`.

2. **Múltiples Interfaces:**
   * `Facturable`: Define el contrato para el cálculo de totales económicos.
   * `Imprimible`: Define el contrato para obtener resúmenes textuales.
   * La clase `OfertaComercial` implementa ambas interfaces simultáneamente.

3. **Criterios de Ordenamiento (`Comparable` y `Comparator`):**
   * **Orden Natural:** La clase `Producto` implementa `Comparable<Producto>` para ordenar elementos por su **precio** de menor a mayor.
   * **Orden Alternativo:** Implementación de `ProductoPorNombreComparator` mediante `Comparator<Producto>` para ordenar alfabéticamente por **nombre**.

4. **Excepción Propia del Dominio:**
   * Creación de `OfertaSinItemsException` para interceptar e impedir el cálculo o emisión de ofertas comerciales vacías.

5. **Persistencia e Infraestructura:**
   * Implementación de la clase `FacturaRepository` aplicando el **Principio de Responsabilidad Única (SRP)** para guardar y leer los datos en un archivo de texto plano (`datos_resumenes.txt`).

---

## Estructura del Proyecto

```text
.
├── README.md
└── Tp1/
    ├── Cliente.java
    ├── Departamento.java
    ├── Empleado.java
    ├── Factura.java
    ├── Facturable.java
    ├── FacturaRepository.java
    ├── Imprimible.java
    ├── Main.java
    ├── OfertaComercial.java
    ├── OfertaSinItemsException.java
    ├── Pago.java
    ├── Persona.java
    ├── Producto.java
    ├── ProductoPorNombreComparator.java
    ├── Proveedor.java
    └── Servicio.java
