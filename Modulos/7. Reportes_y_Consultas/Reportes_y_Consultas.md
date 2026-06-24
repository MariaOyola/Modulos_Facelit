# RF-7 -- REPORTES Y CONSULTAS

## Descripción

El módulo **RF-7 -- Reportes y Consultas** permite visualizar, consultar
y generar información relacionada con la asistencia registrada en el
sistema.

## Objetivos

-   Consultar historial de asistencia.
-   Generar reportes por usuario o ficha.

------------------------------------------------------------------------

# Requerimientos Funcionales

## RF-7.1 Reporte de asistencia por usuario

### Descripción

Permite consultar el historial de asistencia de un usuario específico.

### Entradas

-   Usuario.
-   Rango de fechas.
-   Filtros por mes y estados.

### Proceso

1.  Seleccionar usuario.
2.  Aplicar filtros.
3.  Consultar registros.
4.  Mostrar resultados.

### Salidas

-   Lista de asistencias.
-   Fecha y hora.
-   Ambiente asociado.
-   Estado.

### Criterios de aceptación

-   Consulta por usuario.
-   Filtro por fechas.
-   Orden cronológico.
-   Mensaje cuando no existan registros.

------------------------------------------------------------------------

## RF-7.2 Reporte de asistencia por ficha

### Descripción

Genera reportes agrupados por ficha.

### Entradas

-   Identificador de ficha.
-   Rango de fechas.
-   Filtros opcionales.

### Proceso

1.  Seleccionar ficha.
2.  Recuperar registros.
3.  Consolidar información.
4.  Mostrar resultados.

### Salidas

-   Total de asistencias.
-   Usuarios registrados.
-   Resumen estadístico.

### Criterios de aceptación

-   Consulta de fichas existentes.
-   Agrupación correcta.
-   Filtrado por periodo.

------------------------------------------------------------------------

## RF-7.3 Historial de asistencia tipo calendario

### Descripción

Visualiza el historial mediante calendario.

### Entradas

-   Usuario o ficha.
-   Periodo seleccionado.

### Proceso

1.  Seleccionar consulta.
2.  Cargar historial.
3.  Organizar por fechas.

### Salidas

-   Indicadores visuales.
-   Detalle diario.

### Criterios de aceptación

-   Navegación por periodos.
-   Actualización dinámica.

------------------------------------------------------------------------

# Reglas de Negocio

-   Solo registros existentes.
-   Respetar permisos.
-   No modificar históricos.

------------------------------------------------------------------------

# Dependencias

-   Registro de Asistencia.
-   Gestión de Usuarios.
-   Gestión de Ambientes.

------------------------------------------------------------------------

# Consideraciones Técnicas

-   Implementar paginación.
-   Optimizar consultas.
-   Preparar exportación futura.

------------------------------------------------------------------------

# Resultado Esperado

Consultar y analizar información histórica de asistencia de manera
rápida y organizada.
