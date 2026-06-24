# Guía para el Desarrollo del Front-end

El objetivo es establecer una base técnica para el desarrollo del Front-end del proyecto, garantizando una implementación organizada, modular y alineada con la documentación funcional del sistema.

---

# 1. Diseño basado en el SRS : https://docs.google.com/document/d/1Q9VraDQ4KKaNi_Nba-CACweWYXmk-Xkg/edit?usp=sharing&ouid=105863111727087095874&rtpof=true&sd=true

El desarrollo del Front-end debe realizarse siguiendo la estructura definida en el **Documento de Especificación de Requisitos de Software (SRS)**.

La implementación deberá organizarse por **módulos funcionales (RF)**, respetando la jerarquía de cada requerimiento funcional y sus respectivos submódulos.

Además, cada módulo deberá reflejar claramente el comportamiento de los diferentes roles del sistema:

* Administrador
* Instructor
* Aprendiz

## Módulos Funcionales

| Módulo                          | Enlace |
| ------------------------------- | ------ |
| RF-1 Accesos al Sistema         |   https://github.com/MariaOyola/Modulos_Facelit/blob/main/Modulos/1.%20Acceso%20al%20sistema/1.%20ACCESO%20AL%20SISTEMA.md     |
| RF-2 Gestión de Ambientes       |   https://github.com/MariaOyola/Modulos_Facelit/blob/main/Modulos/2.%20Gestion_Ambientes/Gestion_Ambientes.md                  |
| RF-3 Gestión Académica          |   https://github.com/MariaOyola/Modulos_Facelit/blob/main/Modulos/3.%20Gestion%20acadameca/Gestion_Academica.md                |
| RF-4 Gestión de Horarios        |   https://github.com/MariaOyola/Modulos_Facelit/blob/main/Modulos/4.%20Gestion_Horario/Gestion_Horario.md                      |
| RF-5 Reconocimiento Facial      |                                                                                                                                |
| RF-6 Asistencias y Validaciones |                                                                                                                                |
| RF-7 Reportes y Consultas       |   https://github.com/MariaOyola/Modulos_Facelit/blob/main/Modulos/7.%20Reportes_y_Consultas/Reportes_y_Consultas.md            |
| RF-8 Notificaciones             |   https://github.com/MariaOyola/Modulos_Facelit/blob/main/Modulos/8.%20Notificaciones/Notificaciones.md                        |
| RF-9 Perfil y Personalización   |                                                                                                                                |
|Roles y sus Modulos   |                                                                                                                                |

---

# 2. Revisión del Prototipo

Antes de iniciar el desarrollo, se deberá analizar el prototipo de interfaz para comprender el flujo de navegación, la distribución de pantallas y la interacción entre los diferentes módulos del sistema.

| Documento               | Enlace |
| ----------------------- | ------ |
| Prototipo de Interfaces |   https://www.figma.com/design/fRPJLroPiL9Jeu4zhfy0Zf/FaceID-completo?node-id=0-1&t=mnKzXLzkDCnRh06I-1     |

---

# 3. Definición de la Arquitectura Front-end

Se requiere definir una arquitectura de Front-end que garantice una correcta organización del proyecto.

La estructura deberá contemplar, como mínimo:

* Organización por módulos.
* Componentes reutilizables.
* Pantallas.
* Navegación.
* Reglas de negocio.
* Servicios.
* Gestión de estados.
* Estructura de carpetas.

Como referencia, el proyecto actualmente utiliza una arquitectura híbrida basada en **Módulos + Componentes**.

| Documento              | Enlace |
| ---------------------- | ------ |
| Arquitectura Front-end |   https://github.com/FaceID-Proyect-2026/FaceLit/tree/dev/FaceLit-fixed     |

---

# 4. Buenas Prácticas de Desarrollo

Como complemento al desarrollo del proyecto, se solicita una explicación general sobre cómo se estructura un proyecto Front-end en un entorno empresarial, incluyendo buenas prácticas de arquitectura, organización del código y escalabilidad.


# 5. Modelo de Datos (MER)

Para comprender la información que será consumida por el Front-end, se utilizará como referencia el **Modelo Entidad-Relación (MER)** del proyecto.

Este servirá para identificar:

* Entidades.
* Relaciones.
* Atributos.
* Dependencias entre módulos.

| Documento                     | Enlace |
| ----------------------------- | ------ |
| Modelo Entidad-Relación (MER) |    https://drive.google.com/file/d/1T2iSlNocXG083eY-0qtmCVjRdjQTmZ_b/view?usp=sharing    |

---

## Objetivo

Contar con una guía técnica que permita desarrollar un Front-end organizado, modular y alineado con la arquitectura del proyecto, el SRS y el modelo de datos, facilitando la construcción de un prototipo funcional y escalable.
