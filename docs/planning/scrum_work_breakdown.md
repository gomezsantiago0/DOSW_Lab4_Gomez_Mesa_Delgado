# 📄 Planeación del Sistema

## Desglose de trabajo: Épicas, Historias de Usuario y Tareas

La implementación de los requerimientos identificados de Bankify se desglosa de la siguiente manera:

### 1. Épica:

| Campo | Descripción |
|------|-------------|
| **ID** | EP-01 |
| **Título** | Creación y gestión de torneos |
| **Descripción** | Bankify necesita permitir que los organizadores puedan crear nuevos torneos directamente desde la plataforma, definiendo la fecha del torneo y el valor de inscripción, para ampliar la oferta de torneos disponibles, agilizar la operación (evitando procesos manuales) y aumentar la captación de inscripciones y, con ello, los ingresos asociados. |
| **Stakeholder** | Área de Producto / Operaciones de Torneos de Bankify (responsable de administrar la oferta de torneos en la plataforma). |

### 2. Historias de usuario:

| Campo | Descripción |
|------|-------------|
| **ID** | HU-01 |
| **Título** | Iniciar creación de torneo desde el listado |
| **Descripción** | Como organizador quiero acceder al formulario de creación de torneo desde la pantalla de Listado de Torneos para poder iniciar el registro de un nuevo torneo. |
| **Prioridad** | **HU-01 (Alta):** Es el punto de entrada obligatorio al flujo. Sin esta 
  funcionalidad, ningún organizador puede llegar al formulario de creación 
  — bloquea completamente el resto de la épica.
 |
| **Estimación** | *Puntos de historia* |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-02 |
| **Título** | Completar y enviar el formulario de creación de torneo |
| **Descripción** | Como organizador quiero ingresar la fecha del torneo y el valor de inscripción en el Formulario Crear Torneo para registrar los datos necesarios y que, si son válidos, el torneo se cree y me lleve a la pantalla de Confirmación. |
| **Prioridad** | **HU-02 (Alta):** Es el corazón funcional de la épica: aquí se valida y 
  persiste la información real del torneo (fecha, valor de inscripción) 
  según las reglas de negocio. Sin esta historia no existe "creación de 
  torneos" como funcionalidad |
| **Estimación** | *Puntos de historia* |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-03 |
| **Título** | Cancelar la creación de un torneo |
| **Descripción** | Como organizador quiero poder cancelar el proceso desde el Formulario Crear Torneo para regresar al Listado de Torneos sin guardar ningún dato si decido no continuar. |
| **Prioridad** | **HU-03 (Baja):** Es una mejora de experiencia de usuario, pero no 
  bloquea el objetivo de negocio. El sistema funciona sin este flujo 
  explícito para el MVP.|
| **Estimación** | *Puntos de historia* |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-04 |
| **Título** | Ver confirmación de creación exitosa y volver al listado |
| **Descripción** | Como organizador quiero ver un mensaje de confirmación cuando el torneo se cree exitosamente para tener certeza de que quedó registrado, y poder volver al Listado de Torneos desde ahí. |
| **Prioridad** | **HU-04 (Media):** Da certeza al usuario de que el registro fue exitoso, 
  importante para la confianza en el sistema, pero técnicamente el torneo 
  ya quedó creado en HU-02 aunque no se muestre confirmación. |
| **Estimación** | *Puntos de historia* |

### 3. Tareas:

| Campo | Descripción |
|------|-------------|
| **ID** | TR-01 |
| **Título** | Diseñar botón "Crear Torneo" en el Listado de Torneos |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Diseñar y ubicar en la UI del Listado de Torneos el botón "Crear Torneo" con estilos consistentes con la plataforma. |
| **Tareas requisito** | Ninguna |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-02 |
| **Título** | Implementar navegación hacia el Formulario Crear Torneo |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Implementar la lógica de navegación para que, al hacer clic en "Crear Torneo", el usuario sea redirigido a la pantalla Formulario Crear Torneo. |
| **Tareas requisito** | TR-01 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-03 |
| **Título** | Probar navegación Listado a Formulario |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Ejecutar pruebas (QA/unitarias) que validen que el botón "Crear Torneo" redirige correctamente al formulario en todos los casos. |
| **Tareas requisito** | TR-02 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-04 |
| **Título** | Diseñar UI del Formulario Crear Torneo |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Diseñar la interfaz del formulario con los campos "fecha del torneo" y "valor de inscripción", junto con los botones "Crear Torneo" y "Cancelar". |
| **Tareas requisito** | TR-02 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-05 |
| **Título** | Implementar validaciones de los campos del formulario |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Implementar validaciones (fecha válida/futura, valor de inscripción numérico y positivo) mostrando mensajes de error cuando los datos no sean válidos. |
| **Tareas requisito** | TR-04 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-06 |
| **Título** | Implementar envío del formulario y creación del torneo |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Implementar la llamada al backend/API para crear el torneo con los datos ingresados y, si la respuesta es exitosa, redirigir a la pantalla de Confirmación. |
| **Tareas requisito** | TR-05 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-07 |
| **Título** | Agregar botón "Cancelar" en el Formulario Crear Torneo |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Diseñar y ubicar el botón "Cancelar" en el Formulario Crear Torneo. |
| **Tareas requisito** | TR-04 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-08 |
| **Título** | Implementar navegación de "Cancelar" hacia el Listado |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Implementar la lógica para que, al hacer clic en "Cancelar", el usuario sea redirigido al Listado de Torneos sin guardar cambios. |
| **Tareas requisito** | TR-07 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-09 |
| **Título** | Probar que "Cancelar" no persiste datos |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Ejecutar pruebas que verifiquen que al cancelar no se crea ni guarda ningún torneo con datos parciales. |
| **Tareas requisito** | TR-08 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-10 |
| **Título** | Diseñar pantalla de Confirmación |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Diseñar la UI de la pantalla de Confirmación con el mensaje de éxito y el botón "Volver". |
| **Tareas requisito** | TR-06 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-11 |
| **Título** | Implementar navegación Formulario a Confirmación |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Implementar la redirección automática desde el Formulario hacia la Confirmación cuando el torneo se cree exitosamente. |
| **Tareas requisito** | TR-06, TR-10 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-12 |
| **Título** | Implementar botón "Volver" en Confirmación |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Implementar la lógica del botón "Volver" para que redirija al usuario de vuelta al Listado de Torneos. |
| **Tareas requisito** | TR-10 |