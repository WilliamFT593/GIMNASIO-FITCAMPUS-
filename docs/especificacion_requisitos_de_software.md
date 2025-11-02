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

## 1 INTRODUCCIÓN

<!-- 
═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 1: INTRODUCCIÓN
═══════════════════════════════════════════════════════════════════════════════

PROPÓSITO DE ESTA SECCIÓN:
Proporcionar una visión general del documento de especificación de requisitos.
Esta sección debe ser comprensible para TODOS los lectores, incluyendo aquellos
sin conocimientos técnicos profundos (stakeholders, gerentes, clientes).

IMPORTANCIA ACADÉMICA:
La introducción establece el contexto del proyecto y facilita la comprensión
del documento. Una buena introducción permite que diferentes stakeholders 
comprendan rápidamente el propósito y alcance del sistema sin necesidad de 
leer todo el documento.

AUDIENCIA:
- Equipo de desarrollo
- Analistas de negocio
- Gerentes de proyecto
- Clientes/Stakeholders
- Equipo de QA y testing
- Futuros mantenedores del sistema
-->

### 1.1 Propósito

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Explicar claramente POR QUÉ existe este documento y QUIÉN lo utilizará.

QUÉ DEBE INCLUIR (2-4 párrafos):
✓ Objetivo principal del documento SRS
✓ Público objetivo específico (desarrolladores, testers, cliente, etc.)
✓ Cómo se utilizará el documento en el ciclo de vida del proyecto
✓ Alcance de versión o fase del proyecto (si aplica)

PREGUNTAS GUÍA:
1. ¿Para qué se crea este documento?
2. ¿Quiénes lo van a leer y usar?
3. ¿Qué decisiones se tomarán basándose en este documento?
4. ¿Este documento cubre todo el sistema o solo una versión/módulo?

ERRORES COMUNES A EVITAR:
✗ Ser demasiado vago: "Este documento describe un sistema"
✗ Confundir propósito del documento con propósito del sistema
✗ No especificar la audiencia
✗ Ser excesivamente técnico en esta sección

EJEMPLO ACADÉMICO:
"Este documento de Especificación de Requisitos de Software (SRS) describe los 
requisitos funcionales y no funcionales para el Sistema de Gestión Bibliotecaria 
'BiblioTech', versión 1.0. El propósito de este documento es establecer una base 
común de entendimiento entre el cliente (Biblioteca Municipal Central) y el equipo 
de desarrollo sobre lo que el sistema debe hacer y cómo debe comportarse.

Este documento será utilizado por:
- El equipo de desarrollo como guía para la implementación del sistema
- Los analistas de QA para diseñar casos de prueba
- El cliente para validar que sus necesidades están correctamente reflejadas
- Los gerentes de proyecto para planificar recursos y cronogramas

Las especificaciones aquí contenidas servirán como base contractual para la 
aceptación del sistema y como referencia durante todo el ciclo de vida del 
desarrollo."
-->

[Escriba aquí el propósito de este documento. Use los párrafos necesarios para explicar claramente por qué existe este SRS y quiénes lo utilizarán.]

<br>

### 1.2 Alcance

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Definir claramente QUÉ está incluido y QUÉ NO está incluido en este sistema.

QUÉ DEBE INCLUIR:
✓ Nombre oficial del sistema/software
✓ Descripción breve de lo que hace el sistema (2-3 párrafos)
✓ Beneficios principales que aportará
✓ Objetivos específicos y medibles
✓ Límites del sistema (qué NO incluye)
✓ Relación con otros sistemas (si aplica)

ESTRUCTURA SUGERIDA:

**Nombre del Sistema:**
[Nombre oficial completo]

**Descripción:**
[Explicar en 2-3 párrafos qué hace el sistema, cuál es su dominio de aplicación,
y qué problema resuelve]

**Beneficios Principales:**
- [Beneficio 1: ahorro de tiempo, reducción de errores, etc.]
- [Beneficio 2]
- [Beneficio 3]

**Objetivos del Sistema:**
1. [Objetivo medible 1: Ej. "Reducir el tiempo de préstamo de libros de 5 a 2 minutos"]
2. [Objetivo medible 2]
3. [Objetivo medible 3]

**Límites del Sistema (Fuera de Alcance):**
- [Lo que NO hará el sistema: Ej. "El sistema NO manejará la contabilidad interna de la biblioteca"]
- [Funcionalidad excluida explícitamente]

EJEMPLO ACADÉMICO:

**Nombre del Sistema:** Sistema de Gestión Bibliotecaria BiblioTech

**Descripción:**
BiblioTech es un sistema integral de gestión bibliotecaria diseñado para automatizar 
las operaciones diarias de bibliotecas públicas de tamaño mediano (10,000 a 50,000 
volúmenes). El sistema gestiona el catálogo de materiales, préstamos, devoluciones, 
reservas, y el registro de usuarios.

El sistema reemplazará el actual proceso manual de registro en tarjetas físicas y 
planillas Excel, proporcionando una plataforma centralizada, confiable y de fácil 
acceso para bibliotecarios y usuarios. BiblioTech también incluirá un módulo de 
consulta en línea para que los usuarios puedan buscar materiales y verificar 
disponibilidad desde sus hogares.

**Beneficios Principales:**
- Reducción del tiempo promedio de atención por usuario de 5 a 2 minutos
- Eliminación del 100% de los registros en papel
- Disponibilidad de información en tiempo real sobre el inventario
- Reducción de pérdidas de material mediante sistema automatizado de seguimiento
- Acceso remoto al catálogo 24/7 para los usuarios

**Objetivos del Sistema:**
1. Digitalizar el 100% del catálogo existente en los primeros 3 meses
2. Reducir en un 60% el tiempo de procesamiento de préstamos y devoluciones
3. Implementar sistema de notificaciones automáticas para devoluciones vencidas
4. Proveer reportes estadísticos mensuales sobre uso de la biblioteca
5. Garantizar disponibilidad del sistema del 99.5% durante horario de operación

**Límites del Sistema (Fuera de Alcance):**
- Gestión contable y presupuestaria de la biblioteca
- Sistema de punto de venta para librería anexa
- Gestión de recursos humanos y nómina del personal
- Sistema de seguridad física del edificio (cámaras, alarmas)
- Plataforma de e-books o biblioteca digital de contenidos
-->

[Complete esta sección siguiendo la estructura sugerida arriba]

<br>

### 1.3 Personal involucrado

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Identificar a todas las personas clave que participan en la definición, desarrollo,
y validación del sistema.

IMPORTANCIA:
Esta sección es crucial para:
- Establecer responsabilidades claras
- Facilitar la comunicación entre stakeholders
- Documentar la cadena de toma de decisiones
- Permitir contacto directo cuando surjan dudas

TABLA REQUERIDA:
Complete la siguiente tabla para cada persona involucrada en el proyecto.
Incluya mínimo: Cliente/Patrocinador, Jefe de Proyecto, Analista Principal,
y Líder de Desarrollo.
-->

| Nombre | Rol | Responsabilidades | Información de Contacto |
|--------|-----|-------------------|-------------------------|
| [Nombre completo] | Cliente/Patrocinador del Proyecto | - Aprobar requisitos<br>- Proporcionar retroalimentación<br>- Validar entregas<br>- Decisiones finales sobre alcance | Email: [correo]<br>Tel: [teléfono]<br>Organización: [nombre] |
| [Nombre completo] | Gerente/Jefe de Proyecto | - Coordinar equipo de desarrollo<br>- Gestionar recursos y cronograma<br>- Punto de contacto principal con cliente<br>- Resolución de conflictos | Email: [correo]<br>Tel: [teléfono] |
| [Nombre completo] | Analista de Requisitos | - Elicitación de requisitos<br>- Documentación de SRS<br>- Validación con stakeholders<br>- Gestión de cambios en requisitos | Email: [correo]<br>Tel: [teléfono] |
| [Nombre completo] | Arquitecto de Software / Líder Técnico | - Diseño de arquitectura del sistema<br>- Decisiones técnicas<br>- Revisión de código<br>- Establecer estándares de desarrollo | Email: [correo]<br>Tel: [teléfono] |
| [Nombre completo] | Líder de QA/Testing | - Diseño de estrategia de pruebas<br>- Validación de requisitos<br>- Asegurar calidad del producto<br>- Reportes de defectos | Email: [correo]<br>Tel: [teléfono] |

<!-- 
NOTA PARA PROYECTOS ACADÉMICOS:
En contextos académicos, pueden incluir roles como:
- Docente/Asesor del proyecto
- Estudiantes por rol (analista, desarrollador, tester)
- "Cliente simulado" o stakeholder de práctica
-->

<br>

### 1.4 Definiciones, acrónimos y abreviaturas

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Proporcionar un glosario de términos técnicos, acrónimos y abreviaturas utilizados
en el documento para garantizar comprensión común.

IMPORTANCIA:
Evita ambigüedades y malentendidos. Un mismo término puede significar cosas diferentes
en distintos contextos (ej: "usuario" puede ser usuario final o usuario del sistema).

ORGANIZACIÓN:
Liste los términos en orden alfabético para facilitar la consulta.

TIPOS DE ENTRADAS:
1. Términos del dominio del negocio
2. Términos técnicos de software
3. Acrónimos del proyecto
4. Abreviaturas utilizadas en el documento

FORMATO SUGERIDO:
-->

| Término | Definición |
|---------|------------|
| **API** | Application Programming Interface (Interfaz de Programación de Aplicaciones). Conjunto de definiciones y protocolos para integrar y comunicar aplicaciones de software. |
| **CRUD** | Create, Read, Update, Delete. Operaciones básicas de gestión de datos en una base de datos. |
| **Framework** | Estructura conceptual y tecnológica de soporte definida, normalmente con artefactos o módulos de software concretos, que puede servir de base para la organización y desarrollo de software. |
| **IEEE 830** | Estándar del Instituto de Ingenieros Eléctricos y Electrónicos para especificaciones de requisitos de software. |
| **RF** | Requisito Funcional. Especifica una función que debe realizar el sistema. |
| **RNF** | Requisito No Funcional. Especifica criterios de calidad, restricciones o atributos del sistema. |
| **SRS** | Software Requirements Specification (Especificación de Requisitos de Software). |
| **Stakeholder** | Cualquier persona, grupo u organización que puede afectar o ser afectado por el proyecto. |
| **UI** | User Interface (Interfaz de Usuario). Medio con que el usuario puede comunicarse con el sistema. |
| **UX** | User Experience (Experiencia de Usuario). Percepción y respuesta del usuario resultante del uso o anticipación del uso de un producto. |

<!-- 
INSTRUCCIONES:
1. Agregue TODOS los términos técnicos o del dominio que use en el documento
2. Agregue los acrónimos de su organización o proyecto específico
3. Defina términos ambiguos de manera precisa para su contexto
4. Si usa términos en inglés, incluya la traducción al español

EJEMPLO DE TÉRMINOS ESPECÍFICOS DE DOMINIO (Biblioteca):

| Término | Definición |
|---------|------------|
| **Ejemplar** | Copia física específica de un material bibliográfico. Un libro puede tener múltiples ejemplares. |
| **Material bibliográfico** | Cualquier recurso disponible en la biblioteca: libros, revistas, DVDs, etc. |
| **Préstamo a domicilio** | Tipo de préstamo que permite al usuario llevar material fuera de la biblioteca por un período determinado. |
| **Préstamo en sala** | Tipo de préstamo que solo permite consultar el material dentro de las instalaciones de la biblioteca. |
| **Usuario activo** | Usuario registrado que ha realizado al menos un préstamo en los últimos 12 meses. |
-->

[Complete la tabla con los términos específicos de su proyecto]

<br>

### 1.5 Referencias

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Listar todos los documentos, estándares, normas y recursos externos referenciados
en este SRS o que proporcionan contexto adicional.

IMPORTANCIA:
Permite a los lectores:
- Profundizar en temas específicos
- Validar el cumplimiento de estándares
- Acceder a documentación complementaria
- Verificar la trazabilidad con otros documentos del proyecto

TIPOS DE REFERENCIAS COMUNES:
1. Estándares y normas (IEEE, ISO, etc.)
2. Documentos del proyecto (plan de proyecto, visión, arquitectura)
3. Documentación técnica de frameworks o tecnologías
4. Bibliografía de referencia
5. Sitios web y recursos en línea

FORMATO SUGERIDO (estilo académico):
-->

**Estándares y Normas:**

1. IEEE Computer Society. (1998). *IEEE Recommended Practice for Software Requirements Specifications*. IEEE Std 830-1998. Nueva York: IEEE.

2. ISO/IEC/IEEE 29148:2018. *Systems and software engineering — Life cycle processes — Requirements engineering*. Ginebra: International Organization for Standardization.

**Documentos del Proyecto:**

3. [Nombre del Autor]. ([Año]). *Documento de Visión del Proyecto [Nombre del Proyecto]*. [Organización]. Versión [X.X].

4. [Nombre del Autor]. ([Año]). *Plan de Gestión del Proyecto [Nombre del Proyecto]*. [Organización].

**Documentación Técnica:**

5. [Framework/Tecnología]. ([Año]). *Documentación Oficial*. Recuperado de [URL]

6. [Base de Datos]. ([Año]). *Manual de Referencia*. Recuperado de [URL]

**Bibliografía de Referencia:**

7. Sommerville, I. (2016). *Ingeniería de Software* (10ª ed.). México: Pearson Educación.

8. Pressman, R. S., & Maxim, B. R. (2021). *Ingeniería del Software: Un Enfoque Práctico* (9ª ed.). México: McGraw-Hill Education.

**Recursos en Línea:**

9. Material del curso de Levantamiento de Requerimientos. (2025). [Universidad/Institución]. Disponible en [URL del aula virtual].

<!-- 
EJEMPLO COMPLETO PARA PROYECTO BIBLIOTECARIO:

**Estándares y Normas:**
1. IEEE Std 830-1998. Software Requirements Specifications.
2. ISO 2709:2008. Information and documentation — Format for information exchange.

**Documentos del Proyecto:**
3. Rodríguez, M. (2024). Documento de Visión - Sistema BiblioTech. Biblioteca Municipal Central.
4. González, A. (2024). Estudio de Factibilidad - Automatización de Procesos Bibliotecarios.

**Documentación Técnica:**
5. Django Framework Documentation. (2024). Disponible en: https://docs.djangoproject.com/
6. PostgreSQL 15 Documentation. (2024). Disponible en: https://www.postgresql.org/docs/15/

**Bibliografía:**
7. Lippincott, S. (2015). Library Automation in Transitional Societies: Lessons from Eastern Europe. Oxford: Chandos Publishing.
-->

[Complete esta sección con las referencias relevantes para su proyecto]

<br>

### 1.6 Resumen

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Proporcionar una sinopsis ejecutiva del contenido y organización del resto del
documento SRS.

IMPORTANCIA:
Esta sección orienta al lector sobre:
- Qué encontrará en cada sección principal
- Cómo está organizado el documento
- Dónde buscar información específica

ESTRUCTURA RECOMENDADA:
Un párrafo descriptivo por cada sección principal (Sección 2 y Sección 3),
explicando qué tipo de información contiene.

LONGITUD:
2-4 párrafos máximo. Debe ser conciso pero informativo.

EJEMPLO ACADÉMICO:
-->

Este documento de Especificación de Requisitos de Software está organizado en cuatro secciones principales que siguen el estándar IEEE 830-1998.

**La Sección 2, Descripción General**, presenta una visión global del sistema sin entrar en detalles técnicos. Incluye la perspectiva del producto dentro del contexto organizacional, un resumen de las funciones principales del sistema, las características de los diferentes tipos de usuarios que interactuarán con el sistema, y las restricciones generales bajo las cuales debe operar. También documenta las suposiciones y dependencias que podrían afectar los requisitos, así como las funcionalidades consideradas para versiones futuras.

**La Sección 3, Requisitos Específicos**, constituye el núcleo técnico del documento. Esta sección detalla exhaustivamente todos los requisitos funcionales (lo que el sistema debe hacer) y los requisitos no funcionales (cómo debe comportarse el sistema). Incluye especificaciones detalladas de las interfaces del sistema (usuario, hardware, software y comunicación), criterios de rendimiento, requisitos de seguridad, fiabilidad y disponibilidad, así como restricciones de diseño y otros atributos de calidad que el sistema debe cumplir.

**La Sección 4, Apéndices**, contiene información complementaria que respalda las secciones anteriores, incluyendo diagramas del sistema, modelos de casos de uso, glosario extendido de términos, y matrices de trazabilidad que vinculan requisitos con casos de prueba. Esta sección también puede incluir prototipos de interfaces, esquemas de bases de datos, y otros artefactos que ayudan a clarificar los requisitos especificados.

[Ajuste este resumen según la organización específica de su documento]

<br>

---

## 2 DESCRIPCIÓN GENERAL

<!-- 
═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 2: DESCRIPCIÓN GENERAL
═══════════════════════════════════════════════════════════════════════════════

PROPÓSITO DE ESTA SECCIÓN:
Proporcionar contexto y visión general del sistema sin entrar en detalles técnicos
específicos. Esta sección ayuda a los lectores a comprender el "panorama general"
antes de sumergirse en los requisitos específicos.

IMPORTANCIA ACADÉMICA:
Esta sección establece el contexto de negocio y técnico que justifica los requisitos
específicos que vendrán en la Sección 3. Es fundamental para que stakeholders no
técnicos comprendan el propósito y las capacidades del sistema.

AUDIENCIA PRINCIPAL:
- Gerentes y ejecutivos
- Analistas de negocio
- Arquitectos de sistemas
- Nuevos miembros del equipo

PRINCIPIO CLAVE:
Todo lo descrito en la Sección 2 debe ser GENERAL. Los detalles específicos,
medibles y verificables van en la Sección 3.
-->

### 2.1 Perspectiva del producto

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Situar el sistema en su contexto más amplio: ¿Es un sistema completamente nuevo?
¿Reemplaza un sistema existente? ¿Es parte de un sistema mayor? ¿Cómo se relaciona
con otros sistemas?

QUÉ DEBE INCLUIR:

1. CONTEXTO DEL SISTEMA:
  - Si es un nuevo producto independiente, reemplazo de sistema legacy, o 
    componente de un sistema mayor
  - Relación con otros sistemas existentes en la organización

2. INTERFACES DEL SISTEMA (Vista general):
  - Interfaces con sistemas externos (NO detalles, solo mención)
  - Interfaces con hardware específico
  - Interfaces con otros componentes de software

3. DIAGRAMA DE CONTEXTO (Altamente recomendado):
  Un diagrama simple que muestre:
  - El sistema como caja central
  - Actores externos (usuarios, otros sistemas)
  - Flujos de información principales

EJEMPLO ACADÉMICO:

**Contexto del Sistema:**

BiblioTech es un sistema de información nuevo que reemplazará completamente el 
actual sistema manual de gestión bibliotecaria basado en tarjetas físicas y hojas 
de cálculo Excel. El sistema operará como una aplicación independiente pero 
compartirá cierta información con sistemas externos de la biblioteca.

BiblioTech NO es un subsistema de un sistema mayor, sino una aplicación completa 
y autónoma diseñada específicamente para las necesidades de la Biblioteca Municipal 
Central. Sin embargo, el sistema deberá integrarse con:

- Sistema de identificación de usuarios de la municipalidad (para validar datos 
  de ciudadanos)
- Sistema de correo electrónico institucional (para envío de notificaciones)
- Sistema de respaldo centralizado de la municipalidad (para backup automático)

**Relación con Sistemas Existentes:**

El sistema actual que BiblioTech reemplazará consiste en:
- Tarjetas físicas de catálogo ordenadas alfabéticamente
- Planillas Excel para control de préstamos
- Registro manual en libros de visitas
- Archivo físico de fichas de usuarios

BiblioTech digitalizará completamente estos procesos, manteniendo la misma 
lógica de negocio pero eliminando el manejo de papel.

**Interfaces del Sistema (Visión General):**

BiblioTech interactuará con:
1. **Usuarios del Sistema**: Bibliotecarios, administradores, y usuarios finales 
  (vía interfaz web)
2. **Sistemas Externos**: 
  - API del Sistema de Identificación Municipal
  - Servidor SMTP para envío de correos
  - Servidor de respaldo institucional
3. **Hardware**: 
  - Lectores de código de barras (para escaneo de libros y carnets)
  - Impresoras térmicas (para comprobantes de préstamo)
  - Servidor de base de datos

[Incluya aquí un diagrama de contexto del sistema]

ESTRUCTURA DEL DIAGRAMA DE CONTEXTO:
Puede usar notación simple con cajas y flechas. Ejemplo en texto:

┌─────────────────┐
│    Usuarios     │────┐
│   de Internet   │    │
└─────────────────┘    │
                       ▼
┌────────────────┐   ┌──────────────────────┐   ┌──────────────────┐
│ Bibliotecarios │─▶│   Sistema BiblioTech │─▶│  Sistema Email   │
└────────────────┘   └──────────────────────┘   └──────────────────┘
                              │
                              ▼
                     ┌──────────────────┐
                     │  Base de Datos   │
                     └──────────────────┘

NOTA: En su documento final, reemplace esto con un diagrama formal usando herramientas
como Draw.io, notación mermaid, Lucidchart, o similar.
-->

[Complete esta subsección describiendo la perspectiva de su producto e incluya un diagrama de contexto]

<br>

### 2.2 Funciones del producto

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Proporcionar un resumen de las funciones PRINCIPALES del sistema. NO se trata de
listar todos los requisitos funcionales (eso va en la Sección 3.1), sino de dar
una visión general de las capacidades del sistema.

IMPORTANCIA:
Esta subsección permite a los lectores no técnicos comprender rápidamente qué
hará el sistema sin perderse en detalles técnicos.

NIVEL DE DETALLE:
- ALTO NIVEL: "El sistema gestionará préstamos de libros"
- NO: "El sistema validará que el ISBN tenga formato correcto usando expresión regular"

ORGANIZACIÓN SUGERIDA:
Agrupe las funciones por módulos o áreas funcionales del sistema.

FORMATO RECOMENDADO:
Use viñetas con descripciones de 1-2 líneas por función principal.

EJEMPLO ACADÉMICO:

El Sistema BiblioTech proporcionará las siguientes funciones principales:

**Gestión de Catálogo:**
- Registro y mantenimiento de materiales bibliográficos (libros, revistas, DVDs, etc.)
- Catalogación según estándares bibliotecarios
- Búsqueda avanzada de materiales por múltiples criterios
- Gestión de múltiples ejemplares de un mismo título

**Gestión de Usuarios:**
- Registro de nuevos usuarios de la biblioteca
- Mantenimiento de información de usuarios (actualización de datos, foto, etc.)
- Gestión de diferentes tipos de membresía (estudiante, adulto, infantil)
- Control de estado de usuarios (activo, suspendido, moroso)

**Gestión de Préstamos:**
- Procesamiento de préstamos y devoluciones de material
- Renovación de préstamos
- Sistema de reservas de materiales no disponibles
- Cálculo automático de multas por retraso
- Generación de comprobantes de préstamo

**Gestión de Notificaciones:**
- Notificaciones automáticas de vencimiento de préstamos
- Alertas de disponibilidad de material reservado
- Recordatorios de multas pendientes
- Comunicados generales a usuarios

**Reportes y Estadísticas:**
- Reportes de materiales más prestados
- Estadísticas de uso de la biblioteca
- Reportes de inventario
- Estado de cuenta de usuarios (préstamos activos, multas, etc.)

**Administración del Sistema:**
- Gestión de usuarios del sistema (bibliotecarios, administradores)
- Configuración de parámetros del sistema (días de préstamo, multas, etc.)
- Respaldo y restauración de datos
- Auditoría de operaciones del sistema

OPCIONAL: Puede incluir un diagrama de alto nivel mostrando los módulos principales
y cómo se relacionan.

NOTA IMPORTANTE:
Esta NO es la especificación detallada de requisitos funcionales. Cada función
aquí mencionada se expandirá con requisitos específicos, medibles y verificables
en la Sección 3.1.
-->

[Complete esta subsección describiendo las funciones principales de su sistema, agrupadas lógicamente]

<br>

### 2.3 Características de los usuarios

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Identificar y describir los diferentes tipos de usuarios que interactuarán con
el sistema, incluyendo sus características relevantes que puedan afectar el diseño.

IMPORTANCIA:
Comprender a los usuarios es fundamental para:
- Diseñar interfaces apropiadas para cada perfil
- Establecer niveles adecuados de seguridad y permisos
- Determinar requisitos de capacitación
- Identificar necesidades de usabilidad y accesibilidad

QUÉ INCLUIR PARA CADA TIPO DE USUARIO:

1. Tipo de usuario (nombre del rol)
2. Descripción general del rol
3. Responsabilidades en el sistema
4. Nivel de experiencia técnica
5. Nivel de experiencia con el dominio del negocio
6. Frecuencia de uso del sistema
7. Funciones principales que utilizará
8. Necesidades especiales (accesibilidad, idioma, etc.)

FORMATO SUGERIDO:
Use una tabla o subsecciones para cada tipo de usuario.

TABLA RECOMENDADA:
-->

| Característica | Usuario Tipo 1: [Nombre del Rol] | Usuario Tipo 2: [Nombre del Rol] | Usuario Tipo 3: [Nombre del Rol] |
|----------------|-----------------------------------|-----------------------------------|-----------------------------------|
| **Descripción** | [Breve descripción del rol] | [Breve descripción del rol] | [Breve descripción del rol] |
| **Responsabilidades** | [Qué hace en el sistema] | [Qué hace en el sistema] | [Qué hace en el sistema] |
| **Nivel Técnico** | Alto/Medio/Bajo | Alto/Medio/Bajo | Alto/Medio/Bajo |
| **Experiencia en el Dominio** | Experto/Intermedio/Novato | Experto/Intermedio/Novato | Experto/Intermedio/Novato |
| **Frecuencia de Uso** | Diaria/Semanal/Ocasional | Diaria/Semanal/Ocasional | Diaria/Semanal/Ocasional |
| **Funciones Principales** | [Listar 3-5 funciones] | [Listar 3-5 funciones] | [Listar 3-5 funciones] |
| **Necesidades Especiales** | [Si aplica] | [Si aplica] | [Si aplica] |

<!-- 
EJEMPLO ACADÉMICO DETALLADO:

**TIPO DE USUARIO 1: Bibliotecario**

- **Descripción**: Personal de la biblioteca encargado de las operaciones diarias 
  de préstamos, devoluciones, y atención al público.

- **Responsabilidades en el Sistema**:
  - Registrar préstamos y devoluciones de materiales
  - Registrar nuevos usuarios
  - Procesar pagos de multas
  - Atender consultas sobre disponibilidad de materiales
  - Generar reportes básicos de operaciones diarias

- **Nivel de Experiencia Técnica**: Medio. Tienen conocimientos básicos de informática 
  pero no son expertos técnicos. Pueden manejar aplicaciones de oficina estándar.

- **Experiencia en el Dominio**: Alta. Conocen perfectamente los procesos bibliotecarios 
  y la organización de materiales. Promedio de 5+ años trabajando en bibliotecas.

- **Frecuencia de Uso**: Diaria, durante toda su jornada laboral (8 horas al día).

- **Funciones Principales que Utilizará**:
  - Módulo de préstamos y devoluciones
  - Módulo de gestión de usuarios
  - Búsqueda de materiales en catálogo
  - Gestión de reservas
  - Procesamiento de multas

- **Necesidades Especiales**: 
  - Interfaz intuitiva que permita realizar operaciones rápidamente
  - Capacidad de trabajo con interrupciones frecuentes (atención al público)
  - Acceso rápido a ayuda contextual

**TIPO DE USUARIO 2: Administrador del Sistema**

- **Descripción**: Personal técnico o jefe de biblioteca responsable de la configuración 
  y administración del sistema BiblioTech.

- **Responsabilidades en el Sistema**:
  - Configurar parámetros operativos del sistema
  - Gestionar cuentas de bibliotecarios
  - Mantener el catálogo (altas, bajas, modificaciones masivas)
  - Generar reportes estadísticos y ejecutivos
  - Realizar respaldos del sistema
  - Auditar operaciones del sistema

- **Nivel de Experiencia Técnica**: Alto. Tiene conocimientos avanzados de sistemas 
  informáticos y administración de aplicaciones.

- **Experiencia en el Dominio**: Alta. Comprende todos los procesos bibliotecarios 
  desde una perspectiva gerencial.

- **Frecuencia de Uso**: Semanal para tareas de configuración y mantenimiento, 
  diaria para consulta de reportes y auditoría.

- **Funciones Principales que Utilizará**:
  - Panel de administración completo
  - Configuración de parámetros del sistema
  - Gestión de usuarios del sistema
  - Generación de reportes avanzados
  - Herramientas de respaldo y restauración
  - Visualización de logs de auditoría

- **Necesidades Especiales**: 
  - Acceso a funciones avanzadas no disponibles para usuarios regulares
  - Herramientas de diagnóstico y monitoreo del sistema
  - Capacidad de realizar operaciones masivas sobre datos

**TIPO DE USUARIO 3: Usuario/Cliente de la Biblioteca**

- **Descripción**: Ciudadanos registrados en la biblioteca que consultan el catálogo 
  y su información personal desde Internet.

- **Responsabilidades en el Sistema**:
  - Buscar materiales disponibles en la biblioteca
  - Consultar sus préstamos activos
  - Renovar préstamos (si es posible)
  - Hacer reservas de materiales
  - Consultar su historial de préstamos

- **Nivel de Experiencia Técnica**: Bajo a Medio. Varían desde personas con 
  conocimientos básicos hasta usuarios experimentados de Internet.

- **Experiencia en el Dominio**: Baja a Media. Algunos son usuarios frecuentes 
  de bibliotecas, otros son nuevos usuarios.

- **Frecuencia de Uso**: Variable. Desde uso semanal hasta esporádico (mensual 
  o menos frecuente).

- **Funciones Principales que Utilizará**:
  - Búsqueda de materiales en catálogo
  - Consulta de cuenta personal
  - Sistema de reservas
  - Renovación de préstamos

- **Necesidades Especiales**: 
  - Interfaz muy intuitiva, sin necesidad de capacitación
  - Accesibilidad (cumplimiento WCAG 2.1 nivel AA)
  - Disponible 24/7 desde cualquier dispositivo (responsive)
  - Multiidioma (si aplica)
  - Protección de datos personales
-->

[Complete esta subsección describiendo todos los tipos de usuarios de su sistema]

<br>

### 2.4 Restricciones

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Documentar todas las limitaciones o restricciones que afectarán el diseño e 
implementación del sistema. Estas restricciones pueden ser técnicas, de negocio,
regulatorias, o de cualquier otra naturaleza.

IMPORTANCIA:
Las restricciones son CRÍTICAS porque:
- Limitan las opciones de diseño e implementación
- Pueden afectar costos y cronogramas
- Deben ser conocidas desde el inicio del proyecto
- Son generalmente NO NEGOCIABLES

TIPOS COMUNES DE RESTRICCIONES:

1. Restricciones Regulatorias/Legales
2. Restricciones de Hardware
3. Restricciones de Software
4. Restricciones de Interfaces con Aplicaciones
5. Restricciones Paralelas (procesos concurrentes)
6. Restricciones de Auditoría
7. Restricciones de Lenguaje de Programación
8. Restricciones de Bases de Datos
9. Restricciones de Estándares
10. Restricciones de Presupuesto y Recursos

FORMATO SUGERIDO:
Organice por categorías para mejor comprensión.

EJEMPLO ACADÉMICO:

**Restricciones Regulatorias y Legales:**

- El sistema DEBE cumplir con la Ley de Protección de Datos Personales vigente 
  en el país, garantizando la confidencialidad de información de usuarios.
  
- Toda eliminación de datos personales debe ser irreversible y cumplir con el 
  "derecho al olvido" establecido en la legislación.

- El sistema debe mantener registros de auditoría de acceso a datos personales 
  por un período mínimo de 2 años.

**Restricciones Tecnológicas:**

- El sistema DEBE ejecutarse en los servidores existentes de la municipalidad 
  (Linux Ubuntu Server 22.04 LTS, 8GB RAM, 500GB disco).

- El sistema DEBE ser compatible con los navegadores web utilizados en la biblioteca: 
  Chrome 90+, Firefox 88+, Edge 90+.

- El sistema DEBE integrarse con el lector de código de barras marca Zebra modelo 
  DS2208 ya adquirido por la biblioteca.

**Restricciones de Implementación:**

- El desarrollo DEBE realizarse utilizando tecnologías open source para evitar 
  costos de licenciamiento.

- El sistema DEBE estar implementado y en producción en un plazo máximo de 6 meses.

- El equipo de desarrollo está limitado a 4 personas (2 desarrolladores, 1 analista, 
  1 tester).

**Restricciones de Interfaz:**

- El sistema DEBE integrarse con la API REST del Sistema Municipal de Identificación 
  de Ciudadanos (versión 2.1) para validación de datos de usuarios.

- El sistema DEBE utilizar el servidor SMTP institucional (mail.municipalidad.gob) 
  para envío de correos electrónicos.

**Restricciones Operacionales:**

- El sistema DEBE funcionar con la conexión a Internet existente (10 Mbps simétrica), 
  la cual NO se puede mejorar.

- La base de datos DEBE ser PostgreSQL versión 13 o superior, ya que es el estándar 
  de la municipalidad.

- El sistema NO PUEDE requerir instalación de software adicional en las computadoras 
  de los bibliotecarios (debe ser 100% web).

**Restricciones de Migración de Datos:**

- El sistema DEBE permitir importar datos del sistema Excel actual, incluyendo 
  un mínimo de 15,000 registros de usuarios y 25,000 materiales bibliográficos.

- La migración de datos NO puede causar interrupción del servicio de la biblioteca 
  por más de 4 horas.

**Restricciones de Capacitación:**

- La capacitación del personal DEBE completarse en máximo 16 horas totales 
  (2 días de 8 horas).

- Los materiales de capacitación DEBEN estar en español.

**Restricciones Presupuestarias:**

- El presupuesto total del proyecto NO puede exceder $25,000 USD.

- NO se puede contratar más personal; el trabajo debe realizarse con el equipo 
  disponible.

NOTA IMPORTANTE:
Sea específico. NO escriba "el sistema debe ser rápido" (eso es un requisito de 
rendimiento). Escriba restricciones concretas como "el sistema debe ejecutarse 
en servidores con máximo 8GB de RAM".
-->

[Complete esta subsección documentando todas las restricciones aplicables a su proyecto]

<br>

### 2.5 Suposiciones y dependencias

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Documentar todas las suposiciones (assumptions) hechas durante la especificación
de requisitos y las dependencias externas que podrían afectar el desarrollo o
funcionamiento del sistema.

IMPORTANCIA CRÍTICA:
- Las suposiciones son premisas que SE ASUMEN CIERTAS pero que podrían cambiar
- Si una suposición resulta incorrecta, los requisitos pueden necesitar revisión
- Las dependencias son factores externos fuera del control del equipo
- Identificarlas permite gestión de riesgos proactiva

DIFERENCIA CLAVE:
- SUPOSICIÓN: "Se asume que el usuario tiene conexión a Internet"
- DEPENDENCIA: "El sistema depende de la disponibilidad de la API externa X"

CATEGORÍAS COMUNES:

1. Suposiciones sobre Usuarios
2. Suposiciones sobre el Entorno de Operación
3. Suposiciones sobre Datos
4. Dependencias de Sistemas Externos
5. Dependencias de Terceros
6. Dependencias Tecnológicas

FORMATO SUGERIDO:
Liste cada suposición/dependencia numerada para fácil referencia.

EJEMPLO ACADÉMICO:

**Suposiciones:**

1. **Conectividad**: Se asume que la biblioteca cuenta con conexión a Internet 
  estable y continua durante el horario de operación. Si la conexión falla, 
  algunas funcionalidades no estarán disponibles.

2. **Hardware**: Se asume que las computadoras de las estaciones de trabajo de 
  bibliotecarios cumplen con los requisitos mínimos: procesador dual-core 2GHz, 
  4GB RAM, navegador web actualizado.

3. **Conocimientos del Personal**: Se asume que el personal de biblioteca tiene 
  conocimientos básicos de informática (uso de navegador web, mouse, teclado) 
  y que recibirá capacitación específica sobre BiblioTech antes del lanzamiento.

4. **Proceso de Negocio**: Se asume que los procesos bibliotecarios actuales 
  (políticas de préstamo, cálculo de multas, categorización de materiales) 
  continuarán siendo válidos en el sistema digitalizado.

5. **Volumen de Datos Inicial**: Se asume que el catálogo inicial contiene 
  aproximadamente 25,000 materiales bibliográficos y 15,000 usuarios registrados, 
  con un crecimiento anual estimado del 10%.

6. **Usuarios Finales**: Se asume que los usuarios de la biblioteca que accedan 
  al catálogo en línea tienen conocimientos básicos de navegación web y acceso 
  a un dispositivo con navegador (computadora, tablet, smartphone).

7. **Datos de Migración**: Se asume que los datos en Excel del sistema actual 
  están razonablemente limpios y estructurados, y que cualquier inconsistencia 
  será resuelta antes de la migración.

8. **Apoyo Institucional**: Se asume que la dirección de la biblioteca y la 
  municipalidad proporcionarán el apoyo necesario para la adopción del sistema, 
  incluyendo tiempo para capacitación del personal.

9. **Mantenimiento**: Se asume que la municipalidad proporcionará soporte técnico 
  continuo para el servidor y la infraestructura de red.

**Dependencias:**

1. **Sistema Municipal de Identificación (SMI)**: El módulo de registro de usuarios 
  DEPENDE de la disponibilidad y correcto funcionamiento de la API del SMI para 
  validar identidad de ciudadanos. Si la API no está disponible, el registro de 
  nuevos usuarios se verá afectado.

2. **Servicio de Correo Electrónico**: El módulo de notificaciones DEPENDE del 
  servidor SMTP institucional (mail.municipalidad.gob). Si el servicio de correo 
  falla, las notificaciones automáticas no se enviarán.

3. **Proveedor de Hosting**: El sistema DEPENDE de la infraestructura de servidores 
  de la municipalidad. Cualquier mantenimiento, actualización o problema en esta 
  infraestructura afectará la disponibilidad de BiblioTech.

4. **Código de Barras**: El sistema DEPENDE del estándar ISBN (International Standard 
  Book Number) para identificación de libros. Materiales sin ISBN requerirán 
  códigos alternativos generados internamente.

5. **Navegadores Web**: El sistema DEPENDE de que los navegadores web mantengan 
  compatibilidad con los estándares HTML5, CSS3 y JavaScript ES6. Cambios 
  significativos en navegadores podrían requerir actualizaciones del sistema.

6. **Base de Datos PostgreSQL**: El sistema DEPENDE de PostgreSQL y sus 
  actualizaciones de seguridad. Migraciones a nuevas versiones mayores de 
  PostgreSQL requerirán pruebas exhaustivas.

7. **Lectores de Código de Barras**: El sistema DEPENDE de los lectores de código 
  de barras Zebra DS2208. Si se reemplazan por otro modelo, puede requerirse 
  adaptación del sistema.

8. **Proveedor de Carnes de Biblioteca**: La funcionalidad de escaneado de carnets 
  DEPENDE de que el proveedor de carnets imprima códigos de barras legibles según 
  el estándar Code 39 o similar.

9. **Equipo de Desarrollo**: El cronograma del proyecto DEPENDE de la disponibilidad 
  continua del equipo de desarrollo asignado. Cambios en el equipo podrían afectar 
  plazos de entrega.

10. **Aprobaciones de la Municipalidad**: Ciertas decisiones de diseño y configuración 
  DEPENDEN de aprobaciones del departamento de sistemas de la municipalidad, lo 
  que podría introducir retrasos si las aprobaciones se demoran.

**Impacto de Cambios:**

Si cualquiera de las suposiciones anteriores resulta incorrecta o las dependencias 
externas fallan, se requerirá:
- Revisión de requisitos afectados
- Evaluación de impacto en cronograma y presupuesto
- Posible renegociación de alcance del proyecto

El equipo de proyecto debe monitorear continuamente la validez de estas suposiciones 
y el estado de las dependencias, reportando cualquier cambio significativo a los 
stakeholders.

NOTA PARA ESTUDIANTES:
En proyectos reales, este análisis es crítico para la gestión de riesgos. Una 
suposición incorrecta puede hacer que todo un proyecto fracase. Sea honesto y 
exhaustivo al documentar suposiciones y dependencias.
-->

[Complete esta subsección documentando todas las suposiciones y dependencias de su proyecto]

<br>

### 2.6 Requisitos futuros

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Documentar funcionalidades y mejoras que NO estarán en la versión actual del 
sistema, pero que se han identificado como valiosas para futuras versiones.

IMPORTANCIA:
- Gestiona expectativas de stakeholders (deja claro qué NO estará en esta versión)
- Proporciona una hoja de ruta de evolución del producto
- Ayuda en la planificación arquitectónica (diseñar pensando en extensibilidad)
- Documenta ideas valiosas que surgieron pero están fuera del alcance actual

CATEGORÍAS SUGERIDAS:
1. Funcionalidades nuevas
2. Integraciones adicionales
3. Mejoras de rendimiento
4. Mejoras de usabilidad
5. Soporte de nuevas plataformas

FORMATO:
Liste de manera concisa. NO desarrolle requisitos completos aquí.

PRINCIPIO IMPORTANTE:
Estos requisitos fueron deliberadamente EXCLUIDOS del alcance actual por razones
de tiempo, presupuesto, o prioridad. NO son errores ni omisiones.

EJEMPLO ACADÉMICO:

**Funcionalidades Futuras Planificadas:**

**Versión 2.0 (Estimada para 12 meses después del lanzamiento):**

1. **Aplicación Móvil Nativa**: Desarrollo de aplicaciones nativas para iOS y 
  Android que permitan a los usuarios acceder al catálogo, renovar préstamos, 
  y recibir notificaciones push.

2. **Sistema de Recomendaciones**: Implementar un sistema de recomendaciones 
  inteligente que sugiera materiales basándose en el historial de préstamos 
  y preferencias del usuario (similar a Amazon o Netflix).

3. **Biblioteca Digital**: Incorporar módulo para gestión y préstamo de libros 
  electrónicos (e-books) y audiolibros, con integración de DRM (Digital Rights 
  Management).

4. **Sistema de Comentarios y Reseñas**: Permitir a los usuarios calificar 
  materiales y escribir reseñas, creando una comunidad alrededor de la biblioteca.

5. **Integración con Redes Sociales**: Permitir a usuarios compartir sus lecturas 
  y listas de deseos en redes sociales (Facebook, Twitter, Instagram).

**Versión 2.5 (Estimada para 18 meses):**

6. **Préstamo Interbibliotecario**: Integración con otras bibliotecas municipales 
  para permitir préstamos de materiales entre bibliotecas de la red.

7. **Sistema de Eventos**: Módulo para gestión y difusión de eventos de la 
  biblioteca (clubs de lectura, presentaciones de libros, talleres).

8. **Analítica Avanzada**: Dashboard ejecutivo con análisis predictivo de demanda, 
  recomendaciones de adquisiciones basadas en IA, y análisis de tendencias.

9. **Portal del Autor**: Permitir a autores locales publicar información sobre 
  sus obras, calendario de presentaciones, y conectar con lectores.

10. **Accesibilidad Mejorada**: Soporte completo para lectores de pantalla, modo 
  alto contraste, tamaños de fuente ajustables, y soporte para materiales en 
  Braille.

**Integraciones Futuras:**

11. **Sistema de Pago en Línea**: Integración con pasarelas de pago (PayPal, 
  tarjetas de crédito) para pago de multas y cuotas de membresía en línea.

12. **API Pública**: Exposición de API REST pública (con autenticación) para que 
  desarrolladores externos puedan crear aplicaciones que consuman datos de la 
  biblioteca.

13. **Integración con Servicios Editoriales**: Conexión con bases de datos de 
  editoriales para obtener automáticamente metadatos, portadas, y reseñas de 
  nuevos libros.

**Mejoras Tecnológicas Consideradas:**

14. **Modo Offline**: Permitir operaciones básicas de préstamo/devolución en modo 
  offline cuando no hay conexión a Internet, con sincronización automática 
  posterior.

15. **Reconocimiento por Voz**: Búsqueda de materiales mediante comandos de voz 
  (integración con Alexa, Google Assistant).

16. **Chatbot de Atención**: Asistente virtual con IA que responda preguntas 
  frecuentes de usuarios 24/7.

17. **Realidad Aumentada**: Aplicación AR que ayude a usuarios a localizar 
  físicamente materiales en los estantes de la biblioteca.

**Nota Importante:**
Estos requisitos futuros son tentativos y están sujetos a disponibilidad de 
presupuesto, cambios en prioridades del negocio, y evolución tecnológica. No 
constituyen compromisos contractuales.

CONSIDERACIÓN ARQUITECTÓNICA:
Aunque estas funcionalidades no se implementarán en la versión 1.0, la arquitectura 
del sistema debe diseñarse de manera que permita su incorporación futura sin 
requerir rediseños mayores. Esto implica:
- Diseño modular
- API bien definidas entre componentes
- Base de datos extensible
- Separación clara de responsabilidades

PROCESO DE PRIORIZACIÓN:
Los requisitos futuros serán revisados y priorizados en cada ciclo de planificación, 
basándose en:
- Feedback de usuarios reales después del lanzamiento
- Cambios en el contexto de negocio
- Disponibilidad de recursos
- ROI (Retorno de Inversión) estimado
- Dependencias técnicas
-->

[Complete esta subsección con los requisitos futuros identificados para su proyecto]

<br>

---

## 3 REQUISITOS ESPECÍFICOS

# 3. REQUISITOS FUNCIONALES

## 3.1 Requisitos Funcionales

### 3.1.1 Módulo de Control de Aforo
| Campo | Descripción |
|--------|--------------|
| **ID** | RF-001 |
| **Nombre** | Control de aforo en tiempo real |
| **Descripción** | El sistema FitCampus debe monitorear automáticamente el número de usuarios dentro del gimnasio, actualizando el aforo en tiempo real. Cuando se alcance el límite máximo permitido, el sistema notificará al administrador, bloqueará nuevos accesos y permitirá la creación de una fila virtual. |
| **Prioridad** | Alta |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento funcional derivado del sistema automático FitCampus |
| **Criterios de aceptación** | 1. El sistema registra entrada y salida de usuarios.<br>2. Se actualiza el contador de aforo en tiempo real.<br>3. Se bloquean nuevos accesos al alcanzar el límite.<br>4. Se envía una notificación al administrador.<br>5. Se gestiona una fila virtual de espera. |
| **Dependencias** | RF-002 (Registro de entradas y salidas) |
| **Comentarios** | Este módulo funciona de manera automática y debe integrarse con los sensores de acceso del gimnasio. |

---

### 3.1.2 Módulo de Registro de Entradas y Salidas
| Campo | Descripción |
|--------|--------------|
| **ID** | RF-002 |
| **Nombre** | Registro automático de entradas y salidas |
| **Descripción** | El sistema debe registrar la entrada y salida de cada usuario mediante sensores o lectores de identificación. Estos registros alimentan el conteo de aforo actual y se almacenan en la base de datos para control y reportes. |
| **Prioridad** | Alta |
| **Estabilidad** | Media |
| **Fuente** | Requerimiento del área de control y acceso del gimnasio |
| **Criterios de aceptación** | 1. Se registra la entrada del usuario al acceder.<br>2. Se registra la salida al abandonar el recinto.<br>3. Los datos se actualizan automáticamente en el módulo de aforo.<br>4. Los registros se almacenan en la base de datos.<br>5. Se garantiza la integridad de la información capturada. |
| **Dependencias** | RF-001 (Control de aforo) |
| **Comentarios** | Estos datos pueden usarse para reportes de asistencia y estadísticas de uso. |

---

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

```mermaid
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


**Diagrama de Casos de Uso:**









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
