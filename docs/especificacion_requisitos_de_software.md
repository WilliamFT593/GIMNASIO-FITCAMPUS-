# Especificación de Requisitos de Software (SRS)
### Proyecto: 🏋️ CASO DE ESTUDIO: SISTEMA DE GESTIÓN PARA GIMNASIO UNIVERSITARIO "FITCAMPUS"
*Versión [1.0]*

<br>

<img width="445" height="127" alt="image" src="https://github.com/user-attachments/assets/a2cb6e38-e0cb-4149-b56f-a295d28b4a78" />

*Octubre/2025*

<br>

> **Nota Aclaratoria:** <br>
> Este documento fue elaborado con fines académicos como parte de una práctica formativa bajo el estándar IEEE 830-1998.
> Todos los datos, nombres de entidades, diagramas y estructuras de base de datos son simulados y no corresponden a información real.
> Este documento tiene propósitos educativos y está diseñado para enseñar la correcta especificación de requisitos de software.

<br>

> **Instrucciones para el Estudiante:** <br>
> - Elimine todos los comentarios HTML `<!-- ... -->` en la versión final
> - Reemplace todo el texto entre `[corchetes]` con información real de su proyecto
> - Utilice las tablas y formatos sugeridos como guía
> - Revise el checklist de calidad antes de entregar
> - Mantenga la numeración y estructura del estándar IEEE 830

<br>

**Control de Versiones:**

| Versión | Fecha | Autor | Descripción de Cambios |
|---------|-------|-------|------------------------|
| 1.0 | [DD/MM/AAAA] | [Nombre] | Versión inicial del documento |
| | | | |

<br>

---

## CONTENIDO

- [1 INTRODUCCIÓN](#1-introducción)
  - [1.1 Propósito](#11-propósito)
  - [1.2 Alcance](#12-alcance)
  - [1.3 Personal involucrado](#13-personal-involucrado)
  - [1.4 Definiciones, acrónimos y abreviaturas](#14-definiciones-acrónimos-y-abreviaturas)
  - [1.5 Referencias](#15-referencias)
  - [1.6 Resumen](#16-resumen)
- [2 DESCRIPCIÓN GENERAL](#2-descripción-general)
  - [2.1 Perspectiva del producto](#21-perspectiva-del-producto)
  - [2.2 Funciones del producto](#22-funciones-del-producto)
  - [2.3 Características de los usuarios](#23-características-de-los-usuarios)
  - [2.4 Restricciones](#24-restricciones)
  - [2.5 Suposiciones y dependencias](#25-suposiciones-y-dependencias)
  - [2.6 Requisitos futuros](#26-requisitos-futuros)
- [3 REQUISITOS ESPECÍFICOS](#3-requisitos-específicos)
  - [3.1 Requisitos funcionales](#31-requisitos-funcionales)
  - [3.2 Requisitos de interfaz externa](#32-requisitos-de-interfaz-externa)
    - [3.2.1 Interfaz de usuario](#321-interfaz-de-usuario)
    - [3.2.2 Interfaz de hardware](#322-interfaz-de-hardware)
    - [3.2.3 Interfaz de software](#323-interfaz-de-software)
    - [3.2.4 Interfaz de comunicación](#324-interfaz-de-comunicación)
  - [3.3 Requisitos no funcionales](#33-requisitos-no-funcionales)
    - [3.3.1 Rendimiento](#331-rendimiento)
    - [3.3.2 Fiabilidad](#332-fiabilidad)
    - [3.3.3 Disponibilidad](#333-disponibilidad)
    - [3.3.4 Seguridad](#334-seguridad)
    - [3.3.5 Mantenibilidad](#335-mantenibilidad)
    - [3.3.6 Portabilidad](#336-portabilidad)
  - [3.4 Requisitos de diseño](#34-requisitos-de-diseño)
  - [3.5 Requisitos de calidad](#35-requisitos-de-calidad)
  - [3.6 Restricciones del sistema](#36-restricciones-del-sistema)
  - [3.7 Atributos del sistema](#37-atributos-del-sistema)
- [4 APÉNDICES](#4-apéndices)
  - [4.1 Modelos de casos de uso](#41-modelos-de-casos-de-uso)
  - [4.2 Glosario](#42-glosario)
  - [4.3 Diagramas del sistema](#43-diagramas-del-sistema)
  - [4.4 Matriz de trazabilidad](#44-matriz-de-trazabilidad)
  - [4.5 Criterios de evaluación](#45-criterios-de-evaluación)

<br>

---

# 1. INTRODUCCIÓN

## 1.1 Propósito

El propósito de este documento es definir de manera clara, completa y verificable los requisitos del Sistema de Gestión para el Gimnasio Universitario “FitCampus”,

Este documento describe qué debe hacer el sistema, cómo debe comportarse, quiénes lo utilizarán y cuáles son los objetivos funcionales y estratégicos que debe cumplirCon falcance, las funcionalidades y las restricciones del proyecto.

La siguiente tabla resume cómo cada actor utilizará este documento:

| **Actor** | **Uso del Documento** |
|------------|----------------------|
| Desarrolladores | mplementan las funcionalidades definidas, asegurando que el sistema cumpla con los requisitos funcionales y no funcionales. |
| Analistas | Validan que los requisitos respondan efectivamente a los problemas actuales del gimnasio y a las necesidades del cliente. |
| Cliente (Dirección de Bienestar y Deportes) | Verifica que el sistema FitCampus solucione los problemas críticos: control de aforo, accesos, mantenimiento, reportes, fila virtual, valorización física y experiencia del usuario. |
| Equipo QA | Diseño |

---

## 1.2 Alcance

El sistema FitCampus gestionará de forma integral el aforo en tiempo real del gimnasio universitario. Para lograrlo, registrará automáticamente la entrada y salida de los usuarios por medio de sensores instalados en los torniquetes de acceso, el cual actualiza de inmediato el conteo de personas dentro del gimnasio.

Además del control de aforo, el sistema permitirá:

Administrador: supervisa el estado del gimnasio, gestiona membresías, consulta reportes, y configura límites de aforo.

Sistema Automático: procesa los eventos de entrada/salida, actualiza el conteo de aforo y genera alertas.

Usuario General: consulta su membresía, verifica el aforo en tiempo real y accede a la fila virtual cuando el gimnasio está lleno.

### Objetivos principales
| **Objetivo** | **Descripción** |
|---------------|-----------------|
| Control de Aforo | Evitar sobreocupación del gimnasio y garantizar seguridad. |
| Automatización |Eliminar procesos manuales de registro y reducir errores por ingreso humano. |
| Gestión de Membresías | Llevar control automático de usuarios activos, vencidos y bloqueados. |
| Monitoreo en Tiempo Real | Proveer información instantánea sobre aforo, estado del acceso y alertas. |
| Fila Virtual Inteligente | Permitir que los usuarios esperen su turno sin aglomeraciones físicas en la entrada. |

---

## 1.3 Definiciones, Acrónimos y Abreviaturas

| **Término / Acrónimo** | **Definición** |
|--------------------------|----------------|
| **SRS** | Software Requirements Specification (Documento de Requisitos de Software). |
| **RF** | Requisito Funcional. |
| **RNF** | Requisito No Funcional. |
| **JWT** | JSON Web Token, usado para autenticación segura. |
| **HTTPS** | Protocolo de comunicación segura entre el cliente y el servidor. |
| **FitControl** | Nombre del sistema de control de aforo del gimnasio. |

---

## 1.4 Referencias

| **Referencia** | **Descripción / Fuente** |
|-----------------|--------------------------|
| IEEE Std 830-1998 | *IEEE Recommended Practice for Software Requirements Specifications*. |
| Universidad Nacional del Valle | Requerimientos funcionales definidos por el gimnasio universitario. |
| Documento de Requisitos del Cliente | Base para la especificación funcional. |
| Diagrama de Casos de Uso – FitControl | Diseño visual de las interacciones del sistema. |

---

## 1.5 Visión General del Documento

Este documento está dividido en secciones que describen los diferentes aspectos del sistema:

| **Sección** | **Contenido** |
|--------------|----------------|
| **1. Introducción** | Propósito, alcance y términos clave del sistema. |
| **2. Descripción General** |Contexto del gimnasio, usuarios involucrados, funciones globales y restricciones. |
| **3. Requisitos Específicos** | Requisitos funcionales y no funcionales del sistema. |
| **4. Casos de Uso** | Descripciones formales de las interacciones entre actores y el sistema. |

El propósito de esta estructura es mantener la documentación organizada, comprensible y fácil de actualizar conforme evolucione el proyecto.


<br>

---


---

## 2.1 perspectiva del producto

Contexto del Sistema FitCampus
El Sistema FitCampus es una solución de software integral diseñada para transformar la gestión operativa del Gimnasio Universitario de la UDS. Se conceptualiza como un ecosistema digital centralizador que reemplaza los procesos manuales actuales basados en papel, proporcionando automatización, control en tiempo real y análisis de datos para toda la operación del gimnasio.

┌─────────────────────────────────────────────────────────────────┐
│                    SISTEMA FITCAMPUS                            │
│                                                                 │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │   MÓDULO    │  │   MÓDULO    │  │   MÓDULO    │             │
│  │ CONTROL DE  │  │  GESTIÓN DE │  │   REPORTE   │             │
│  │   ACCESO    │  │   CLASES    │  │ MANTENIMIENT│             │
│  │             │  │             │  │             │             │
│  └─────────────┘  └─────────────┘  └─────────────┘             │
│          │               │               │                     │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │   MÓDULO    │  │   MÓDULO    │  │   MÓDULO    │             │
│  │ VALORACIÓN  │  │  RESERVA    │  │  DASHBOARD  │             │
│  │   FÍSICA    │  │  CANCHAS    │  │ ANALÍTICO   │             │
│  │             │  │             │  │             │             │
│  └─────────────┘  └─────────────┘  └─────────────┘             │
└─────────────────┬─────────────────┬─────────────────────────────┘
                  │                 │
                  │                 │
┌─────────────────▼─────────────────▼─────────────────────────────┐
│                      INTERFACES EXTERNAS                        │
│                                                                 │
│ ┌────────────┐  ┌────────────┐  ┌────────────┐  ┌────────────┐ │
│ │ TORNIQUETES│  │  TABLETS   │  │  BÁSCULA   │  │ SISTEMA    │ │
│ │   ACCESO   │  │RECEPCIÓN & │  │  DIGITAL   │  │UNIVERSITARIO│ │
│ │ (RFID/QR)  │  │INSTRUCTORES│  │ (BLUETOOTH)│  │(CARNÉS)    │ │
│ └────────────┘  └────────────┘  └────────────┘  └────────────┘ │
│                                                                 │
│ ┌────────────┐  ┌────────────┐  ┌────────────┐  ┌────────────┐ │
│ │  APLICACIÓN│  │   PORTAL   │  │  SISTEMA   │  │  CORREO    │ │
│ │   MÓVIL    │  │   WEB      │  │  MENSAJERÍA│  │ELECTRÓNICO │ │
│ │ (USUARIOS) │  │(ADMIN)     │  │ (SMS/PUSH) │  │            │ │
│ └────────────┘  └────────────┘  └────────────┘  └────────────┘ │
└─────────────────────────────────────────────────────────────────┘

## 2.2 Funciones del Producto

Las funciones principales del sistema están organizadas en los siguientes grupos:

| **Módulo** | **Función Principal** | **Descripción Breve** |
|-------------|----------------------|------------------------|
| Control de Aforo | Monitoreo en tiempo real | Muestra el número de personas dentro del gimnasio y actualiza los datos automáticamente. |
| Registro de Accesos | Entrada y salida de usuarios | Registra cuándo entra y sale cada usuario mediante el sistema automático. |
| Notificaciones | Aforo máximo alcanzado | Envía alertas cuando se llega al límite establecido de personas. |
| Bloqueo de Acceso | Prevención de ingreso | Impide que nuevos usuarios entren si el gimnasio está lleno. |
| Fila Virtual | Espera de usuarios | Gestiona el orden de ingreso cuando el aforo está completo. |
| Membresías | Administración de usuarios | Permite al administrador registrar, actualizar y renovar membresías. |

---

## 2.3 Características de los Usuarios

| **Característica** | **Usuario Tipo 1: Administrador** | **Usuario Tipo 2: Sistema Automático** | **Usuario Tipo 3: Usuario General** |
|----------------------|----------------------------------|----------------------------------------|------------------------------------|
| **Descripción** | Personal encargado de la supervisión del gimnasio. | Módulo automatizado encargado de detectar y registrar accesos. | Personas que utilizan las instalaciones del gimnasio. |
| **Responsabilidades** | Gestionar aforo, membresías y alertas. | Registrar entradas/salidas y mantener el conteo. | Acceder al gimnasio, consultar membresías. |
| **Nivel Técnico** | Medio | Alto | Bajo |
| **Experiencia en el Dominio** | Intermedio | Experto | Novato |
| **Frecuencia de Uso** | Diaria | Continua | Diaria |
| **Funciones Principales** | Ver reportes, actualizar membresías, recibir alertas. | Enviar datos al sistema, actualizar aforo. | Entrar, salir y ver su estado de membresía. |
| **Necesidades Especiales** | Panel de control claro y rápido. | Conexión constante a la red. | Interfaz sencilla y accesible desde móvil. |

---

## 2.4 Restricciones

| **Tipo de Restricción** | **Descripción** |
|--------------------------|-----------------|
| Técnica | El sistema requiere conexión a Internet y servidor disponible las 24 horas. |
| Seguridad | Todas las contraseñas deben almacenarse cifradas (bcrypt o SHA-256). |
| Integración | Debe conectarse con sensores automáticos de acceso. |
| Legal | Cumplimiento con las normas de protección de datos personales. |
| Comunicación | Uso obligatorio del protocolo HTTPS para transmisión segura. |

---

## 2.5 Suposiciones y Dependencias

| **Suposición / Dependencia** | **Descripción** |
|-------------------------------|-----------------|
| Infraestructura | El gimnasio cuenta con red Wi-Fi estable y sensores instalados. |
| Base de Datos | Se usará un motor relacional (MySQL o PostgreSQL). |
| Autenticación | El sistema depende del módulo de inicio de sesión (RF-001). |
| Hardware | Los sensores deben enviar información precisa al servidor. |
| Personal | El administrador debe estar capacitado para usar el sistema. |

---

## 2.6 Requisitos Futuros

| **Código** | **Requisito Futuro** | **Descripción** |
|-------------|----------------------|-----------------|
| RF-F01 | Sistema de pagos en línea | Permitir renovar membresías mediante pagos digitales. |
| RF-F02 | Aplicación móvil | Crear una app para ver el aforo y estado de membresía en tiempo real. |
| RF-F03 | Reportes estadísticos | Generar informes automáticos del uso del gimnasio. |
| RF-F04 | Notificaciones push | Enviar alertas al celular del usuario cuando haya cupo disponible. |

<br>

---

## 3 REQUISITOS ESPECÍFICOS

# 3. REQUISITOS FUNCIONALES

## 3.1 Requisitos Funcionales

## 3.1.1 Módulo de Gestión de Membresías

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-001 |
| **Nombre** | Administración de membresías |
| **Descripción** | El sistema debe permitir al administrador registrar, actualizar, suspender o eliminar las membresías de los usuarios, manteniendo un historial de sus estados y fechas de renovación. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento del área administrativa del gimnasio |
| **Criterios de aceptación** | 1. El administrador puede crear, editar y eliminar membresías.<br>2. Se registran fechas de inicio y vencimiento.<br>3. El sistema genera alertas de vencimiento próximas.<br>4. Los cambios se reflejan en tiempo real en la base de datos. |
| **Dependencias** | RF-005 (Control de aforo), RF-006 (Registro de accesos) |
| **Comentarios** | Las membresías vencidas deben impedir el acceso al gimnasio automáticamente. |

---

## 3.1.2 Módulo de Autenticación y Control de Acceso

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-002 |
| **Nombre** | Inicio de sesión y autenticación segura |
| **Descripción** | El sistema debe permitir el acceso mediante credenciales únicas (usuario y contraseña) y usar autenticación JWT para sesiones seguras. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento de seguridad del sistema |
| **Criterios de aceptación** | 1. Login con usuario/contraseña.<br>2. Emisión y validación de tokens JWT.<br>3. Manejo seguro de contraseñas (hashing). |
| **Dependencias** | — |
| **Comentarios** | Soporta autenticación de usuarios y administración de sesiones. |

---

## 3.1.3 Módulo de Notificaciones y Alertas

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-003 |
| **Nombre** | Envío de notificaciones automáticas |
| **Descripción** | El sistema debe enviar notificaciones automáticas al administrador y a los usuarios cuando se produzcan eventos importantes, como aforo máximo, membresía vencida o turno disponible. |
| **Prioridad** | Media |
| **Estabilidad** | Media |
| **Fuente** | Requerimiento de experiencia de usuario |
| **Criterios de aceptación** | 1. El sistema envía notificaciones por correo o dentro de la app.<br>2. Se generan alertas al alcanzar el límite de aforo.<br>3. Se notifica al usuario 3 días antes del vencimiento de su membresía. |
| **Dependencias** | RF-001, RF-005 |
| **Comentarios** | En una versión futura se integrarán notificaciones push móviles. |

---

## 3.1.4 Módulo de Reportes y Estadísticas

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-004 |
| **Nombre** | Generación de reportes de uso |
| **Descripción** | El sistema debe permitir al administrador generar reportes sobre el uso del gimnasio, incluyendo aforo diario, membresías activas, ingresos y salidas. |
| **Prioridad** | Media |
| **Estabilidad** | Alta |
| **Fuente** | Solicitud del área de administración |
| **Criterios de aceptación** | 1. El sistema genera reportes filtrados por fecha o tipo de usuario.<br>2. Los reportes pueden exportarse a PDF o Excel.<br>3. La información se obtiene de los registros en la base de datos. |
| **Dependencias** | RF-001, RF-005, RF-006 |
| **Comentarios** | Los reportes deben incluir métricas de uso y asistencia. |

---

## 3.1.5 Módulo de Control de Aforo

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-005 |
| **Nombre** | Control de aforo en tiempo real |
| **Descripción** | El sistema debe monitorear automáticamente el número de usuarios dentro del gimnasio, actualizando el aforo en tiempo real y bloqueando el acceso al alcanzar el límite. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento funcional derivado del sistema automático FitCampus |
| **Criterios de aceptación** | 1. El sistema registra entrada y salida de usuarios.<br>2. Actualiza aforo en tiempo real.<br>3. Bloquea accesos al alcanzar el límite.<br>4. Notifica al administrador.<br>5. Gestiona una fila virtual. |
| **Dependencias** | RF-006 |
| **Comentarios** | Se integra con sensores del gimnasio. |

---

## 3.1.6 Módulo de Registro de Entradas y Salidas

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-006 |
| **Nombre** | Registro automático de entradas y salidas |
| **Descripción** | Registra la entrada y salida de cada usuario mediante sensores o lectores de identificación. |
| **Prioridad** | Alta |
| **Estabilidad** | Media |
| **Fuente** | Área de control y acceso del gimnasio |
| **Criterios de aceptación** | 1. Registra entrada.<br>2. Registra salida.<br>3. Actualiza aforo.<br>4. Guarda datos en BD.<br>5. Garantiza integridad. |
| **Dependencias** | RF-005 |
| **Comentarios** | Sirve para estadísticas y reportes. |

---

## 3.1.7 Módulo de Gestión de Rutinas Personalizadas

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-007 |
| **Nombre** | Gestión de rutinas personalizadas |
| **Descripción** | Permite a los entrenadores crear, asignar y modificar rutinas según objetivos del usuario. |
| **Prioridad** | Alta |
| **Estabilidad** | Media |
| **Fuente** | Área de entrenamiento y bienestar |
| **Criterios de aceptación** | 1. Crear rutina.<br>2. Usuario visualiza rutina.<br>3. Modificar o eliminar.<br>4. Guardar en BD. |
| **Dependencias** | RF-012 |
| **Comentarios** | Mejora la personalización del entrenamiento. |

---

## 3.1.8 Módulo de Control de Asistencia Automatizado

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-008 |
| **Nombre** | Control de asistencia automatizado |
| **Descripción** | El sistema registra asistencia mediante código QR o biometría. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Gestión administrativa |
| **Criterios de aceptación** | 1. Registrar con QR/huella.<br>2. Registrar hora/fecha.<br>3. Historial de asistencias.<br>4. Actualización en tiempo real. |
| **Dependencias** | RF-006 |
| **Comentarios** | Facilita control de aforo y estadísticas. |

---

## 3.1.9 Módulo de Gestión de Fila Virtual

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-009 |
| **Nombre** | Gestión de fila virtual |
| **Descripción** | Crea una fila virtual cuando el aforo está completo y notifica turnos. |
| **Prioridad** | Alta |
| **Estabilidad** | Media |
| **Fuente** | Sistema automático de aforo |
| **Criterios de aceptación** | 1. Crea fila.<br>2. Usuario ve posición.<br>3. Notificaciones automáticas.<br>4. Actualización en tiempo real. |
| **Dependencias** | RF-005, RF-008 |
| **Comentarios** | Reduce aglomeraciones. |

---

## 3.1.10 Módulo de Gestión de Reservas de Equipos

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-010 |
| **Nombre** | Reservas de máquinas y áreas |
| **Descripción** | Permite reservar máquinas, equipos o zonas con horarios específicos. |
| **Prioridad** | Media |
| **Estabilidad** | Media |
| **Fuente** | Solicitud de usuarios y administración |
| **Criterios de aceptación** | 1. Selección de equipo.<br>2. Ver disponibilidad.<br>3. Registrar reserva.<br>4. Evitar duplicación. |
| **Dependencias** | RF-012, RF-003 |
| **Comentarios** | Mejora gestión del espacio. |

---

## 3.1.11 Módulo de Reportes de Aforo y Asistencia

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-011 |
| **Nombre** | Reportes de aforo y asistencia |
| **Descripción** | Genera reportes diarios, semanales y mensuales exportables. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento institucional |
| **Criterios de aceptación** | 1. Filtrar por fecha.<br>2. Incluir métricas.<br>3. Descargar PDF/Excel.<br>4. Información precisa. |
| **Dependencias** | RF-006, RF-008 |
| **Comentarios** | Apoya toma de decisiones. |

---

## 3.1.12 Módulo de Gestión de Perfil del Usuario

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-012 |
| **Nombre** | Gestión del perfil del usuario |
| **Descripción** | Permite actualizar datos personales, objetivos y preferencias. |
| **Prioridad** | Media |
| **Estabilidad** | Alta |
| **Fuente** | Bienestar estudiantil |
| **Criterios de aceptación** | 1. Actualizar datos.<br>2. Validación.<br>3. Guardado correcto.<br>4. Entrenadores pueden consultar. |
| **Dependencias** | RF-002 |
| **Comentarios** | Mejora personalización del servicio. |

---

## 3.1.13 Módulo de Inventario de Equipos

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-013 |
| **Nombre** | Gestión de inventario |
| **Descripción** | Registra, actualiza y consulta el inventario de máquinas, equipos y accesorios del gimnasio. |
| **Prioridad** | Media |
| **Estabilidad** | Media |
| **Fuente** | Administración y mantenimiento |
| **Criterios de aceptación** | 1. Registro de equipos.<br>2. Actualización de estado.<br>3. Consulta por categoría.<br>4. Almacenamiento correcto. |
| **Dependencias** | RF-011 (Reservas) |
| **Comentarios** | Control del estado físico del gimnasio. |

---

## 3.1.14 Módulo de Mantenimiento Preventivo

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-014 |
| **Nombre** | Mantenimiento preventivo |
| **Descripción** | Programa y registra mantenimientos preventivos, generando alertas previas a la fecha de intervención. |
| **Prioridad** | Media |
| **Estabilidad** | Media |
| **Fuente** | Área de mantenimiento |
| **Criterios de aceptación** | 1. Programación por equipo.<br>2. Alertas previas.<br>3. Historial de mantenimientos.<br>4. Registro en base de datos. |
| **Dependencias** | RF-014 |
| **Comentarios** | Aumenta la vida útil de los equipos. |

---

## 3.1.15 Módulo de Roles y Permisos

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-015 |
| **Nombre** | Gestión de roles |
| **Descripción** | Permite crear roles personalizados y asignar permisos específicos a cada tipo de usuario. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Política institucional |
| **Criterios de aceptación** | 1. Creación de roles.<br>2. Asignación de permisos.<br>3. Acceso restringido según rol.<br>4. Actualización en tiempo real. |
| **Dependencias** | RF-002 |
| **Comentarios** | Mejora la seguridad general del sistema. |

---

## 3.1.16 Módulo de Pagos en Línea

| Campo | Descripción |
|-------|-------------|
| **ID** | RF-016 |
| **Nombre** | Pagos en línea |
| **Descripción** | Permite realizar pagos online para membresías, reservas o servicios adicionales mediante pasarelas seguras. |
| **Prioridad** | Alta |
| **Estabilidad** | Media |
| **Fuente** | Área financiera |
| **Criterios de aceptación** | 1. Pago con tarjeta o billetera digital.<br>2. Confirmación en tiempo real.<br>3. Comprobante automático.<br>4. Actualización de servicios tras el pago. |
| **Dependencias** | RF-001 (Membresías), RF-009 (Notificaciones) |
| **Comentarios** | Facilita la autogestión del usuario. |


# 4. CASOS DE USO

## 4.1 Caso de Uso: Controlar Aforo en Tiempo Real

### Identificación
| Campo | Descripción |
|--------|--------------|
| **ID** | UC-01 |
| **Nombre** | Controlar aforo en tiempo real |
| **Actor principal** | Sistema Automático |
| **Actores secundarios** | Administrador, Usuarios |
| **Tipo** | Primario |
| **Prioridad** | Alta |

---

### Descripción
Este caso de uso describe el proceso mediante el cual el sistema FitCampus controla de forma automática el número de personas dentro del gimnasio. Cada vez que un usuario entra o sale, el sistema actualiza el contador de aforo. Si se alcanza el límite máximo, el sistema notifica al administrador, bloquea temporalmente nuevos ingresos y permite gestionar una fila virtual.

---

### Flujo principal
1. El sistema detecta el ingreso de un usuario mediante su identificación.  
2. Registra la entrada en el sistema (*UC-2*).  
3. Actualiza el contador de aforo actual.  
4. Si el aforo se encuentra dentro del límite, mantiene el acceso habilitado.  
5. El sistema detecta cuando un usuario sale y actualiza el registro (*UC-3*).  
6. Si el límite de capacidad se alcanza, se ejecuta *UC-4 (Notificar aforo máximo)*.  
7. En caso de que el aforo esté completo, se activa *UC-5 (Bloquear acceso por aforo completo)*.  
8. Si hay usuarios en espera, el sistema activa *UC-6 (Gestionar fila virtual)*.

---

### Flujo alternativo
- Si los sensores no detectan correctamente una entrada o salida, el sistema genera un registro de evento de error para revisión manual.  

---

### Postcondición
El sistema mantiene actualizado el número de personas dentro del gimnasio y garantiza que el aforo nunca supere el máximo permitido.

---

### Relaciones con otros casos de uso
| Caso relacionado | Relación | Descripción |
|------------------|-----------|--------------|
| **UC-2** | <<extends>> | Registrar entrada de cada usuario. |
| **UC-3** | <<extends>> | Registrar salida de cada usuario. |
| **UC-4** | <<includes>> | Notificar aforo máximo alcanzado. |
| **UC-5** | <<extends>> | Bloquear acceso por aforo completo. |
| **UC-6** | <<extends>> | Gestionar fila virtual de espera. |

---

### Diagrama del Caso de Uso



usecase
    actor "Sistema Automático" as SA
    rectangle "Sistema FitCampus" {
        (UC-01: Controlar aforo en tiempo real)
        (UC-2: Registrar entrada de usuario)
        (UC-3: Registrar salida de usuario)
        (UC-4: Notificar aforo máximo)
        (UC-5: Bloquear acceso por aforo completo)
        (UC-6: Gestionar fila virtual)
    }

    SA --> (UC-01: Controlar aforo en tiempo real)
    (UC-01: Controlar aforo en tiempo real) --> (UC-2: Registrar entrada de usuario) : <<extends>>
    (UC-01: Controlar aforo en tiempo real) --> (UC-3: Registrar salida de usuario) : <<extends>>
    (UC-01: Controlar aforo en tiempo real) --> (UC-4: Notificar aforo máximo) : <<includes>>
    (UC-01: Controlar aforo en tiempo real) --> (UC-5: Bloquear acceso por aforo completo) : <<extends>>
    (UC-01: Controlar aforo en tiempo real) --> (UC-6: Gestionar fila virtual) : <<extends>>

-->


---


## Caso de Uso: Gestionar Membresias de Usuario

### Identificación
| Campo | Descripción |
|--------|--------------|
| **ID** | UC-07 |
| **Nombre** | Gestionar Membresias de Usuario |
| **Actor principal** | Administrador |
| **Actores secundarios** | Sistema automatico |
| **Tipo** | Secundario/De Soporte |
| **Prioridad** | Alta |

---

### Descripción
Este caso de uso describe el proceso mediante el cual el Administrador (o personal autorizado) puede realizar las operaciones de mantenimiento esenciales sobre las membresías de los usuarios. Esto incluye crear nuevas membresías, modificar planes existentes, extender la fecha de caducidad, suspender o reactivar cuentas y registrar pagos.

---

### Flujo principal
1. El Administrador inicia sesión en el portal de gestión del sistema FitCampus.
2. El Administrador selecciona la opción "Gestionar Membresías" y busca al usuario por nombre, ID o correo electrónico.
3. El Sistema muestra el perfil del usuario y el estado actual de su membresía (plan, fecha de inicio/fin, estado de pago).
4. El Administrador selecciona la acción deseada (Crear/Renovar/Modificar/Suspender/Registrar Pago).
5. El Administrador ingresa los datos necesarios para la acción:
 -Crear/Renovar: Selecciona el plan (Ej: Básico, Premium), duración y registra el pago (si aplica).
 -Modificar: Cambia el tipo de plan (Ej: de Básico a Premium).
 -Suspender/Reactivar: Cambia el estado de la membresía.
6. El Sistema valida los datos ingresados ​​y realiza la actualización en la base de datos.
7. El Sistema confirma al Administrador que la gestión ha sido completada exitosamente.
8. El Sistema automático (opcionalmente) envía una notificación al usuario sobre el cambio en su membresía.

---

### Flujo alternativo
FA-1: Pago Rechazado o Pendiente :
Si el Administrador intenta renovar la membresía y no se registra un pago exitoso, el sistema bloquea la activación de la nueva fecha de fin y notifica al Administrador. La membresía puede quedar en estado "Pendiente de Pago" .

FA-2: Intento de Uso de Membresía Vencida :
Si el sistema detecta una solicitud de ingreso (UC-2) o de reserva (UC-08) con una membresía cuya fecha de fin ya pasó, el sistema notifica automáticamente al usuario y al Administrador que se requiere una renovación (relación con UC-2 y UC-08). 

---

### Postcondición
La información de la membresía del usuario se encuentra actualizada en el sistema (plan, fecha de caducidad, estado activo/suspendido), lo cual afecta directamente su acceso al gimnasio y los servicios (clases, etc.).

---

### Relaciones con otros casos de uso
| Caso relacionado | Relación | Descripción |
|------------------|-----------|--------------|
| **UC-2** | <<depends>> | El registro de entrada debe validar el estado activo de la membresía antes de permitir el ingreso. |
| **UC-8** | <<depends>> | La reserva de clases debe validar el estado y tipo de membresía para permitir el acceso a la clase. |
| **UC-10** | <<extends>> | Puede ser necesario modificar la membresía si el usuario requiere acceso a horarios específicos de máquinas o zonas. |


##  Caso de Uso: Reservar Clases Grupales

### Identificación
| Campo | Descripción |
|--------|--------------|
| **ID** | UC-08 |
| **Nombre** | Reservar Clases Grupales |
| **Actor principal** | Usuario |
| **Actores secundarios** | Sistema Automatico, Administrador(gestor de clases ) |
| **Tipo** | Primario |
| **Prioridad** | Alta |

---

### Descripción
Este caso de uso describe el proceso mediante el cual un usuario del gimnasio FitCampus puede consultar el horario de clases grupales, verificar su disponibilidad (cupo) y asegurar su plaza mediante una reserva. El sistema debe gestionar el límite de cupo y, si es necesario, una lista de espera.

---

### Flujo principal
1. El Usuario inicia sesión en la aplicación o portal web de FitCampus.
2. El Usuario selecciona la opción para Consultar Horario de Clases .
3. El Sistema verifica la membresía del usuario (UC-07) para asegurar que esté activa y con acceso a la clase deseada.
4. El Sistema muestra el listado de clases disponibles, indicando el Cupo Actual/Máximo y el horario.
5. El Usuario selecciona la clase que desea reservar.
6. El Sistema realiza una verificación final del cupo disponible.
7. Si hay cupo, el sistema registra la reserva del usuario para esa clase y reduce el cupo disponible en uno.
8. El Sistema notifica al usuario la confirmación de la reserva (correo, notificación).
9. La reserva se registra como una Entrada Pendiente que se validará automáticamente al ingresar al gimnasio a la hora de la clase (relación con UC-2).

---

### Flujo alternativo
FA-1: Clase sin Cupo (Lista de Espera) :
Si el sistema detecta que el cupo está en su límite máximo, pregunte al usuario si desea inscribirse en la lista de espera .
Si el usuario acepta, el sistema lo agrega a la fila virtual (relación con UC-6).
Si otro usuario cancela su reserva, el sistema asigna automáticamente la plaza al primer usuario en la lista de espera y ejecuta el Director de Flujo desde el paso 7.

FA-2: Membresía Inválida :
Si la verificación en el paso 3 indica que la membresía está caducada o no incluye acceso a clases, el sistema bloquea la reserva y notifica al usuario la razón.

---

### Postcondición
El usuario tiene una plaza reservada y confirmada para la clase grupal seleccionada, o ha sido agregado a la lista de espera correspondiente. El cupo disponible para la clase se mantiene actualizado en tiempo real.

---

### Relaciones con otros casos de uso
| Caso relacionado | Relación | Descripción |
|------------------|-----------|--------------|
| **UC-07** | <<depends>> | El sistema depende de la gestión de membresías para validar el acceso a la reserva. |
| **UC-06** | <<extends>> | Se utiliza la lógica de gestión de fila virtual para la lista de espera de las clases. |
| **UC-2** | <<depends>> | La reserva es un requisito para que el UC-2 (Registrar entrada) valide el ingreso del usuario a la zona de clases a la hora reservada. |

---

## Caso de Uso: Generar Reportes 

### Identificación
| Campo | Descripción |
|--------|--------------|
| **ID** | UC-09 |
| **Nombre** | Generar Reportes de Uso y Aforo |
| **Actor principal** | Administrador |
| **Actores secundarios** | Sistema automatico |
| **Tipo** | De soporte/Secundario |
| **Prioridad** | Medios de comunicacion |

---

### Descripción
Este caso de uso describe cómo el sistema FitCampus procesa los datos históricos recopilados de los ingresos (UC-2), salidas (UC-3) y el control de aforo (UC-1) para generar informes analíticos. Estos informes son esenciales para que el Administrador pueda identificar patrones de máxima concurrencia, horas valle, y la asistencia a clases, lo cual es crucial para la optimización de recursos y la toma de decisiones operativas.

---

### Flujo principal
1. El Administrador inicia sesión en el portal de gestión.
2. El Administrador selecciona la opción "Generar Informes" .
3. El Administrador especifica los parámetros del reporte (rango de fechas, tipo de reporte —ej: Aforo, Asistencia a Clases, Movimiento de Membresías—, y formato de salida —ej: PDF, CSV—).
4. El Sistema accede a los registros históricos (UC-1, UC-2, UC-3, UC-8).
5. El Sistema automático procesa los datos para calcular las métricas clave (ej: aforo promedio por hora, pico de afluencia, tasa de ocupación de clases).
6. El Sistema genera el informe en el formato solicitado, incluyendo gráficos y tablas.
7. El Sistema presenta el informe en pantalla o lo envía al correo electrónico del Administrador.

---

### Flujo alternativo
FA-1: Datos Insuficientes :
Si el Administrador selecciona un rango de fechas para el cual no existen registros completos (ej: el sistema no estaba operativo), el sistema emite una advertencia e informa que el reporte se generará solo con los datos disponibles, o solicitar un nuevo rango.

FA-2: Informe de Generación Lenta :
Si el rango de datos es muy extenso (ej: un año completo), el sistema notifica al Administrador que el reporte se generará en el segundo plano y le enviará una notificación o correo cuando esté listo para su descarga.

---

### Postcondición
El Administrador tiene en su poder un informe analítico que refleja el uso y el aforo del gimnasio durante el período especificado, lo cual le permite tomar decisiones informadas sobre horarios y recursos.

---

### Relaciones con otros casos de uso
| Caso relacionado | Relación | Descripción |
|------------------|-----------|--------------|
| **UC-1** | <<depends>> | Utilice los registros de aforo en tiempo real para generar informes históricos de concurrencia. |
| **UC-2** | <<depends>> | Utilice los registros de entrada y salida para calcular la afluencia total y los picos de uso por hora. |
| **UC-3** | <<depends>> | Utilice los registros de entrada y salida para calcular la afluencia total y los picos de uso por hora. |
| **UC-8** | <<depends>> | Utiliza los datos de reservas para reportar la tasa de ocupación y la popularidad de las clases grupales. |
| **UC-7** | <<depends>> | Puede generar informes de nuevas altas, bajas y renovaciones de membresías. |

---

## Caso de Uso: Sincronizar Horario de Disponibilidad de Maquinas

### Identificación
| Campo | Descripción |
|--------|--------------|
| **ID** | UC-10 |
| **Nombre** | Sincronizar Horario de Disponibilidad de Maquinas |
| **Actor principal** | Sistema automatico |
| **Actores secundarios** | Personal de Mantenimiento, Usuario |
| **Tipo** | De soporte/Secundario |
| **Prioridad** | Medios de comunicacion |

---

### Descripción
Este caso de uso describe el proceso mediante el cual el sistema FitCampus mantiene actualizado el estado de disponibilidad de las máquinas de ejercicio clave. El objetivo es informar a los usuarios y al personal sobre qué máquinas están operativas, en uso, o fuera de servicio por mantenimiento, limpieza o avería, evitando frustraciones y optimizando el flujo de trabajo.

---

### Flujo principal
1. El Sistema automático o un Personal de Mantenimiento inicia el proceso de actualización del estado de una máquina específica.
2. El Sistema identifica la máquina (Ej: Cinta 3, Elíptica 1).
3. El Personal de Mantenimiento (si es manual) o el Sistema Automático (si hay sensores) ingresa/detecta el nuevo estado de la máquina:
-Operativa (Disponible)
-En Uso (se puede ligar con UC-2/UC-3 o balizas de proximidad).
-Fuera de Servicio (Mantenimiento/Avería) .
4. El Sistema actualiza el registro de disponibilidad para la máquina con el nuevo estado y la hora de la actualización.
5. El Sistema genera una notificación interna al Administrador sobre cualquier máquina marcada como "Fuera de Servicio" .
6. El Sistema actualiza la interfaz de usuario para que la información se refleje en tiempo real para los Usuarios (ej: en la aplicación de FitCampus).

---

### Flujo alternativo
FA-1: Mantenimiento Planificado :
El Personal de Mantenimiento puede registrar un horario de inactividad futuro para la máquina (Ej: "Fuera de Servicio por Limpieza, Martes de 10:00 a 11:00").
El Sistema muestra un mensaje de "Mantenimiento Programado" y el horario a los usuarios.
Al llegar la hora, el sistema cambia el estado automáticamente y lo revierte al finalizar el horario.

FA-2: Avería Reportada por Usuario :
El Usuario tiene la opción en la aplicación de reportar un problema con una máquina.
El Sistema registra la incidencia y cambia temporalmente el estado de la máquina a "Inspección Pendiente" hasta que el personal la verifique.

---

### Postcondición
El sistema mantiene un registro preciso y en tiempo real del estado de disponibilidad de cada máquina clave del gimnasio, permitiendo al Administrador la gestión del mantenimiento y ofreciendo información clara a los Usuarios.

---

### Relaciones con otros casos de uso
| Caso relacionado | Relación | Descripción |
|------------------|-----------|--------------|
| **UC-2** | <<depends>> | El estado "En Uso" puede depender de los registros de entrada y salida del usuario en la zona de máquinas, si se implementa un control de presencia granular. |
| **UC-3** | <<depends>> | El estado "En Uso" puede depender de los registros de entrada y salida del usuario en la zona de máquinas, si se implementa un control de presencia granular.|
| **UC-9** | <<depends>> | El sistema utiliza los registros de inactividad de las máquinas para generar informes de "Tiempo Fuera de Servicio" y evaluar la eficiencia del mantenimiento. |
| **UC-01** | <<extends>> | Podría extenderse para controlar el "aforo por zona" (Ej: Zona de Cardio vs. Zona de Pesas), usando la disponibilidad de máquinas como métrica. |


---











### 4.2 Glosario

<!--
Glosario extendido complementando la Sección 1.4.
Incluye términos adicionales que surgieron durante la especificación detallada.
-->

[Si ya documentó un glosario completo en 1.4, puede referenciarlo:]

Ver Sección 1.4 para el glosario completo de términos, acrónimos y abreviaturas utilizados en este documento.

[O expandir con términos adicionales específicos del dominio:]

**Términos Adicionales del Dominio Bibliotecario:**

| Término | Definición |
|---------|------------|
| **Catálogo bibliográfico** | Registro organizado de todos los materiales disponibles en la biblioteca, con información descriptiva de cada uno. |
| **Clasificación Dewey** | Sistema Dewey de clasificación decimal utilizado para organizar libros por temas. Rango de 000 a 999. |
| **ISBN** | International Standard Book Number. Código único de 13 dígitos que identifica libros comerciales. |
| **MARC** | MAchine-Readable Cataloging. Formato estándar para representar y comunicar información bibliográfica en forma legible por computadora. |
| **Morosidad** | Estado de un usuario que no ha devuelto materiales en la fecha establecida. |
| **Obra** | Contenido intelectual (ej: "Don Quijote de la Mancha"). Una obra puede tener múltiples ediciones y ejemplares. |
| **Política de préstamo** | Reglas que definen cuántos materiales puede prestar cada tipo de usuario, por cuántos días, y si puede renovar. |
<br>

### 4.3 Diagramas del sistema

<!--
Incluya diagramas que ayuden a visualizar la arquitectura, estructura de datos,
flujos de información, etc.

TIPOS DE DIAGRAMAS ÚTILES:
- Diagrama de contexto (relación del sistema con su entorno)
- Diagrama de arquitectura de alto nivel
- Diagrama de componentes
- Diagrama de despliegue
- Modelo entidad-relación de la base de datos
- Diagramas de flujo de procesos críticos
- Wireframes/mockups de interfaces principales
-->

**4.3.1 Diagrama de Contexto del Sistema**

[Incluya diagrama mostrando el sistema y sus interacciones con actores externos y sistemas externos]

[![](https://img.plantuml.biz/plantuml/svg/VLRBRkCs5DthAswpwKm0mzEi2cCQZ2ofYG2_8Cf1fx4NZCGuH2JI9Qcaaw8VCyjPp6e-mJ_MIxqiMtQz2KBUnpdd7bxxapPKcIBF8972iB-D73pmXunBmv8dvwUKFNB180gys9tTJ098Cggru-XdBhPKqHmKImmLcup1FmxWPqoJvusIXKWzcKdryQFcsh2SNb_3X6-Up3WhsEb0cXYfch0RnPWu7OSWcHAoYVpCiao-Lg5IfKoLOJ3ECAyy_Hs94Vx6u9ShvzykTAgKVArXLqa-LSyjm7tU1vjdk46IFgSRpAMGCiof58C1a8eaZ4ljOgkTypFyPZ_WUl4y2WZSBgVkR4xWNVZsLy6PIkdxAi8fcSF5KXTKSJdqCiwmyagCcqdG2w0QYkeUMgcQn7qSNfUX3zsJVeARvbmWP4LJgLQYHbzcKdlLoMXfa934mTG5BvZ5aJkfeU_7Vt5vsLVXyd8btZN7ADaDquRlVWZeGgRloywrKQ1ZcLvt0i4VSH2LCleCcpzH8CMM8KlrlW-fwJmj14_ubcOhWI325ENbZpoXYSLY4Kx36aFEeUEmWrfClN2K2yWqNgo49vLY4e8C8nHMuOciAvZjsHAj42iHCOruKecL48sY6N_3OLJ3G-SMXqLQ7VoGBEOaZCExhWIXU3mdmOIL8_TsFrA-aIN_CHgVQgJz9tjG57noTVNXruf_LaMVmH_cMyMqL7GbujqtbVFQcBmvFurvudwUBsEeSCzduUocXjaOUd3_n5CSoZgLhs9mQ5xdqCf7eQLRyKtZs8vkx1oSSXZ7rKjrdLhaeykAlrFBS7JPqjnJYuA9wo6dW8nWIPPk5Cw7tYJ49n8SSrHsMGskMvkFxFxGHMOe9DJilcRIZYTYec0l5BPgzmrNSovnJhSqORXdDHgGQgV97sJiqTPh6enW9XjNIy4qO117mwCtfCehgqDESJgSPaoVvZ0EnvDm7WUUPL8pE1f0dqV4DkKkEG1TldGfQ8CFZnPA9anR-x_8hAXGzkWSTXl10Nmcm72MRoNAOH-pcp5bq81VG1nmFqtEzQVX3FT8vFhpg5czvRexFPn7lYcGLNrcAGc6_oksbSgmBaTLF-O-dQg-rQXA0aoXwUux9YPMaudSQBiOQP5ojDpk-nbpDTjtkfo5NhXezs_RhsM0Js44TxXFKWgyt7GfJLSYuGN-fS8slR-DumKPufTI3EuYN5VlfqQyby2dHcgGA6lfc6wDCo23w2wqsjeLUHuWliaH1E85oHxD3Q7Pr64y8UlwyVPGbOFfE0BBoF_Np0_mcA1c_lmSg7eRs3dLayI969dlljPpkbVwYqY6XDokszNHWqOCDONkkE4ah8CLNk5fzasVRBMshKCUwgrzloHZk0tzTP_5VWzRcN8gB8_giFgYkm-8DyJcQmS_dvX8yOVVVm00)](https://editor.plantuml.com/uml/VLRBRkCs5DthAswpwKm0mzEi2cCQZ2ofYG2_8Cf1fx4NZCGuH2JI9Qcaaw8VCyjPp6e-mJ_MIxqiMtQz2KBUnpdd7bxxapPKcIBF8972iB-D73pmXunBmv8dvwUKFNB180gys9tTJ098Cggru-XdBhPKqHmKImmLcup1FmxWPqoJvusIXKWzcKdryQFcsh2SNb_3X6-Up3WhsEb0cXYfch0RnPWu7OSWcHAoYVpCiao-Lg5IfKoLOJ3ECAyy_Hs94Vx6u9ShvzykTAgKVArXLqa-LSyjm7tU1vjdk46IFgSRpAMGCiof58C1a8eaZ4ljOgkTypFyPZ_WUl4y2WZSBgVkR4xWNVZsLy6PIkdxAi8fcSF5KXTKSJdqCiwmyagCcqdG2w0QYkeUMgcQn7qSNfUX3zsJVeARvbmWP4LJgLQYHbzcKdlLoMXfa934mTG5BvZ5aJkfeU_7Vt5vsLVXyd8btZN7ADaDquRlVWZeGgRloywrKQ1ZcLvt0i4VSH2LCleCcpzH8CMM8KlrlW-fwJmj14_ubcOhWI325ENbZpoXYSLY4Kx36aFEeUEmWrfClN2K2yWqNgo49vLY4e8C8nHMuOciAvZjsHAj42iHCOruKecL48sY6N_3OLJ3G-SMXqLQ7VoGBEOaZCExhWIXU3mdmOIL8_TsFrA-aIN_CHgVQgJz9tjG57noTVNXruf_LaMVmH_cMyMqL7GbujqtbVFQcBmvFurvudwUBsEeSCzduUocXjaOUd3_n5CSoZgLhs9mQ5xdqCf7eQLRyKtZs8vkx1oSSXZ7rKjrdLhaeykAlrFBS7JPqjnJYuA9wo6dW8nWIPPk5Cw7tYJ49n8SSrHsMGskMvkFxFxGHMOe9DJilcRIZYTYec0l5BPgzmrNSovnJhSqORXdDHgGQgV97sJiqTPh6enW9XjNIy4qO117mwCtfCehgqDESJgSPaoVvZ0EnvDm7WUUPL8pE1f0dqV4DkKkEG1TldGfQ8CFZnPA9anR-x_8hAXGzkWSTXl10Nmcm72MRoNAOH-pcp5bq81VG1nmFqtEzQVX3FT8vFhpg5czvRexFPn7lYcGLNrcAGc6_oksbSgmBaTLF-O-dQg-rQXA0aoXwUux9YPMaudSQBiOQP5ojDpk-nbpDTjtkfo5NhXezs_RhsM0Js44TxXFKWgyt7GfJLSYuGN-fS8slR-DumKPufTI3EuYN5VlfqQyby2dHcgGA6lfc6wDCo23w2wqsjeLUHuWliaH1E85oHxD3Q7Pr64y8UlwyVPGbOFfE0BBoF_Np0_mcA1c_lmSg7eRs3dLayI969dlljPpkbVwYqY6XDokszNHWqOCDONkkE4ah8CLNk5fzasVRBMshKCUwgrzloHZk0tzTP_5VWzRcN8gB8_giFgYkm-8DyJcQmS_dvX8yOVVVm00)

**4.3.2 Diagrama de Arquitectura de Alto Nivel**

[Incluya diagrama mostrando capas principales: Presentación, Lógica de Negocio, Acceso a Datos, Integraciones]
[![](https://img.plantuml.biz/plantuml/svg/XLVDSjis4BxpARQ-r7RYPZAPNZoTJ6LQSTMnVYegwNJg7Y0Iek6000k0IfnEhts0vWbop26dt7hLc_H9kWl-YtBZWqVS_G0illsm2tnl7JEko2GmytiX78zTOTXPp79cWwyIlX6AGpYVBkQpyMm51lrCfP87WNqjLCuCoo3MMQuLLmx-203_BbZyEZMwK4cefJRVVPSRRj7DOg7Ly-TmBT9RTo4BVXYjUAeHMGEl3EVgC39XJjiQzmkNKhyv31JAyTJqrby8zVems1ccx9ORosGR0xilmTeat7WWN4WSwQqlj7AHUCVXwTFWpoup621RCyiF4mC_ttBc7fWNvt72IGwNWc7e6OE4mwYJ8_yjdOQPs789Pn09wpZYBiHQ2htYyUsDEjuVyGn2IYqyWeYRhK16x4aGvBWYIpaSXQF522x7i5YE8yptA9piti-EO932SZ-_Jf1Nis7lu6U-lb5BRb47LcpPRu1BlE7h4ZLQJ03dMs4uBmeAvCJxMIwyt_zJsd4mn3NeJJCKuFGKDwAGbtJtYPsVdbRcC_XXDRt-zZ64KVJiCVp8jYoAZSXTux_GsbbCPVvaoZ18mIHSSYjIrI12b2rpI1O_X_3Mw8m_XXV2y8r--xW20OoJ5CqHsp1JHijLueEb10rekzwzlvg4_kTiV3KF9tFYhXLqHTjqzpaffCPytAXHuP1N4IEpky_gHjrZOjB2Y8Gb9Kk5knsEkkBM4Tv_lBG5HgUjnnVLnnV6XCpjFY2hsW-AKQVqCHoqCBkFM28oRU7-HbtohPO5QO2Ngv4il7Su4jM02cCbpbGVGzYqa0u1zx1WQRM5p9k6q9bsOkEPQjPNP3gqTgwDu_NQvST3OciO9hLL6cPh8Ia5t7OrzugHqISAOiCJhcBKLJLpAIdbZ9Pqq5WSSwlXU7an2ayQG2S7O56Ej95MibB_Nd0D62vGnL9OtM3392vQ4Vo_uXk5uJYQ0_uUhUOH2Q-kZvNiY1Khd4Pvx8c6AEeBfuUjJr27qAmn7S2tecdmUqBfmVUKWjllgQKVYjT66qP7AZtSg4Ze9nQD1il8z9081WoG61RC6KfMC_DzLmsZDTMN9jDOU2yRtoJB9S-eO4AuVDdQfqpnEmQ-nU2uVlvVMWRpvHIETKuU9ay6IMyQoj45_KSLNLAEaN9jNMfuzDCrLjdjqsUFJevet-i4atz8BD5u-Mg2zIcYZybiDRvQjiM-touhzOHIu7wmvomcDwhkDTD2OG_9cVGisqp49Qe_99gk5ZTgd35HurpU0zQzg2uSE65ILgOr1bxajl8_bBszXIbt8JRW63Mw-sIfklREiSy2BGPEP5mNhit1aZSd3-k2pdOVSBHk_I_mE59CcEvC9neofWecsm8WJ8pz5jQ6izVS03OOZ44DyXXBNIHmLD5eOVoMODeUrMmF2BvH6EuaeLwngRj5JNg7n0HhHqdtHE76NL4ggQ5z3_eGtsRRKqshbjLoD8jUZPVHw7hiQqp_jbH5VwtJLAYKMiRUGPIbfuJrEv9M6u6ThrlUOs-hnCJYszt7gbt5jvLowfBS3Dbs30_9fHi4QMMKIwGKK-fqGZ7w9VA-PfOynPGOhngTSyFs3c-bgHWJP324TopnK6uCbRCMjlle3EcHd0Ob8JBIhHuev6jSKLQB04tAovZWU2CBBrwBQv4U-4c0zoKuEtlkMncSGwHnFvXxnE0zQRLe_4s5gmrDuwyDRPskBKqnhWrLpMtzLNiD_EgrgLcg_l45J-S8rq4r8phDfeclSROH3tt_Ex29e-yghnJrhjijrZGCF9r5IcfQJydKdhKDkAPk6DB0qrbau6id3BgJUFyw2Vh3kzR-nYjZRt_ry7O7bSKtqzeGjCchSuag9EL5J-ZY7tGAVWLmEUaK2zMJrNKKzAjyEMrTY11dxBsAdqJH3q7WizFCKIkcVrhgUInqYXCILnrx-2RHRzGtpMb1yz3NaFY0lwNk0K27aWeHbDNiC29kgnyMn26qvUzBM6pvvzXtpEv3nh5U-IBAttfau0jdWspEsRclgBkF1BMbPll83XiLqbyjWw1RRG-XUzNu8BWJn9V1NTPxw43obAgdB_61lxij9xDmig2UDLh-z7Ao6eShlDvCmddagxe7HPpUwUM5dgloQLmMVMpbB66-vE8bWIigrhsN0Up-mSxCFFIIvxuKusi07s1A9FYAZCl6Yy4VCsF4ci6_V_qDU7cxqoVL_3YrBR2L26p4ipcHhsCEehawnlLBmKSXrCP3wzXV4UIkZVVq55iGNbr45I3QSOriJOcGEgvwalMl2vgm6hGYHZj35gRWwt8R3hF81WF65kTYlKMeBUK5lOU0Uo-zNn9FYjTiLjtCplm3gx3TqTMpZQxeXHCKvBfyLFXDufDzkxTFlEdIcnqqdkjRZedeDr8upeGJARLV9BIIQydubDtJLZGHVETpAEXonIGStnMsl5TXpcc_MO_Aam3dBnKM1D_Z_oAJ_m40)](https://editor.plantuml.com/uml/XLVDSjis4BxpARQ-r7RYPZAPNZoTJ6LQSTMnVYegwNJg7Y0Iek6000k0IfnEhts0vWbop26dt7hLc_H9kWl-YtBZWqVS_G0illsm2tnl7JEko2GmytiX78zTOTXPp79cWwyIlX6AGpYVBkQpyMm51lrCfP87WNqjLCuCoo3MMQuLLmx-203_BbZyEZMwK4cefJRVVPSRRj7DOg7Ly-TmBT9RTo4BVXYjUAeHMGEl3EVgC39XJjiQzmkNKhyv31JAyTJqrby8zVems1ccx9ORosGR0xilmTeat7WWN4WSwQqlj7AHUCVXwTFWpoup621RCyiF4mC_ttBc7fWNvt72IGwNWc7e6OE4mwYJ8_yjdOQPs789Pn09wpZYBiHQ2htYyUsDEjuVyGn2IYqyWeYRhK16x4aGvBWYIpaSXQF522x7i5YE8yptA9piti-EO932SZ-_Jf1Nis7lu6U-lb5BRb47LcpPRu1BlE7h4ZLQJ03dMs4uBmeAvCJxMIwyt_zJsd4mn3NeJJCKuFGKDwAGbtJtYPsVdbRcC_XXDRt-zZ64KVJiCVp8jYoAZSXTux_GsbbCPVvaoZ18mIHSSYjIrI12b2rpI1O_X_3Mw8m_XXV2y8r--xW20OoJ5CqHsp1JHijLueEb10rekzwzlvg4_kTiV3KF9tFYhXLqHTjqzpaffCPytAXHuP1N4IEpky_gHjrZOjB2Y8Gb9Kk5knsEkkBM4Tv_lBG5HgUjnnVLnnV6XCpjFY2hsW-AKQVqCHoqCBkFM28oRU7-HbtohPO5QO2Ngv4il7Su4jM02cCbpbGVGzYqa0u1zx1WQRM5p9k6q9bsOkEPQjPNP3gqTgwDu_NQvST3OciO9hLL6cPh8Ia5t7OrzugHqISAOiCJhcBKLJLpAIdbZ9Pqq5WSSwlXU7an2ayQG2S7O56Ej95MibB_Nd0D62vGnL9OtM3392vQ4Vo_uXk5uJYQ0_uUhUOH2Q-kZvNiY1Khd4Pvx8c6AEeBfuUjJr27qAmn7S2tecdmUqBfmVUKWjllgQKVYjT66qP7AZtSg4Ze9nQD1il8z9081WoG61RC6KfMC_DzLmsZDTMN9jDOU2yRtoJB9S-eO4AuVDdQfqpnEmQ-nU2uVlvVMWRpvHIETKuU9ay6IMyQoj45_KSLNLAEaN9jNMfuzDCrLjdjqsUFJevet-i4atz8BD5u-Mg2zIcYZybiDRvQjiM-touhzOHIu7wmvomcDwhkDTD2OG_9cVGisqp49Qe_99gk5ZTgd35HurpU0zQzg2uSE65ILgOr1bxajl8_bBszXIbt8JRW63Mw-sIfklREiSy2BGPEP5mNhit1aZSd3-k2pdOVSBHk_I_mE59CcEvC9neofWecsm8WJ8pz5jQ6izVS03OOZ44DyXXBNIHmLD5eOVoMODeUrMmF2BvH6EuaeLwngRj5JNg7n0HhHqdtHE76NL4ggQ5z3_eGtsRRKqshbjLoD8jUZPVHw7hiQqp_jbH5VwtJLAYKMiRUGPIbfuJrEv9M6u6ThrlUOs-hnCJYszt7gbt5jvLowfBS3Dbs30_9fHi4QMMKIwGKK-fqGZ7w9VA-PfOynPGOhngTSyFs3c-bgHWJP324TopnK6uCbRCMjlle3EcHd0Ob8JBIhHuev6jSKLQB04tAovZWU2CBBrwBQv4U-4c0zoKuEtlkMncSGwHnFvXxnE0zQRLe_4s5gmrDuwyDRPskBKqnhWrLpMtzLNiD_EgrgLcg_l45J-S8rq4r8phDfeclSROH3tt_Ex29e-yghnJrhjijrZGCF9r5IcfQJydKdhKDkAPk6DB0qrbau6id3BgJUFyw2Vh3kzR-nYjZRt_ry7O7bSKtqzeGjCchSuag9EL5J-ZY7tGAVWLmEUaK2zMJrNKKzAjyEMrTY11dxBsAdqJH3q7WizFCKIkcVrhgUInqYXCILnrx-2RHRzGtpMb1yz3NaFY0lwNk0K27aWeHbDNiC29kgnyMn26qvUzBM6pvvzXtpEv3nh5U-IBAttfau0jdWspEsRclgBkF1BMbPll83XiLqbyjWw1RRG-XUzNu8BWJn9V1NTPxw43obAgdB_61lxij9xDmig2UDLh-z7Ao6eShlDvCmddagxe7HPpUwUM5dgloQLmMVMpbB66-vE8bWIigrhsN0Up-mSxCFFIIvxuKusi07s1A9FYAZCl6Yy4VCsF4ci6_V_qDU7cxqoVL_3YrBR2L26p4ipcHhsCEehawnlLBmKSXrCP3wzXV4UIkZVVq55iGNbr45I3QSOriJOcGEgvwalMl2vgm6hGYHZj35gRWwt8R3hF81WF65kTYlKMeBUK5lOU0Uo-zNn9FYjTiLjtCplm3gx3TqTMpZQxeXHCKvBfyLFXDufDzkxTFlEdIcnqqdkjRZedeDr8upeGJARLV9BIIQydubDtJLZGHVETpAEXonIGStnMsl5TXpcc_MO_Aam3dBnKM1D_Z_oAJ_m40)

**4.3.3 Diagrama de Componentes del Sistema**

**[Incluya diagrama mostrando los principales componentes/módulos del sistema y sus interacciones]

**Módulo de prestamos**

[![](https://img.plantuml.biz/plantuml/svg/ZLMxRjim5Dtr5RUURC11ban5KIIMtGQ5dRgnaux1DNNZig18bQGC64K_fcE6JDcwwiTAwcN9bjfuiKoUS-xHVVdIMDGsZGKm5ITAahHapZPy8xYonBu5RxXa8eq8teKNv-75GrZ1tWU1vLOGJ3bkDSO83XGUHE0C5jbBb0hbBvOwUtAXOcM285JI8fUa7oOgbH7g_H2JP0o3gqHmXendBn8ckOMrip0OmSy0tASM7oQQSZ6lf9KGf1sx_86Hqks80tUvIZINMrZSXt0W-Oi5IlgEeEb7wZGDNA_NIqXG8oIr0EoTu4w9b74Ntmn6FNPMf7USaG-NFt7LOQJ0m1ptXO5vzh9rR-sHahRAaTx23WMFi8Ws1fRz5ipbqJrgsWeq7bkxEt5Ja5qM3dRkgwD-FpL_KEF1lrMa83KfQgx6477ZC7p3SpM8qPBcACOWikUOsuxCCFJEVMGyk0aFXzxF1rTZxFTIek4nXtb2LGlV9eQssHy9YN8Mh4lZgGMfB7zqDws4DEjpKmBAulRvcCbTzemWM-X_LwBgYrjANFO6_ijmgtHNNtnQNa4DsFkJAyR8A70vGglQaKxVignHTwIxulBLST8AVnobgdXtc4LvIwyE51yOe-1NOpDCDyDeuoWJDBxUCFKChx5KncurhRxCSqKH8oFPdDLnxNxSbg-rXoQsILLbFnEhnNgPLpX6Bi0V5vFPNV74CPZIcdozWriIdTleT2NCXT-Hw8NZxCcgg4X1EVDEgobLqpg6-Sxa8lcEAgvr7xjp_9hy4g3BwUhJwPoXfau5w7LoD0fBqeORIowJicoMaddwmktMTaasgR1vwFP-wXKuwjgcGdkZ7Paly7aVpedEPuPflg7SxdGIbk2MkmfxX6aR-8zWLwxBZYqRadoV5elATUxvUhxodRYw_lprOJxxEBkP3aV19Sd8_Ql_1G00)](https://editor.plantuml.com/uml/ZLMxRjim5Dtr5RUURC11ban5KIIMtGQ5dRgnaux1DNNZig18bQGC64K_fcE6JDcwwiTAwcN9bjfuiKoUS-xHVVdIMDGsZGKm5ITAahHapZPy8xYonBu5RxXa8eq8teKNv-75GrZ1tWU1vLOGJ3bkDSO83XGUHE0C5jbBb0hbBvOwUtAXOcM285JI8fUa7oOgbH7g_H2JP0o3gqHmXendBn8ckOMrip0OmSy0tASM7oQQSZ6lf9KGf1sx_86Hqks80tUvIZINMrZSXt0W-Oi5IlgEeEb7wZGDNA_NIqXG8oIr0EoTu4w9b74Ntmn6FNPMf7USaG-NFt7LOQJ0m1ptXO5vzh9rR-sHahRAaTx23WMFi8Ws1fRz5ipbqJrgsWeq7bkxEt5Ja5qM3dRkgwD-FpL_KEF1lrMa83KfQgx6477ZC7p3SpM8qPBcACOWikUOsuxCCFJEVMGyk0aFXzxF1rTZxFTIek4nXtb2LGlV9eQssHy9YN8Mh4lZgGMfB7zqDws4DEjpKmBAulRvcCbTzemWM-X_LwBgYrjANFO6_ijmgtHNNtnQNa4DsFkJAyR8A70vGglQaKxVignHTwIxulBLST8AVnobgdXtc4LvIwyE51yOe-1NOpDCDyDeuoWJDBxUCFKChx5KncurhRxCSqKH8oFPdDLnxNxSbg-rXoQsILLbFnEhnNgPLpX6Bi0V5vFPNV74CPZIcdozWriIdTleT2NCXT-Hw8NZxCcgg4X1EVDEgobLqpg6-Sxa8lcEAgvr7xjp_9hy4g3BwUhJwPoXfau5w7LoD0fBqeORIowJicoMaddwmktMTaasgR1vwFP-wXKuwjgcGdkZ7Paly7aVpedEPuPflg7SxdGIbk2MkmfxX6aR-8zWLwxBZYqRadoV5elATUxvUhxodRYw_lprOJxxEBkP3aV19Sd8_Ql_1G00)

**4.3.4 Modelo Entidad-Relación de la Base de Datos**

[Incluya diagrama ER mostrando entidades principales y sus relaciones]

Ejemplo de entidades principales:
- Usuario (id, carnet, nombres, apellidos, email, tipo_usuario, fecha_registro, estado)
- Material (id, isbn, titulo, autor, editorial, año, categoria, ubicacion)
- Ejemplar (id, material_id, codigo_barras, estado, fecha_adquisicion)
- Prestamo (id, usuario_id, ejemplar_id, fecha_prestamo, fecha_devolucion_esperada, fecha_devolucion_real, estado)
- Multa (id, prestamo_id, monto, fecha_generacion, fecha_pago, estado)
- Reserva (id, usuario_id, material_id, fecha_reserva, estado)

[![](https://img.plantuml.biz/plantuml/svg/jLbDRzl86RxhLmoCNTWMRCDEugOGDa5eYKgOIAIMaepTee0m8iVA92I76PBEUZUzzjP3sr-mnnvoAFQsL_sJ_fA-yyKlKNRQRGF446VUuRmVp_l95rcEULx44OfPI29sIlZfcguZod8IlEtr3j6G9JTqKt0SqEql2Ge98bbE8vRrilSqIJ77CGeYd6Nefnw2VrSuUB_Xh4Z28OiOHnEwUPj_JwA8VLJxZ8U4gxsh28ZbgiKv-wWMHvY_lueAqljJhvVJF29eAbb3TfBJ48UdFeaqCwTeJhESn1XTIPuNmFCVawCHnHjW2mlU0vBc1OwEXIYskt16rcY0blEbvJlUwigvcZZUmXvQw2Y8A4boaWa98unA9U3Z7gpJ_0uTzFkx1_lz0uGpL6G5vfHf7VHHlq_3bLxizz40EUx2Vcdxw9jlPc-UFvTKfwUQEC0y8JaGNLl-y9Nb7pqwFmR2fUjykxGrSH_bD6Mha0L53FmmeBRTvVJeS6YFbXFhyEHmPisjcUSlxCDZVI81KjuyS-yD2OlN73HGaLsSdvkNuHHiI4EsP_i6L8zN2HWcflgkaRMmzMv8EGa2of862-NXd4JaXYNieicXt3LxZphs-WXiJwCMHtjKPqna56U1tXOUACwUBvOZnm83mOFZZk6NCpbi2iR91f36MsAfFV93IeLxi6GL4wb1Yfjqu34uhDqyN3ZNukRvSZwptP4pykJDUbtT71THZhDLIf9G0nDUQG-TgJK1AKyUAIgspWY_bPTBYeNztQB170u4_EcFM6j_uKn1Nciw4-xLuH9pPxwmf-0FAU4PIt24FXG4u8qHYL2clAtB8_IvfZje-awlMEdD1xsZ00aJ79EQbI-xZ9n23Fe8mMNr5cTlws2vl3Isv2ogcN_gkC2qRuqy7zHVkJI80y-MbCYjkzDlS8ylm-a-dBIWGG4Eu6BPwWQNTneDZkon1RX6vv9o7J4m7xnJA2N73VlNKH9miWiGGQ2s0OeqPe2bW6HiXuQcEmH6p2UW-YREfk0LlcDDQX0oInexCSu9fm2y1chCwWDmeTcw7cCkddP6Wxo8wbm-hfcno1bVfPmc0Krnr1Mk90d9LXa98Cb9c3UWMKKr4NLAQOnH9ywLBspgszS0C16uHzSZ-3iKVxo5RunCGWhtKDn6ZU9X-q-sIWj8KO6nczQ9ETiAjfVw80qfYt77HW1yRiHzgv1y97UTmRQawM8f95d0QMfGPE9GiTOihcve1Z_tk8S4_cf34i9hkXevyvddWcEAoEnwgzgp5YV6S6QLCWxd0QSywZQ5WZ5DDc2uClAO6Dq4gFtQdiucbWyL0KifuF5c-ramBWk38YdXMG-2ven6C7b7uZJ2l8bWixeFmVS3VRnRDR2GRjXgZJd7sVt1KHS29LzDjEp4dORQPxvmTPcXR7VbspFBjuQEvuejszUvwyfwRRKo9Wu_5CBY2WzbCaoX483Wtzhz_-KrnVxKgrdBB6bh0KSWVjogtSpg0zRgBl76BQezfc-JjJ9ZMNJiEzPn92ItB2gQ8U4-z9J2rwDXHynKIgzHT-UHwleLoQ220AUi6t-72D9ErF6oVNbmP5ylRLMqNTlkK67Fe5278IgAfehFEj0Re6e8Oz3Lf6Weyxz68A3Dzg-j6W3rYiOVi27kRC9FB_vFqFV54SMKkegV1yqYIrTRbSskjt36pb35YQ47qT3MGMDekKDxeWF8TpD7r5lQLhfdO3czgV9OL_rHLTYxQ0eOk1RHZ3KFTmQHLZa2jLBTDFBP52AY0czL8MBf0QFiYHnxdFr1ewWgGh9Y5E_RKBNEA-pB8iBQ_jKhGt3CT0ks4rYDbLMgRQlqNXlFh9UMl6lekIFF5R_hTapnfj4UnIHdaDFridgTFRQDBoyi_xKjwnyGnfsFRLzuT9L5xec7NnmDzTqTn5y03GDfaUng2AalQw0q4Dp0Ittdj_bo0m-bFcKKd0e3oV2eyxOp4HB0WaIpx6ri5qWLKguc7aJs2YiuAzgpWR9kYacIuNUaA_obdCaXIxWRARJJ9hUqQ_TUZ06VZWBPs9e8CKmrBFed2CXPJfCwhsKDMVP4ujgwqPiD4U4Swdj3qs7rYVToPIr7piA3bgHcziQwjZike4Pl6ZnYcmSRMcYLP8H8ErGZlPtSjgOrjKfv5-KFUWC6UsY5Dyi-l7Saa-DrXCt1hdP1fYZbZVlU7s9X3fo8vCDKt_nw3gvKxIK59DZ6Ubyqaz1XG7HgTP7o58JvA6hvgm_9HVYYFU-P2S-dJwUdx2TKI_07EOLuTz2cg5BTWQX489Vla9Z8k-SDhUHr8AhRDP3rohvF4zPgR_KgfDgBWntA6bEah0v21kyitz4X8365hAGiToJbfqeA5VQ1eZMXwNYZjYz6HodV_aCk7n_yH-TC_RJz9TbxikJC77kG409FG3ACH73VHwmyioul68eWBcRHYDsO-HIWIbHZBoVM7E84SksN7a1fqE_3nYaQgh7izjU41WofDm7AHVyVRt_EmUfYgaeahItdEvhq3j9BH3TOzEzCRY_g0qY0CU4nJK045cq_vwQvBDKyqBwW9fG3f6OtbsNhIR8JT769mkrdd6dIQePfo1ytoSyRv6RAQOWVDOYVbhGWc8hLrQGIPLJF9j5pzDMZSqarLNDFE8LKhOOkv8n2J0NI0iI27n4o4GF2QYWyXxJDOc1qlrtsjne1Ze8Y4hyoiW5Zg5XMr_rTSofJ5n7CkQOOOQHRYov38o6zl1-fyXzqi9STINzdijqpfDeOUQLLAWEykUOcnlBTZHAyufNdMqVDgGaicxx8hEiuSLOHb1szl7vEuNguEsF0lqO6-jUV_wP1pikokDjCvltIJ6ewC3V6gMuQeBGW4jQ23PufHp7ZX06245yYNcYJtYfVQKmP1i00z7HPoXAwZWW29qyPnr7bURhzW_Vz01A9aeETQ3aKJYML650C8Es40f9eZT_X4_7cW781622HiYohyOvcFXSlGl7srmXm8rAFaPraKc1RFZA8D2D80DyMz1rewW0TNLHp8gbO8BsidGMHRWYNO_szMZRCz_iBP-RDqVTewa6TLsfQTm43zDNvsUKvn18k3IdaqyQjwGU47x8iPsetPMBqeZxdHQZX3BAFWChi5aU5q9PuRVKjJCKpfIljKG78hUD1MSZDLMWmdBgUrgPEiXpfp5_QF-jqn2hej9MqPZdufj2Ipe-IfV5a-TeJ0KCtsEh-YpDaU3MfjJGoS5Q12sWVdHacdbNImFhZC-6oqXzl2K0PrTHsOZwB8Eb-Chn3FLHUTbS9L7N9GFha3CtXHScjZ9eoVm17LMQwhFXM1SEJtxz5udkhC2-4ME5-lplJlWpFWoeUL0quq3oLD0dR9JFjkEBxgDJA1p0MhdkTl9L1vCwEQvQ8o4OyIC1A_KDVA6EdACQKxlk26QXqMJqZeYFG0tANaua8PAf25dGHlYLencaCCcEvCwxlZ1dV_fmGjMF6Kx1xZSLNOvrw8QX4M9Ml1gYkvqCBxFm1uidsxwx1v8A5WDW8_alYJ9nyF7RHqOBmGCGEk0vCweg_qR6Eci9Vn0SvaWHYCWnEbcGK0fVEbOA0ar1y5H04mjTaeMiusVu543K4x_1ji130gnuufP329PJy6JggyWyxhfFSQ4K02HTV1_K7rtUC9faYr20wKn-MJyhdzWTXIMpCVYQ-dSYLCdyqHinoosJeizRyiBbvNqeyLT52voQvK2-YzVh9JfTfb0WW4n_jeDEeLFVA7huPx4cQpv-rXfVt7YbBYNkFgV4Aa9pNLvKFJvmtDZhy-iNNXy9Lb8_qUY_WRn57_mO0)](https://editor.plantuml.com/uml/jLbDRzl86RxhLmoCNTWMRCDEugOGDa5eYKgOIAIMaepTee0m8iVA92I76PBEUZUzzjP3sr-mnnvoAFQsL_sJ_fA-yyKlKNRQRGF446VUuRmVp_l95rcEULx44OfPI29sIlZfcguZod8IlEtr3j6G9JTqKt0SqEql2Ge98bbE8vRrilSqIJ77CGeYd6Nefnw2VrSuUB_Xh4Z28OiOHnEwUPj_JwA8VLJxZ8U4gxsh28ZbgiKv-wWMHvY_lueAqljJhvVJF29eAbb3TfBJ48UdFeaqCwTeJhESn1XTIPuNmFCVawCHnHjW2mlU0vBc1OwEXIYskt16rcY0blEbvJlUwigvcZZUmXvQw2Y8A4boaWa98unA9U3Z7gpJ_0uTzFkx1_lz0uGpL6G5vfHf7VHHlq_3bLxizz40EUx2Vcdxw9jlPc-UFvTKfwUQEC0y8JaGNLl-y9Nb7pqwFmR2fUjykxGrSH_bD6Mha0L53FmmeBRTvVJeS6YFbXFhyEHmPisjcUSlxCDZVI81KjuyS-yD2OlN73HGaLsSdvkNuHHiI4EsP_i6L8zN2HWcflgkaRMmzMv8EGa2of862-NXd4JaXYNieicXt3LxZphs-WXiJwCMHtjKPqna56U1tXOUACwUBvOZnm83mOFZZk6NCpbi2iR91f36MsAfFV93IeLxi6GL4wb1Yfjqu34uhDqyN3ZNukRvSZwptP4pykJDUbtT71THZhDLIf9G0nDUQG-TgJK1AKyUAIgspWY_bPTBYeNztQB170u4_EcFM6j_uKn1Nciw4-xLuH9pPxwmf-0FAU4PIt24FXG4u8qHYL2clAtB8_IvfZje-awlMEdD1xsZ00aJ79EQbI-xZ9n23Fe8mMNr5cTlws2vl3Isv2ogcN_gkC2qRuqy7zHVkJI80y-MbCYjkzDlS8ylm-a-dBIWGG4Eu6BPwWQNTneDZkon1RX6vv9o7J4m7xnJA2N73VlNKH9miWiGGQ2s0OeqPe2bW6HiXuQcEmH6p2UW-YREfk0LlcDDQX0oInexCSu9fm2y1chCwWDmeTcw7cCkddP6Wxo8wbm-hfcno1bVfPmc0Krnr1Mk90d9LXa98Cb9c3UWMKKr4NLAQOnH9ywLBspgszS0C16uHzSZ-3iKVxo5RunCGWhtKDn6ZU9X-q-sIWj8KO6nczQ9ETiAjfVw80qfYt77HW1yRiHzgv1y97UTmRQawM8f95d0QMfGPE9GiTOihcve1Z_tk8S4_cf34i9hkXevyvddWcEAoEnwgzgp5YV6S6QLCWxd0QSywZQ5WZ5DDc2uClAO6Dq4gFtQdiucbWyL0KifuF5c-ramBWk38YdXMG-2ven6C7b7uZJ2l8bWixeFmVS3VRnRDR2GRjXgZJd7sVt1KHS29LzDjEp4dORQPxvmTPcXR7VbspFBjuQEvuejszUvwyfwRRKo9Wu_5CBY2WzbCaoX483Wtzhz_-KrnVxKgrdBB6bh0KSWVjogtSpg0zRgBl76BQezfc-JjJ9ZMNJiEzPn92ItB2gQ8U4-z9J2rwDXHynKIgzHT-UHwleLoQ220AUi6t-72D9ErF6oVNbmP5ylRLMqNTlkK67Fe5278IgAfehFEj0Re6e8Oz3Lf6Weyxz68A3Dzg-j6W3rYiOVi27kRC9FB_vFqFV54SMKkegV1yqYIrTRbSskjt36pb35YQ47qT3MGMDekKDxeWF8TpD7r5lQLhfdO3czgV9OL_rHLTYxQ0eOk1RHZ3KFTmQHLZa2jLBTDFBP52AY0czL8MBf0QFiYHnxdFr1ewWgGh9Y5E_RKBNEA-pB8iBQ_jKhGt3CT0ks4rYDbLMgRQlqNXlFh9UMl6lekIFF5R_hTapnfj4UnIHdaDFridgTFRQDBoyi_xKjwnyGnfsFRLzuT9L5xec7NnmDzTqTn5y03GDfaUng2AalQw0q4Dp0Ittdj_bo0m-bFcKKd0e3oV2eyxOp4HB0WaIpx6ri5qWLKguc7aJs2YiuAzgpWR9kYacIuNUaA_obdCaXIxWRARJJ9hUqQ_TUZ06VZWBPs9e8CKmrBFed2CXPJfCwhsKDMVP4ujgwqPiD4U4Swdj3qs7rYVToPIr7piA3bgHcziQwjZike4Pl6ZnYcmSRMcYLP8H8ErGZlPtSjgOrjKfv5-KFUWC6UsY5Dyi-l7Saa-DrXCt1hdP1fYZbZVlU7s9X3fo8vCDKt_nw3gvKxIK59DZ6Ubyqaz1XG7HgTP7o58JvA6hvgm_9HVYYFU-P2S-dJwUdx2TKI_07EOLuTz2cg5BTWQX489Vla9Z8k-SDhUHr8AhRDP3rohvF4zPgR_KgfDgBWntA6bEah0v21kyitz4X8365hAGiToJbfqeA5VQ1eZMXwNYZjYz6HodV_aCk7n_yH-TC_RJz9TbxikJC77kG409FG3ACH73VHwmyioul68eWBcRHYDsO-HIWIbHZBoVM7E84SksN7a1fqE_3nYaQgh7izjU41WofDm7AHVyVRt_EmUfYgaeahItdEvhq3j9BH3TOzEzCRY_g0qY0CU4nJK045cq_vwQvBDKyqBwW9fG3f6OtbsNhIR8JT769mkrdd6dIQePfo1ytoSyRv6RAQOWVDOYVbhGWc8hLrQGIPLJF9j5pzDMZSqarLNDFE8LKhOOkv8n2J0NI0iI27n4o4GF2QYWyXxJDOc1qlrtsjne1Ze8Y4hyoiW5Zg5XMr_rTSofJ5n7CkQOOOQHRYov38o6zl1-fyXzqi9STINzdijqpfDeOUQLLAWEykUOcnlBTZHAyufNdMqVDgGaicxx8hEiuSLOHb1szl7vEuNguEsF0lqO6-jUV_wP1pikokDjCvltIJ6ewC3V6gMuQeBGW4jQ23PufHp7ZX06245yYNcYJtYfVQKmP1i00z7HPoXAwZWW29qyPnr7bURhzW_Vz01A9aeETQ3aKJYML650C8Es40f9eZT_X4_7cW781622HiYohyOvcFXSlGl7srmXm8rAFaPraKc1RFZA8D2D80DyMz1rewW0TNLHp8gbO8BsidGMHRWYNO_szMZRCz_iBP-RDqVTewa6TLsfQTm43zDNvsUKvn18k3IdaqyQjwGU47x8iPsetPMBqeZxdHQZX3BAFWChi5aU5q9PuRVKjJCKpfIljKG78hUD1MSZDLMWmdBgUrgPEiXpfp5_QF-jqn2hej9MqPZdufj2Ipe-IfV5a-TeJ0KCtsEh-YpDaU3MfjJGoS5Q12sWVdHacdbNImFhZC-6oqXzl2K0PrTHsOZwB8Eb-Chn3FLHUTbS9L7N9GFha3CtXHScjZ9eoVm17LMQwhFXM1SEJtxz5udkhC2-4ME5-lplJlWpFWoeUL0quq3oLD0dR9JFjkEBxgDJA1p0MhdkTl9L1vCwEQvQ8o4OyIC1A_KDVA6EdACQKxlk26QXqMJqZeYFG0tANaua8PAf25dGHlYLencaCCcEvCwxlZ1dV_fmGjMF6Kx1xZSLNOvrw8QX4M9Ml1gYkvqCBxFm1uidsxwx1v8A5WDW8_alYJ9nyF7RHqOBmGCGEk0vCweg_qR6Eci9Vn0SvaWHYCWnEbcGK0fVEbOA0ar1y5H04mjTaeMiusVu543K4x_1ji130gnuufP329PJy6JggyWyxhfFSQ4K02HTV1_K7rtUC9faYr20wKn-MJyhdzWTXIMpCVYQ-dSYLCdyqHinoosJeizRyiBbvNqeyLT52voQvK2-YzVh9JfTfb0WW4n_jeDEeLFVA7huPx4cQpv-rXfVt7YbBYNkFgV4Aa9pNLvKFJvmtDZhy-iNNXy9Lb8_qUY_WRn57_mO0)

**4.3.5 Mockups de Interfaces Principales**

[Incluya bocetos o mockups de las pantallas principales:]
- Pantalla de login
- Panel principal / Dashboard
- Pantalla de préstamos
- Pantalla de búsqueda de catálogo
- Pantalla de registro de usuario

[Puede usar herramientas como Figma, Balsamiq, o incluso dibujos escaneados]

<br>

### 4.4 Matriz de trazabilidad

<!--
La matriz de trazabilidad vincula requisitos con otros artefactos del proyecto
para asegurar que todos los requisitos están cubiertos en diseño, implementación,
y pruebas.

TIPOS DE TRAZABILIDAD:
- Requisitos <-> Casos de Uso
- Requisitos <-> Casos de Prueba
- Requisitos <-> Módulos de Código
- Requisitos <-> Fuente (stakeholder que lo solicitó)
-->

**4.4.1 Matriz Requisitos - Casos de Uso**

| Requisito | Caso de Uso Relacionado | Prioridad |
|-----------|-------------------------|-----------|
| RF-001 | CU-000 (Login) | Esencial |
| RF-010 | CU-003 (Registrar Usuario) | Esencial |
| RF-030 | CU-001 (Realizar Préstamo) | Esencial |
| RF-031 | CU-001 (Realizar Préstamo) | Esencial |
| RF-040 | CU-002 (Realizar Devolución) | Esencial |
| ... | ... | ... |

**4.4.2 Matriz Requisitos - Casos de Prueba**

| Requisito | Casos de Prueba | Estado Prueba |
|-----------|-----------------|---------------|
| RF-001 | TC-001, TC-002, TC-003 | Pendiente |
| RF-002 | TC-004, TC-005 | Pendiente |
| RF-010 | TC-010, TC-011, TC-012, TC-013 | Pendiente |
| ... | ... | ... |

[Esta matriz se completará durante la fase de pruebas]

<br>


*Plantilla elaborada con propósitos académicos*  
*Basada en IEEE Std 830-1998*  
*Versión  1.0 - Octubre 2025*
