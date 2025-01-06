# Creación de un Cubo en SQL Server Analysis Services (SSAS)

## Descripción General
Este documento describe el proceso de creación de un cubo OLAP utilizando SQL Server Analysis Services (SSAS), trabajando con la base de datos **Adventure Works**. Se detallan los pasos realizados, las configuraciones implementadas y las funcionalidades añadidas al modelo multidimensional.

---

## Pasos Realizados

### 1. **Orígenes de Datos**
Se configuró la conexión a la base de datos **Adventure Works**, que sirve como el origen principal de datos para el cubo. Esto incluye:
- Selección del servidor SQL y la base de datos Adventure Works.
- Verificación de las credenciales y prueba de la conexión para asegurar el acceso a los datos.

---

### 2. **Vista del Origen de Datos (DSV)**
Se creó una vista lógica del origen de datos para filtrar y organizar las tablas necesarias:
- **Tablas Seleccionadas**: Se incluyeron tablas relevantes.
- **Relaciones**: Se definieron relaciones entre las tablas, alineándolas con claves primarias y foráneas.
- **Campos Calculados**: Se añadieron columnas calculadas para enriquecer el análisis. Por ejemplo, cálculos personalizados en costos y ventas.

---

### 3. **Creación del Cubo**
Se creó un cubo que contiene dimensiones para realizar análisis multidimensionales:
- **Dimensiones Incluidas**:
  - `DimDate`
  - `DimCustomers`
  - `DimProduct`

---

### 4. **Jerarquías en Dimensiones**
Cada dimensión se enriqueció con jerarquías para facilitar la navegación y análisis de datos:
- **DimDate**:
  - Jerarquía: Año → Trimestre → Mes → Día
- **DimCustomers**:
  - Jerarquía: País → Región → Ciudad
- **DimProduct**:
  - Jerarquía: Categoría → Subcategoría → Producto

---

### 5. **Creación de un KPI (Key Performance Indicator)**
Se configuró un KPI para medir el desempeño en costos y ventas:
- **Expresión de Valor**: `Total Product Cost`
- **Expresión de Objetivo**: `Sales Amount`
- Indicadores visuales para representar el cumplimiento del objetivo.

---

### 6. **Tendencia**
Se definió una tendencia para analizar el cambio en las ventas y costos a lo largo del tiempo. Esto permite a los usuarios identificar patrones y comportamientos en los datos históricos.

---

### 7. **Creación de Acciones**
Se crearon acciones personalizadas que permiten a los usuarios interactuar con los datos:
- **Acción de Exportación**: Permitir a los usuarios exportar los datos del cubo a **Excel** para análisis detallado.

---

### 8. **Perspectivas**
Se añadieron perspectivas para simplificar la experiencia del usuario final:
- **Perspectiva de Ventas**: Incluye las medidas y dimensiones relevantes para el análisis de ventas, ocultando datos no relacionados.

---

## Conclusión
Este cubo OLAP proporciona una estructura eficiente para el análisis multidimensional de los datos de Adventure Works. Las funcionalidades añadidas, como jerarquías, KPIs, tendencias, acciones y perspectivas, mejoran la usabilidad y el valor analítico del modelo.

**Herramientas utilizadas**: SQL Server Analysis Services, Excel

**Próximos pasos**: Validar el modelo con usuarios finales y optimizar las consultas para mejorar el rendimiento en escenarios de producción.

