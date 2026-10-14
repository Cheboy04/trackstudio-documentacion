# Reporte de avance — Track Studio

**Fecha de corte:** 2026-10-07 · **Semana:** 3 de 12 · **Sprint activo:** TS Sprint 2 (semanas 3–4)
**Fuente:** Jira (proyecto `TS`, 60 issues), `HANDOFF_v16.md` y el dato que dio el equipo sobre `TS-49`.

## 1. Resultado

| Indicador | Valor |
|---|---|
| Avance esperado (3 semanas × 9 %) | **27,0 %** |
| Avance real ponderado | **23,9 %** |
| Desviación | **−3,1 puntos** (unos 2 días de trabajo de retraso) |
| Ritmo real | 8,0 % por semana (meta: 9 %) |
| Proyección al ritmo actual | 96 % al cierre de la semana 12 |

```
Esperado  ███████████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  27,0 %
Real      ████████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  23,9 %
```

El proyecto va **ligeramente atrasado, pero se puede recuperar**. Cerrar el Sprint 2 completo sube el avance al 34,3 %. La meta de la semana 4 es 36 %, así que además hay que recuperar unos 2 pts de deuda (por ejemplo, cerrar `TS-53` y avanzar `TS-46`).

## 2. Método de cálculo

- **Alcance:** 49 issues (28 historias y 21 tareas). No se cuentan las 11 épicas ni la subtarea `TS-50`, que forma parte de `TS-42`.
- **Peso:** los *story points* de Jira. Las tareas no tienen estimación, así que cada una vale 1 punto. Total: **113 puntos** (92 de historias y 21 de tareas).
- **Avance por estado:**

| Estado en Jira | Avance |
|---|---|
| Listo | 100 % |
| Pendiente de verificación | 90 % |
| En curso | 50 % (salvo los ajustes que siguen) |
| Por hacer | 0 % |

- **Ajustes manuales:**
  - **`TS-49` (ERD), 30 %:** lo indicó el equipo. Jira lo marca como **Listo**, así que hay que corregir el estado allí o confirmar cuál de los dos datos es el correcto.
  - **`TS-16` (HU-05), 90 %:** está implementada en las dos capas y probada en local. Falta el PR hacia `develop` y la verificación en staging.
  - **`TS-19` (HU-08), 10 %:** Jira la marca **En curso**, pero todavía no tiene spec (handoff v16 §7).
  - **`TS-46` (tesis, desarrollo), 25 %:** la evidencia SCRUM se escribe por sprint y lleva 1,5 de 6.
  - **`TS-53` (evidencia del S1), 50 %.**

Meta: 9 % por semana × 12 semanas (6 sprints de 2 semanas) = 108 %. Al ritmo planificado, el proyecto llega al 100 % a mitad de la semana 12 y le queda medio sprint de holgura.

## 3. Avance por bloque

| Bloque | Puntos | Ganados | Avance |
|---|---|---|---|
| Historias de usuario (HU-01 a HU-28) | 92 | 19,0 | 20,7 % |
| Tareas (infraestructura, ERD, tesis, deuda técnica) | 21 | 8,05 | 38,3 % |
| **Total** | **113** | **27,05** | **23,9 %** |

### Por sprint (historias)

| Sprint | Historias | Puntos | Avance | Estado |
|---|---|---|---|---|
| S1 | HU-01 a HU-04 | 16 | 100 % | Cerrado ✅ |
| S2 | HU-05 a HU-09 | 13 | 23 % | Activo, en su primera semana |
| S3 | HU-10 a HU-13 | 13 | 0 % | — |
| S4 | HU-14 a HU-16 | 13 | 0 % | — |
| S5 | HU-17 a HU-19 | 13 | 0 % | — |
| S6 | HU-20 a HU-28 | 24 | 0 % | — |

## 4. Detalle del Sprint 2

| Clave | Historia o tarea | Pts | Estado en Jira | Avance usado |
|---|---|---|---|---|
| TS-16 | HU-05 Registrar y editar artistas | 3 | Pendiente de verificación | 90 % |
| TS-17 | HU-06 Listar artistas | 2 | Por hacer | 0 % |
| TS-18 | HU-07 Cambiar estado de artista | 2 | Por hacer | 0 % |
| TS-19 | HU-08 CRUD de producciones | 3 | En curso | 10 % |
| TS-20 | HU-09 Validar restricciones de formato | 3 | Por hacer | 0 % |
| TS-49 | Diseñar y cerrar el ERD | 1 | Listo | **30 %** (dato del equipo) |
| TS-41 | Dominio trackstudio.site y DNS | 1 | Por hacer | 0 % |
| TS-46 | Tesis: desarrollo (evidencia SCRUM) | 1 | En curso | 25 % |

Le quedan 10 de 13 puntos de historias en una semana. Esa es la principal amenaza para el plan.

## 5. Riesgos y observaciones

1. **El Sprint 2 está cargado al final.** Faltan 4 de 5 historias y quedan 5 días. Para cerrar HU-06, HU-07 y HU-08 (7 pts), sus specs tienen que arrancar ya.
2. **El estado de `TS-49` no coincide.** Jira dice Listo y el equipo, 30 %. El `CLAUDE.md` también da el ERD por CERRADO desde el 2026-10-06. Hay que unificar el dato para que el reporte sea fiable.
3. **ADR 9.2 (migraciones en deploy) sigue ABIERTO.** No se sabe si la migración de `artists` se ejecutó en staging, y eso bloquea la verificación de HU-05 en staging.
4. **Deuda arrastrada:** `TS-53` (evidencia del S1) sigue En curso aunque el Sprint 1 ya cerró. `TS-55` a `TS-59` (seguridad y deuda técnica, 5 pts) no tienen sprint asignado.
5. **Tareas fuera del horizonte:** `TS-44` (target-s7) y `TS-48` (target-s8) apuntan a sprints que no existen en un plan de 6. Hay que reubicarlas.
6. **Estimación:** las tareas no tienen *story points*. Si se estiman en Jira, este cálculo se vuelve más preciso.

## 6. Para volver al plan

| Al cierre de | Meta | Necesario |
|---|---|---|
| Semana 4 (fin del S2) | 36 % | Sumar unos 13,6 pts: cerrar HU-05 a HU-09, `TS-49` y `TS-41` (11,7 pts) y unos 2 pts de deuda o de tesis |
| Semana 6 (fin del S3) | 54 % | Mantener unos 10 pts por semana |
