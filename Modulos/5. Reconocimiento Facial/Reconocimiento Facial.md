# Módulo 5: Reconocimiento Facial

## Descripción General

El módulo de Reconocimiento Facial constituye el núcleo funcional de
FaceLit, ya que permite validar la identidad de los usuarios mediante
biometría facial para automatizar procesos de autenticación y control de
asistencia dentro de los ambientes de formación del SENA.

Este módulo se encarga de:

-   Registrar el rostro de usuarios autorizados.
-   Identificar usuarios mediante reconocimiento biométrico.
-   Generar automáticamente eventos relacionados con la asistencia.
-   Sincronizar la información con los demás componentes del sistema.

La funcionalidad se fundamenta en procesos de captura, análisis y
comparación facial para garantizar una validación confiable de
identidad.

## RF-5 Reconocimiento Facial

### Objetivo

Permitir que el sistema capture, procese y utilice información
biométrica facial para reconocer usuarios y ejecutar acciones asociadas
al proceso de asistencia.

## RF-5.1 Registrar rostro del usuario

### Flujo del proceso

1.  El usuario inicia el proceso de registro facial.
2.  El sistema habilita el mecanismo de captura.
3.  Se verifica la presencia de un rostro válido.
4.  Se realiza la captura facial.
5.  Se validan condiciones mínimas de calidad.
6.  Se genera la representación biométrica.
7.  Se confirma el registro.

## RF-5.2 Identificar usuario por reconocimiento facial

### Flujo del proceso

1.  Captura facial en tiempo real.
2.  Procesamiento biométrico.
3.  Comparación con referencia registrada.
4.  Cálculo de coincidencia.
5.  Validación de identidad.

## RF-5.3 Registrar evento y sincronizar información

### Flujo del proceso

1.  Confirmar identidad.
2.  Determinar contexto.
3.  Generar evento.
4.  Sincronizar información.
5.  Actualizar historial.

## Flujo General

Usuario\
↓\
Capturar rostro\
↓\
Validar rostro\
↓\
Generar referencia biométrica\
↓\
Reconocimiento\
↓\
Validar identidad\
↓\
Generar evento\
↓\
Actualizar historial
