# Checklist de Revisión

# Protocolo de Code Review Forense — Código Generado por IA

INSTRUCCIÓN DE USO: Aplica este protocolo ANTES de hacer commit.

-El rol aquí es de auditor escéptico, no de ejecutor.
-Si el código compila pero no pasa este protocolo, NO está listo.
-La IA implementa. El humano audita.

## 1. Alucinaciones de librerías

### Pregunta clave

¿Ese import realmente existe?

La IA puede inventar:

- librerías
- funciones
- APIs
- métodos
- Versiones no usadas en el proyecto

**Que revisar:**

- Documentación oficial de cada librería usada
- Existencia real del paquete en el ecosistema
- Compatibilidad con la versión del proyecto
- Funciones que parecen reales pero no están en la versión actual

### Checklist

- [ ] Los imports existen y son reales
- [ ] Las funciones usadas existen en la versión correcta
- [ ] La API corresponde a la versión actual del paquete
- [ ] No hay dependencias inventadas o innecesarias

## 2. Lógica de negocio sutil

### Pregunta clave

¿La lógica es realmente correcta en TODOS los escenarios?
NOTA: Los errores más peligrosos no rompen el código, se esconden en cálculos sutiles y casos borde que la IA no contempló.

**Errores comunes generados por IA:**

- Uso de float para dinero (siempre usar Decimal)
- Redondeos incorrectos
- Manejo incorrecto de fechas y zonas horarias
- Condiciones incompletas o lógica invertida
- Casos borde ignorados (monto 0, lista vacía, valor nulo)

### Checklist

- [ ] Los cálculos son correctos y verificados manualmente
- [ ] No se usa float para valores monetarios
- [ ] El manejo de fechas es consistente
- [ ] Los edge cases están contemplados y probados
- [ ] Las condiciones límite fueron verificada

## 3. Seguridad

### Pregunta clave

¿El código introduce riesgos de seguridad?

La IA puede generar código funcional pero inseguro.
NOTA:  Un código que "funciona" no significa que sea seguro para producción.

**Revisar:**

- Validación de todos los inputs del usuario
- Riesgo de inyección (SQL, comandos, scripts)
- Credenciales o secrets hardcodeados en el código
- Endpoints sin autenticación o autorización
- Logs que expongan datos sensibles
- Manejo incorrecto de datos personales

### Checklist

- [ ] Todos los inputs están validados antes de procesarse
- [ ] No hay riesgo de inyección SQL o de comandos
- [ ] No se exponen credenciales ni API keys en el código
- [ ] No se filtran datos sensibles en logs
- [ ] Los endpoints tienen autenticación donde corresponde


## 4. Context window (Pérdida de contexto)

### Pregunta clave

¿La IA olvidó algo del brief?

NOTA: Cuando el contexto es largo, la IA puede ignorar constraints, decisiones
arquitectónicas o requisitos definidos al inicio. Esto ocurre porque la
ventana de contexto tiene límites.

Síntomas comunes:

- Constraints del brief ignorados
- Arquitectura cambiada sin justificación
- Dependencias no aprobadas añadidas
- Definition of Done incumplida
- Tipos o interfaces modificados sin avisar

### Checklist

- [ ] El código respeta todos los constraints del brief
- [ ] La arquitectura acordada fue respetada
- [ ] No se agregaron dependencias no aprobadas
- [ ] Se cumple la Definition of Done definida
- [ ] Los tipos e interfaces son consistentes con el plan

---

## 5. Punto personalizado del proyecto

Pregunta clave: ¿El código cumple los estándares específicos de este stack?
Este punto depende de tu stack o arquitectura.

**Ejemplos comunes:**

- ¿Los tests nuevos realmente ejecutan el código nuevo?
- ¿El linter del proyecto pasa sin errores ni warnings?
- ¿Los logs no exponen datos sensibles?
- ¿La performance es aceptable bajo carga real?
- ¿El código es compatible con la arquitectura del proyecto?
- ¿Se documentaron las funciones públicas con docstrings?

Mi criterio personalizado: [Define aquí el tuyo]

### Checklist

- [ ] Tests cubren el código nuevo
- [ ] Logs no exponen datos sensibles
- [ ] Performance es aceptable
- [ ] Métricas funcionan correctamente

## Resultado del Review

### Checklist
 1. Alucinaciones de librerías 
 2. Lógica de negocio
 3. Seguridad 
 4. Context window 

| 5. Decisión final:

- [ ] El código pasa todos los puntos — listo para commit
- [ ] Correcciones menores aplicadas — listo para commit
- [ ] Correcciones críticas pendientes — NO hacer commit aún

**Reviewer:** ____________________  
**Fecha:** ____________________
**Tarea / Brief asociado:** ____________________
