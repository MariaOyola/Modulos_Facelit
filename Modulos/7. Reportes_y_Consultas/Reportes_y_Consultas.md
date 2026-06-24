
# RF-7 — REPORTES Y CONSULTAS

## Descripción

El módulo **RF-7 — Reportes y Consultas** permite consultar, visualizar y analizar la información histórica de asistencia registrada en el sistema, aplicando restricciones según el rol del usuario.

Este módulo garantiza que cada actor acceda únicamente a la información autorizada.

## Objetivos

- Consultar historial de asistencia.
- Generar reportes según el nivel de acceso del usuario.
- Facilitar el seguimiento y análisis de asistencia.
- Visualizar información histórica mediante reportes y calendario.

---

# Roles y Permisos

| Rol | Permisos |
|---|---|
| Administrador | Puede consultar y generar todos los reportes del sistema. |
| Instructor | Solo puede consultar reportes relacionados con sus propias fichas asignadas. |
| Aprendiz | Solo puede consultar su historial y reportes personales. |

---

# Requerimientos Funcionales

## RF-7.1 Reporte de asistencia por usuario

### Descripción
Permite consultar el historial de asistencia de un usuario específico según permisos del rol.

### Acceso
- Administrador: consulta cualquier usuario.
- Instructor: consulta únicamente aprendices de sus fichas.
- Aprendiz: consulta únicamente su propio historial.

### Entradas
- Usuario.
- Rango de fechas.
- Estado de asistencia.

### Proceso
1. Validar permisos del usuario autenticado.
2. Seleccionar usuario objetivo.
3. Aplicar filtros.
4. Recuperar registros.
5. Mostrar resultados.

### Salidas
- Historial de asistencia.
- Fecha y hora.
- Ambiente asociado.
- Estado de asistencia.

### Criterios de aceptación
- Solo se muestran datos autorizados.
- Permite filtrar por fechas.
- Presenta resultados ordenados cronológicamente.
- Muestra mensaje cuando no existan registros.

---

## RF-7.2 Reporte de asistencia por ficha

### Descripción
Genera reportes agrupados por ficha respetando restricciones de acceso.

### Acceso
- Administrador: acceso a todas las fichas.
- Instructor: acceso únicamente a sus fichas asignadas.
- Aprendiz: sin acceso a reportes globales por ficha.

### Entradas
- Identificador de ficha.
- Rango de fechas.
- Filtros opcionales.

### Proceso
1. Validar permisos.
2. Seleccionar ficha.
3. Recuperar asistencias.
4. Consolidar resultados.
5. Mostrar reporte.

### Salidas
- Total de asistencias.
- Usuarios registrados.
- Resumen estadístico.

### Criterios de aceptación
- Solo se consultan fichas autorizadas.
- Información agrupada correctamente.
- Permite filtrado por periodo.

---

## RF-7.3 Historial de asistencia tipo calendario

### Descripción
Visualiza el historial de asistencia en formato calendario.

### Acceso
- Administrador: acceso global.
- Instructor: únicamente fichas asignadas.
- Aprendiz: únicamente historial propio.

### Entradas
- Usuario o ficha.
- Periodo.

### Proceso
1. Validar permisos.
2. Cargar historial.
3. Organizar eventos por fecha.
4. Mostrar calendario.

### Salidas
- Vista calendario.
- Indicadores visuales.
- Detalle diario.

### Criterios de aceptación
- Navegación entre periodos.
- Actualización dinámica.
- Restricción por rol aplicada correctamente.

---

# Reglas de Negocio

- El administrador puede generar cualquier reporte.
- El instructor solo puede visualizar reportes de sus fichas.
- El aprendiz solo puede visualizar sus reportes personales.
- No se permite modificar registros históricos desde este módulo.
- Solo se consultan registros existentes.

---

# Dependencias

- RF Registro de Asistencia.
- Gestión de Usuarios.
- Gestión de Ambientes.

---

# Consideraciones Técnicas

- Implementar paginación.
- Optimizar consultas por rango de fechas.
- Registrar auditoría de consultas.
- Preparar exportación futura (PDF/Excel).

---

# Resultado Esperado

Permitir consultar información histórica de asistencia de forma segura, organizada y acorde al rol del usuario.
