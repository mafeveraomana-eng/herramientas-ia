# Technical Brief - [Nombre del Proyecto / Funcionalidad]
> INSTRUCCIÓN DE USO: Completa todas las secciones antes de pedirle código a la IA. Una vez completo, comparte este brief y pregúntale:
"Critica este brief: ¿qué falta, qué está ambiguo, qué restricción añadirías?" Corrige primero. Implementa después.

## 1. Título de la tarea

Nombre claro y específico de la funcionalidad o servicio a implementar.
NOTA: El título debe contener intención arquitectónica, no solo el tema.
Ejemplo:
-Mal: "Calcular impuestos"
-Bien: "Servicio desacoplado de cálculo de impuestos por país"

[Tu título aquí]

---

## 2. Contexto

Describe el problema actual y por qué se necesita esta solución.

NOTA: Sin este bloque, la IA rellena huecos con suposiciones incorrectas.

Responde estas tres preguntas:

- Cómo funciona el sistema actualmente
- Qué problema existe (acoplamiento, deuda técnica, escalabilidad, etc.)
- Qué se busca lograr con esta implementación

Ejemplo de estructura:

"El sistema actual ____. Esto genera problemas como ____.

El objetivo de esta tarea es ____ para mejorar ____."

[Tu contexto aquí]

---

## 3. Requerimientos técnicos

### Lenguaje / Stack

- Lenguaje:
- Versión mínima:
- Framework (si aplica):
- Base de datos (si aplica):

Ejemplo:

- Python 3.9+
- FastAPI
- PostgreSQL

---

### Arquitectura

Describe patrones o principios a usar.

Ejemplo:

- Clean Architecture
- Strategy Pattern
- Dependency Injection
- Stateless service

[Tu arquitectura aquí]

---

### Usuarios y roles

Define quién usa el sistema y qué puede hacer cada uno.

| Rol |  Permisos / Acciones  |

|-----|-----------------------|

| [Rol 1] | [Qué puede hacer] |

| [Rol 2] | [Qué puede hacer] |

---

### Input esperado

Define los datos de entrada.

Ejemplo:

```python
InputObject
- field_1: type
- field_2: type
```
### Output esperado

Define los datos de salida.

```
OutputObject:
  - field_1: type
  - field_2: type
```

### 4. Constraints (Restricciones)
NOTA: Todo lo que la IA NO debe hacer. Si esta sección falta, la IA improvisa.
- No usar librerías externas salvo las aprobadas por el equipo.
- Implementar type hints en todo el código.
- Seguir principios SOLID y buenas prácticas del lenguaje.
- Separar claramente el dominio, estrategias y servicios principales.
- Alcance del MVP: [define qué queda FUERA de esta versión]

[Agrega tus restricciones específicas aquí]

---

### 5. Definition of Done (DoD)
NOTA: Criterios concretos y verificables. No "que funcione", sino evidencia real.
La IA trabaja mejor cuando el éxito está definido antes de escribir código.

El trabajo se considera terminado cuando:

- El código pasa linters y convenciones de estilo adoptadas por el equipo (ej: flake8, black).
- La cobertura de tests unitarios es al menos 90%.
- El usuario puede completar el flujo [X] sin errores.

[Agrega tus criterios específicos aquí]

---

> RECUERDA: Este brief es el contrato de la tarea.
> Brief de calidad = Código de calidad.
> Primero el brief → luego la crítica → luego el plan → luego el código.
