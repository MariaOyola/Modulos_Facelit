# Módulo 9: Perfil y Personalización

## Descripción General

El Módulo de Perfil y Personalización permite a los usuarios administrar su información personal y adaptar la interfaz del sistema según sus preferencias.

Este módulo proporciona funcionalidades relacionadas con:

* Consulta de información personal.
* Gestión de la sesión activa.
* Configuración general de la aplicación.
* Cambio de idioma.
* Personalización visual del dashboard.

Su objetivo es mejorar la experiencia de usuario, facilitar la accesibilidad y permitir una interacción más cómoda con la plataforma FaceLit.

---

# RF-9 Perfil y Personalización

## Objetivo

Permitir que los usuarios visualicen su información personal, administren su sesión y personalicen aspectos visuales y funcionales del sistema.

---

# RF-9.1 Visualización del Perfil

## Descripción

Permite consultar la información personal registrada dentro de la plataforma.

La información mostrada corresponde a los datos almacenados durante el proceso de registro y administración de usuarios.

## Información visualizada

* Nombres.
* Apellidos.
* Tipo de documento.
* Número de documento.
* Correo electrónico.
* Rol asignado.
* Fotografía o imagen de perfil.
* Estado de la cuenta.

## Proceso

1. El usuario accede a la sección Perfil.
2. El sistema consulta la información registrada.
3. Se recuperan los datos asociados al usuario.
4. La información se presenta en pantalla.

## Salidas

* Perfil visualizado correctamente.
* Información actualizada del usuario.

## Reglas de Negocio

* El usuario únicamente puede visualizar su propia información.
* Los datos deben obtenerse desde la base de datos institucional.
* La información debe mostrarse de forma segura.

## Criterios de Aceptación

* El perfil carga correctamente.
* Los datos corresponden al usuario autenticado.
* La información se presenta de forma clara.
* No se muestran datos de otros usuarios.

---

# RF-9.2 Cerrar Sesión

## Descripción

Permite finalizar la sesión activa del usuario dentro del sistema.

Esta funcionalidad garantiza la protección de la información cuando el usuario deja de utilizar la plataforma.

## Proceso

1. El usuario selecciona la opción Cerrar Sesión.
2. El sistema invalida el token de autenticación.
3. Se eliminan las credenciales temporales.
4. El usuario es redireccionado al Login.

## Flujo

```text
Usuario
    ↓
Cerrar Sesión
    ↓
Eliminar Token
    ↓
Finalizar Sesión
    ↓
Pantalla Login
```

## Salidas

* Sesión cerrada correctamente.
* Retorno al módulo de autenticación.

## Reglas de Negocio

* No podrán realizarse operaciones protegidas después del cierre de sesión.
* El token debe invalidarse inmediatamente.
* Se deben eliminar datos temporales almacenados localmente.

## Criterios de Aceptación

* La sesión finaliza correctamente.
* El usuario es redireccionado al Login.
* No es posible acceder a rutas protegidas.

---

# RF-9.3 Configuración

## Descripción

Permite administrar las preferencias generales del sistema asociadas al usuario.

## Opciones de Configuración

* Preferencias visuales.
* Idioma.
* Tema de la aplicación.
* Notificaciones.
* Preferencias de accesibilidad.

## Proceso

1. El usuario accede a Configuración.
2. El sistema carga las preferencias actuales.
3. El usuario modifica una configuración.
4. El sistema guarda los cambios.

## Salidas

* Configuración actualizada.
* Preferencias almacenadas.

## Criterios de Aceptación

* Los cambios se guardan correctamente.
* Las configuraciones persisten entre sesiones.
* El sistema aplica las preferencias inmediatamente.

---

# RF-9.4 Configuración de Idioma

## Descripción

Permite seleccionar el idioma de visualización de la plataforma.

Esta funcionalidad mejora la accesibilidad y facilita el uso del sistema para usuarios de diferentes regiones.

## Idiomas Soportados

* Español.
* Inglés.

*(La lista puede ampliarse según las necesidades del proyecto.)*

## Proceso

1. El usuario accede a Configuración.
2. Selecciona Idioma.
3. Escoge el idioma deseado.
4. El sistema actualiza las traducciones de la interfaz.

## Flujo

```text
Configuración
      ↓
Seleccionar Idioma
      ↓
Guardar Preferencia
      ↓
Actualizar Interfaz
```

## Salidas

* Idioma actualizado.
* Interfaz traducida automáticamente.

## Reglas de Negocio

* El idioma seleccionado debe persistir entre sesiones.
* Todas las pantallas deben utilizar archivos de traducción centralizados.

## Dependencias Técnicas

En la aplicación esta funcionalidad se implementa mediante:

```text
i18n
useTranslation()
LanguageSelector
```

## Criterios de Aceptación

* El idioma cambia inmediatamente.
* La preferencia queda almacenada.
* El idioma permanece después de cerrar sesión.

---

# RF-9.5 Personalización del Dashboard (Colores)

## Descripción

Permite modificar la apariencia visual del dashboard mediante temas y esquemas de colores.

Su objetivo es mejorar la experiencia de usuario y la accesibilidad visual.

## Opciones Disponibles

* Modo Claro.
* Modo Oscuro.
* Temas institucionales.
* Paletas de colores personalizadas.

## Proceso

1. El usuario accede a Configuración.
2. Selecciona Personalización.
3. Escoge el tema visual.
4. El sistema aplica los cambios.

## Flujo

```text
Configuración
      ↓
Seleccionar Tema
      ↓
Guardar Preferencia
      ↓
Actualizar Dashboard
```

## Salidas

* Dashboard actualizado.
* Preferencias visuales guardadas.

## Reglas de Negocio

* Los cambios deben reflejarse inmediatamente.
* La preferencia debe mantenerse después del reinicio de sesión.
* La personalización no debe afectar la funcionalidad del sistema.

## Dependencias Técnicas

La funcionalidad se implementa mediante:

```text
ThemeProvider
useTheme()
ThemeToggle
```

## Criterios de Aceptación

* El usuario puede cambiar entre modo claro y oscuro.
* El dashboard actualiza su apariencia en tiempo real.
* La preferencia permanece almacenada.
* El sistema carga automáticamente el tema seleccionado al iniciar sesión.

---

# Flujo General del Módulo

```text
Usuario Autenticado
        ↓
Perfil
        ↓
Configuración
        ↓
Idioma
        ↓
Tema Visual
        ↓
Guardar Preferencias
        ↓
Dashboard Personalizado
```

# Dependencias del Módulo

El Módulo de Perfil y Personalización depende de:

* Módulo 1: Seguridad y Acceso.
* Módulo 7: Instructores, Aprendices y Directivos.

Estas dependencias permiten obtener la información personal del usuario y administrar las preferencias asociadas a su cuenta.

# Conclusión

El Módulo 9 proporciona las funcionalidades necesarias para que cada usuario gestione su información personal y adapte la plataforma a sus preferencias. A través de la visualización del perfil, configuración del idioma, personalización visual y gestión de sesiones, FaceLit mejora la experiencia de uso y garantiza una interacción más accesible, segura y personalizada.
