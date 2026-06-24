# Módulo 6: Asistencias y Validaciones

## Descripción General

El Módulo de Asistencias y Validaciones tiene como propósito gestionar automáticamente el control de asistencia de aprendices, instructores y demás actores institucionales mediante el uso de reconocimiento facial.

Este módulo recibe la información generada por el Módulo de Reconocimiento Facial y realiza las validaciones necesarias para determinar:

* La entrada del usuario al ambiente.
* La salida del usuario del ambiente.
* La correspondencia entre el usuario y el ambiente asignado.
* La puntualidad de asistencia.
* Los retrasos o incumplimientos de horario.

Su funcionamiento depende de la integración con los módulos de Horarios, Ambientes y Actores Institucionales.

---

# RF-6 Asistencias y Validaciones

## Objetivo

Gestionar el registro automático de asistencias mediante reconocimiento facial, validando la ubicación del usuario y el cumplimiento de los horarios establecidos.

---

# RF-6.1 Registrar entrada y salida del usuario

## Descripción

Permite registrar automáticamente los eventos de entrada y salida de un usuario cuando este es identificado mediante reconocimiento facial.

Cada evento queda almacenado con fecha, hora y ambiente asociado.

## Entradas

* Usuario identificado.
* Fecha actual.
* Hora actual.
* Ambiente detectado.

## Proceso

1. El sistema recibe la identificación facial.
2. Verifica que exista una programación activa.
3. Registra la hora de ingreso.
4. Al finalizar la jornada registra la hora de salida.
5. Guarda la información en la base de datos.

## Datos almacenados

```json
{
  "usuarioId": "UUID",
  "ambienteId": "UUID",
  "fecha": "2026-06-24",
  "horaEntrada": "07:00:12",
  "horaSalida": "12:05:20"
}
```

## Salidas

* Registro de entrada exitoso.
* Registro de salida exitoso.
* Actualización del historial de asistencia.

## Relación con el SRS

El SRS establece que el sistema debe registrar automáticamente la fecha y hora del reconocimiento facial sin intervención manual.

Asimismo, la información debe visualizarse posteriormente dentro del historial de asistencias.

## Criterios de Aceptación

* La hora se registra automáticamente.
* La fecha se registra automáticamente.
* No se requiere digitación manual.
* El registro queda asociado al usuario correcto.
* El registro queda asociado al ambiente correcto.

---

# RF-6.2 Validar si el usuario está en el ambiente correcto

## Descripción

Permite verificar que el usuario se encuentre en el ambiente de formación que tiene asignado según su horario académico.

Esta validación evita que se registren asistencias en ambientes incorrectos.

## Entradas

* Usuario identificado.
* Ambiente actual.
* Horario programado.
* Ficha de formación.

## Proceso

1. El sistema identifica al usuario.
2. Consulta la programación académica.
3. Obtiene el ambiente asignado.
4. Compara el ambiente actual con el programado.
5. Determina si la asistencia es válida.

## Escenarios

### Ambiente Correcto

```text
Usuario identificado
        ↓
Ambiente actual = Ambiente programado
        ↓
Asistencia válida
```

### Ambiente Incorrecto

```text
Usuario identificado
        ↓
Ambiente actual ≠ Ambiente programado
        ↓
Incidencia registrada
```

## Salidas

### Validación exitosa

```text
Asistencia válida
```

### Validación fallida

```text
Usuario fuera del ambiente asignado
```

## Reglas de Negocio

* Un usuario únicamente podrá registrar asistencia en ambientes autorizados.
* El ambiente debe corresponder al horario activo.
* El sistema registrará incidencias cuando exista inconsistencia.

## Dependencias

Este requisito depende directamente de:

* Módulo 2: Estructura Institucional.
* Módulo 3: Infraestructura y Ambientes.
* Módulo 7: Actores Institucionales.
* Módulo 8: Horarios e Incidencias.

## Criterios de Aceptación

* El sistema consulta correctamente la programación.
* La validación ocurre automáticamente.
* Se genera una observación cuando el ambiente no coincide.
* La asistencia no se marca como válida cuando existe inconsistencia.

---

# RF-6.3 Cálculo de Retrasos

## Descripción

Permite determinar si un usuario llegó puntualmente o con retraso a una sesión de formación.

El cálculo se realiza comparando la hora de ingreso registrada con la hora de inicio programada.

## Entradas

* Hora programada de inicio.
* Hora real de ingreso.
* Tolerancia institucional.

## Proceso

1. Se obtiene la hora programada.
2. Se obtiene la hora de ingreso.
3. Se calcula la diferencia entre ambas.
4. Se clasifica el resultado.

## Fórmula

```text
Retraso = HoraIngreso - HoraProgramada
```

## Ejemplo

### Caso 1: Puntual

```text
Hora programada: 07:00
Hora ingreso: 06:58

Resultado:
Puntual
```

### Caso 2: Retraso

```text
Hora programada: 07:00
Hora ingreso: 07:15

Resultado:
15 minutos de retraso
```

## Clasificaciones

| Estado       | Condición                      |
| ------------ | ------------------------------ |
| Puntual      | Hora ingreso ≤ Hora programada |
| Retraso      | Hora ingreso > Hora programada |
| Inasistencia | No existe registro facial      |

## Relación con el SRS

El SRS establece que el sistema debe registrar automáticamente la fecha y hora del reconocimiento facial y permitir posteriormente la consulta de retardos, asistencias e inasistencias.

Además, los reportes deberán generarse utilizando esta información para determinar asistencias, llegadas tarde e inasistencias.

## Salidas

* Estado de puntualidad.
* Minutos de retraso.
* Registro de incidencia.
* Actualización de historial.

## Criterios de Aceptación

* El cálculo debe realizarse automáticamente.
* El usuario no interviene en el proceso.
* El sistema registra el número exacto de minutos de retraso.
* El historial refleja el estado correspondiente.

---

# Flujo General del Módulo

```text
Reconocimiento Facial
        ↓
Usuario Identificado
        ↓
Validar Ambiente
        ↓
Ambiente Correcto
        ↓
Registrar Entrada
        ↓
Consultar Horario
        ↓
Calcular Retraso
        ↓
Actualizar Historial
        ↓
Generar Evidencia de Asistencia
```

# Dependencias del Módulo

El módulo de Asistencias y Validaciones depende de:

* Módulo 3: Infraestructura y Ambientes.
* Módulo 5: Reconocimiento Facial.
* Módulo 7: Instructores, Aprendices y Directivos.
* Módulo 8: Horarios, Observaciones e Incidencias.

Estas dependencias permiten validar correctamente quién ingresó, dónde ingresó y si cumplió con el horario asignado.

# Conclusión

El Módulo 6 transforma la identificación biométrica en información académica útil para la institución. A través del registro automático de entradas y salidas, la validación del ambiente y el cálculo de retrasos, FaceLit garantiza un control de asistencia preciso, automatizado y alineado con la programación académica del SENA.
