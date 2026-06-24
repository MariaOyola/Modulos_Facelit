# README -- Módulo Gestión de Ambientes

## Descripción

El módulo **Gestión de Ambientes** permite administrar los ambientes
institucionales dentro del sistema, facilitando su registro, consulta y
asignación de fichas.

## Objetivo

Permitir la gestión eficiente de ambientes mediante operaciones de
creación, consulta, asignación y eliminación.

## Alcance

  Código   Requerimiento
  -------- -----------------------------------
  RF-2     Gestión de Ambientes
  RF-2.1   Registrar ambientes y eliminarlos
  RF-2.2   Consultar ambientes
  RF-2.3   Asignar fichas a ambientes

## RF-2.1 Registrar ambientes y eliminarlos

### Acciones

-   Registrar un nuevo ambiente.
-   Editar información (si aplica).
-   Eliminar ambientes existentes.
-   Validar duplicados.

### Datos sugeridos

-   Código
-   Nombre
-   Tipo
-   Capacidad
-   Estado
-   Ubicación

### Reglas

-   Código único.
-   No eliminar ambientes con fichas activas.
-   Campos obligatorios completos.

## RF-2.2 Consultar ambientes

### Acciones

-   Listar ambientes.
-   Buscar por código
-   Ver detalle.

## RF-2.3 Asignar fichas a ambientes

### Acciones

-   Seleccionar ficha.
-   Seleccionar ambiente.
-   Registrar asignación.
-   Consultar asignaciones.

### Reglas

-   Solo ambientes disponibles.
-   Validar capacidad.
-   Evitar conflictos.

## Flujo

Registrar Ambiente → Consultar → Seleccionar → Asignar Ficha → Confirmar

## Consideraciones Técnicas

-   Validaciones frontend/backend.
-   Persistencia de relaciones.
-   Auditoría de operaciones.

## Criterios de aceptación

-   Registro correcto.
-   Eliminación válida.
-   Consulta actualizada.
-   Asignación exitosa.
