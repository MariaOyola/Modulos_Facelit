# Módulo 8 – Gestión de Notificaciones

## Resumen del Módulo de Notificaciones

Este módulo permite al sistema generar, almacenar y distribuir notificaciones automáticas a los diferentes usuarios según su rol dentro de la aplicación.

Las notificaciones tienen como objetivo mantener informados a los Administradores, Instructores y Aprendices sobre eventos importantes relacionados con el funcionamiento del sistema.

Cada notificación se almacena en un buzón interno del usuario, donde podrá consultarla posteriormente desde la interfaz del sistema. De igual manera, las notificaciones clasificadas como importantes podrán enviarse automáticamente al correo electrónico institucional del usuario.

El funcionamiento es similar al de un gestor de correo electrónico como Gmail: cada evento genera una notificación, esta queda almacenada en el historial del aplicativo y, cuando corresponde, también es enviada por correo electrónico.

---

# Tipos de Notificaciones según el Rol

## Administrador

El Administrador recibirá notificaciones relacionadas con la administración general del sistema, por ejemplo:


* Actualización de información de usuarios.
* Eliminación de registros.
* Nuevas fichas creadas.
* Cambios de horarios.
* Cambios de ambientes.
* Registros de asistencia realizados.
* Intentos de acceso no autorizados.
* Errores del sistema.
* Eventos registrados en la bitácora.
* Solicitudes pendientes de aprobación.

Estas notificaciones permiten mantener informado al Administrador sobre todas las actividades relevantes del sistema.

---

## Instructor

El Instructor recibirá notificaciones relacionadas con las fichas que tiene asignadas.

Ejemplos:

* Inicio próximo de una clase.
* Registro de asistencia realizado.
* Aprendiz con ingreso tardío.
* Aprendiz ausente.
* Cambio de ambiente.
* Cambio de horario.
* Registro facial pendiente de un aprendiz.
* Novedades relacionadas con sus grupos de formación.

El Instructor únicamente visualizará información correspondiente a las fichas donde se encuentre asignado.

---

## Aprendiz

El Aprendiz recibirá notificaciones relacionadas con su proceso de formación.

Ejemplos:

* Llegaste tarde al horario programado.
* Se registró correctamente tu asistencia.
* Cambio de ambiente.
* Cambio de horario.
* Registro facial pendiente.
* Recordatorio de actualización de datos.
* Inasistencia registrada.
* Avisos institucionales dirigidos a su ficha.

El Aprendiz únicamente podrá visualizar las notificaciones asociadas a su propia cuenta.

---

# Funcionamiento General

Cada vez que ocurra un evento importante dentro del sistema, el motor de notificaciones realizará automáticamente las siguientes acciones:

1. Detectar el evento generado.
2. Clasificar la notificación según su tipo.
3. Identificar el usuario o usuarios destinatarios.
4. Crear el mensaje correspondiente.
5. Almacenar la notificación en el buzón interno del usuario.
6. Marcar inicialmente la notificación como **No leída**.
7. Si la notificación requiere envío externo, remitirla también al correo electrónico institucional.
8. Registrar el evento en la bitácora del sistema.

---

# RF-8.1 Generación Automática de Notificaciones

## Objetivo

Permitir que el sistema genere automáticamente notificaciones cada vez que ocurra un evento relevante durante la operación del aplicativo.

## Funcionalidades

El sistema podrá generar notificaciones cuando ocurran eventos como:

* Registro de asistencia.
* Llegadas tarde.
* Inasistencias.
* Cambios de horario.
* Cambios de ambiente.
* Registro de nuevos usuarios.
* Actualización de información.
* Eliminación de registros.
* Intentos de acceso no autorizados.
* Registro facial pendiente.
* Eventos administrativos.
* Errores importantes del sistema.

Cada notificación contendrá como mínimo:

* Tipo de notificación.
* Categoría.
* Usuario destinatario.
* Fecha.
* Hora.
* Mensaje.
* Estado (Leída / No leída).

---

## Reglas de Negocio

* Todas las notificaciones serán generadas automáticamente.
* Ningún evento válido deberá perderse.
* Toda notificación deberá almacenarse en el historial del usuario.
* Las notificaciones iniciarán con estado **No leída**.
* El sistema registrará la creación de cada notificación en la bitácora.

---

# RF-8.2 Visualización de Notificaciones

## Objetivo

Permitir que cada usuario consulte desde la interfaz las notificaciones que le corresponden según su rol.

## Funcionalidades

Cada usuario dispondrá de un centro de notificaciones representado mediante un icono de campana.

Desde este módulo podrá:

* Consultar todas sus notificaciones.
* Visualizar el detalle de cada una.
* Marcar como leídas.
* Filtrar por:

  * Todas.
  * No leídas.
  * Leídas.
* Consultar el historial completo de notificaciones.

Cada notificación mostrará:

* Categoría.
* Fecha.
* Hora.
* Estado.
* Mensaje.

---

## Visualización según el Rol

### Administrador

Visualizará únicamente las notificaciones relacionadas con la administración del sistema y los eventos generados por los usuarios.

---

### Instructor

Visualizará únicamente las notificaciones relacionadas con las fichas y aprendices bajo su responsabilidad.

---

### Aprendiz

Visualizará únicamente las notificaciones relacionadas con su propio proceso académico.

---

## Reglas de Negocio

* Ningún usuario podrá visualizar notificaciones pertenecientes a otro usuario.
* El historial permanecerá disponible hasta que la política de almacenamiento determine su eliminación.
* Marcar una notificación como leída actualizará inmediatamente su estado.
* Toda consulta quedará registrada en la bitácora.

---

# RF-8.3 Envío de Notificaciones por Correo Electrónico

## Objetivo

Permitir que las notificaciones importantes también sean enviadas automáticamente al correo electrónico institucional del usuario.

## Funcionalidades

Cuando una notificación sea clasificada como importante o crítica, el sistema enviará automáticamente un correo electrónico al destinatario.

Ejemplos:

* Cambio de ambiente.
* Cambio de horario.
* Registro facial pendiente.
* Llegada tarde.
* Inasistencia.
* Anomalía detectada.
* Avisos institucionales.
* Eventos administrativos relevantes.

El envío del correo no reemplaza la notificación interna; ambas permanecerán disponibles.

---

## Reglas de Negocio

* El usuario deberá tener registrado un correo electrónico válido.
* El envío se realizará automáticamente mediante el servidor de correo configurado.
* Si el envío falla, el sistema realizará hasta tres reintentos.
* Si después de los reintentos continúa el error, la notificación quedará marcada como **Pendiente de envío**.
* El historial de envíos quedará registrado en la bitácora.

---

# Flujo General del Módulo

```text
Ocurre un evento en el sistema
            │
            ▼
El sistema detecta el evento
            │
            ▼
Clasifica la notificación
            │
            ▼
Identifica los usuarios destinatarios
            │
            ▼
Genera la notificación
            │
            ▼
La almacena en el buzón interno
            │
            ▼
Marca como "No leída"
            │
            ▼
¿La notificación requiere correo?
        │                 │
       Sí                 No
        │                 │
        ▼                 ▼
Envía correo          Finaliza proceso
electrónico
        
```

---

# Relaciones del Módulo

## Usuario → Notificaciones

Un usuario puede recibir múltiples notificaciones.

Cada notificación pertenece únicamente a un usuario.

---

## Evento → Notificación

Un evento puede generar una o varias notificaciones.

Cada notificación es consecuencia de un único evento registrado.

---

## Notificación → Correo Electrónico

Una notificación puede generar un envío por correo electrónico cuando su nivel de importancia lo requiera.

El envío queda asociado al historial de la notificación.

---

# Restricciones del Sistema

El sistema no permitirá:

* Visualizar notificaciones de otros usuarios.
* Eliminar registros del historial sin autorización.
* Enviar correos a direcciones inválidas.
* Generar notificaciones duplicadas para un mismo evento.
* Perder notificaciones generadas por eventos válidos.

Todas las operaciones realizadas en este módulo deberán registrarse en la bitácora del sistema para garantizar la trazabilidad de la información.
