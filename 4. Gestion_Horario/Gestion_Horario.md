# Módulo 4 – Gestión de Horarios

## Resumen del Módulo de Gestión de Horarios

Este módulo permite al **Administrador** gestionar completamente los horarios académicos de las fichas de formación. Desde este módulo podrá registrar, consultar, editar, eliminar y visualizar los horarios, garantizando que la programación académica no presente conflictos entre ambientes e instructores.

Cada horario estará conformado por la siguiente información:

* Ficha de formación.
* Día de la semana.
* Hora de inicio.
* Hora de finalización.
* Ambiente asignado.
* Instructor responsable.

Antes de registrar un horario, el sistema verificará automáticamente que:

* La ficha exista.
* El ambiente exista y se encuentre disponible en la franja seleccionada.
* El instructor exista y no tenga otro horario asignado en el mismo día y hora.
* No existan conflictos de programación que impidan registrar el horario.

Una vez registrado el horario, el Administrador podrá:

* Registrar nuevos horarios.
* Consultar todos los horarios existentes.
* Editar la información de un horario.
* Eliminar un horario.
* Visualizar toda la información del horario.

---

## Gestión de Ambientes

Cada horario tendrá asociado uno o varios ambientes donde se desarrollará la formación.

El sistema permitirá que un mismo ambiente pueda utilizarse en diferentes horarios durante el día, siempre y cuando las franjas horarias no se crucen.

De igual forma, un horario podrá involucrar varios ambientes cuando la programación académica así lo requiera.

Sin embargo, el sistema deberá impedir conflictos como los siguientes:

* Dos instructores utilizando el mismo ambiente en el mismo día y a la misma hora.
* Dos horarios distintos ocupando simultáneamente el mismo ambiente.
* Asignaciones que generen choques de programación.

Antes de guardar cualquier modificación, el sistema validará nuevamente la disponibilidad de los ambientes involucrados.

---

# RF-4.1 Registrar Horarios de cada Ficha

## Objetivo

Permitir al Administrador registrar los horarios oficiales de cada ficha para que posteriormente puedan ser utilizados en la consulta de horarios, ingreso de instructores y control de asistencia mediante reconocimiento facial.

## Funcionalidades

El Administrador podrá:

* Registrar horarios.
* Consultar horarios.
* Editar horarios.
* Eliminar horarios.
* Visualizar el detalle de cada horario.

Cada horario deberá contener:

* Ficha.
* Programa de formación.
* Día.
* Hora de inicio.
* Hora de finalización.
* Ambiente.
* Instructor.

El sistema validará automáticamente:

* Disponibilidad del ambiente.
* Disponibilidad del instructor.
* Existencia de la ficha.
* Conflictos de programación.

Si toda la información es válida, el horario será almacenado y quedará disponible para todo el sistema.

---

## Reglas de Negocio

* Una ficha puede tener múltiples horarios.
* Un horario pertenece a una única ficha.
* Un horario debe tener al menos un instructor asignado.
* Un horario debe tener al menos un ambiente.
* No podrán existir dos horarios ocupando el mismo ambiente en la misma franja horaria.
* Un instructor no podrá estar asignado en dos horarios diferentes que se crucen en el tiempo.
* Cada modificación realizada sobre un horario deberá registrarse en la bitácora del sistema.

---

# RF-4.2 Consulta de Horarios

## Objetivo

Permitir que cada usuario consulte únicamente los horarios que le corresponden según su rol dentro del sistema.

## Consulta según el rol

### Administrador

El Administrador podrá consultar:

* Todos los horarios registrados.
* Horarios por ficha.
* Horarios por ambiente.
* Horarios por instructor.
* Detalle completo de cualquier horario.

Además podrá:

* Editar.
* Eliminar.
* Consultar información completa del horario.

---

### Instructor

El Instructor únicamente podrá visualizar los horarios donde haya sido asignado previamente por el Administrador.

Podrá visualizar:

* Día.
* Hora de inicio.
* Hora de finalización.
* Ambiente.
* Ficha.
* Programa de formación.
* Aprendices asociados a la ficha.

No podrá modificar ninguna información.

El Instructor solamente podrá ingresar al sistema cuando tenga un horario previamente asignado.

Su acceso dependerá completamente de la programación realizada por el Administrador.

---

### Aprendiz

El Aprendiz únicamente podrá consultar el horario correspondiente a la ficha donde se encuentra asociado.

No podrá visualizar:

* Horarios de otras fichas.
* Horarios de otros aprendices.
* Horarios generales del sistema.

Solamente visualizará:

* Día.
* Hora.
* Instructor.
* Ambiente.
* Programa de formación.

---

## Reglas de Consulta

Cada usuario únicamente podrá consultar la información autorizada por su rol.

El sistema deberá impedir el acceso a horarios que no pertenezcan al usuario autenticado.

Toda consulta quedará registrada en la bitácora del sistema.

---

# RF-4.3 Asociación de Instructores a Horarios

## Objetivo

Permitir que el Administrador asigne instructores a los horarios previamente registrados.

## Funcionalidades

El Administrador podrá:

* Asociar un instructor a un horario.
* Cambiar el instructor asignado.
* Eliminar la asociación.
* Consultar el instructor responsable.

Antes de realizar la asociación, el sistema verificará que:

* El instructor exista.
* El instructor se encuentre activo.
* El instructor no tenga otro horario en la misma franja.
* No existan conflictos de programación.

Una vez realizada la asociación, el horario quedará disponible para el Instructor.

---

## Reglas de Negocio

* Un instructor puede estar asignado a muchos horarios.
* Un horario debe tener un instructor responsable.
* Un instructor no podrá estar asignado simultáneamente a dos horarios que se crucen.
* Todas las asociaciones deberán quedar registradas. 

---

# Excepciones de Horarios

El módulo permitirá gestionar situaciones excepcionales que modifiquen temporalmente un horario sin eliminar su programación original.

Entre las excepciones se encuentran:

* Cambio temporal de instructor por reemplazo.
* Instructor incapacitado o con permiso.
* Ambiente temporalmente inactivo.
* Cambio temporal de ambiente.
* Reprogramación de una clase.
* Cancelación de una sesión académica.
* Eventos institucionales que afecten la programación.

Cuando exista una excepción, el sistema deberá reflejar automáticamente dicha modificación en las consultas de horarios para Administradores, Instructores y Aprendices.

Las excepciones deberán quedar registradas en la bitácora con:

* Fecha.
* Hora.
* Usuario que realizó el cambio.
* Motivo de la excepción.
* Información anterior.
* Nueva información.

---

# Flujo General del Módulo

```text
Administrador
        │
        ▼
Registra Horario
        │
        ▼
Selecciona Ficha
        │
        ▼
Selecciona Día y Horario
        │
        ▼
Selecciona Ambiente
        │
        ▼
Selecciona Instructor
        │
        ▼
El Sistema valida:

✔ Disponibilidad del instructor
✔ Disponibilidad del ambiente
✔ Existencia de la ficha
✔ Conflictos de horario

        │
        ▼
Horario Registrado
        │
        ▼
Disponible para:

• Consulta del Administrador
• Consulta del Instructor
• Consulta del Aprendiz
• Validación de asistencia
• Reconocimiento facial
```


# Restricciones del Sistema

El sistema no permitirá:

* Registrar horarios con ambientes ocupados.
* Registrar horarios con instructores ocupados.
* Registrar horarios sin ficha.
* Registrar horarios sin instructor.
* Registrar horarios sin ambiente.
* Consultar información no autorizada según el rol.
* Generar conflictos entre horarios, instructores o ambientes.

Todas las operaciones realizadas en este módulo deberán registrarse en la bitácora del sistema para garantizar la trazabilidad de la información.
