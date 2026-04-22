# UserStories-ASP

## 1. User Stories

### US-01: Crear vacante

**Como** recruiter  

**Quiero** crear una vacante con descripción y requisitos  

**Para** iniciar un proceso de selección estructurado  

**Criterios de aceptación (BDD):**

- **Given** que el recruiter está autenticado en el sistema  

 **When** crea una vacante con título, descripción y requisitos  

 **Then** la vacante se guarda en estado "draft"

- **Given** una vacante en estado draft  

 **When** se asigna un hiring manager  

 **Then** la vacante queda disponible para aprobación

**Prioridad:** Alta  

**Story Points:** 5  

**Nota de estimación:**  

Aunque los tickets técnicos asociados a US-01 (T-01, T-02 y T-03) suman 10 puntos, la estimación de la User Story se mantiene en 5 porque:

- Parte del trabajo puede ejecutarse en paralelo  

- Existen componentes reutilizables  

- La incertidumbre funcional es baja  

---

### US-02: Publicar vacante

**Como** recruiter  

**Quiero** publicar una vacante en distintos canales  

**Para** atraer candidatos  

**Criterios de aceptación (BDD):**

- **Given** una vacante aprobada  

 **When** el recruiter selecciona canales de publicación  

 **Then** la vacante se publica en los canales seleccionados  

- **Given** una vacante no aprobada  

 **When** el recruiter intenta publicarla  

 **Then** el sistema bloquea la acción  

**Prioridad:** Alta  

**Story Points:** 5  

---

### US-03: Registrar candidato

**Como** recruiter  

**Quiero** registrar candidatos  

**Para** gestionarlos en el proceso de selección  

**Criterios de aceptación (BDD):**

- **Given** acceso al módulo de candidatos  

 **When** el recruiter ingresa datos básicos  

 **Then** el sistema crea el perfil del candidato  

- **Given** un candidato existente  

 **When** se adjunta un CV  

 **Then** el sistema lo almacena correctamente  

**Prioridad:** Alta  

**Story Points:** 5  

---

### US-04: Evaluar candidato

**Como** interviewer  

**Quiero** completar un scorecard  

**Para** evaluar objetivamente al candidato  

**Criterios de aceptación (BDD):**

- **Given** una entrevista completada  

 **When** el interviewer ingresa puntuaciones  

 **Then** el sistema guarda el scorecard  

- **Given** un scorecard completo  

 **When** se envía la evaluación  

 **Then** se registra la recomendación final  

**Prioridad:** Alta  

**Story Points:** 8  

---

### US-05: Agendar entrevista

**Como** recruiter  

**Quiero** agendar entrevistas  

**Para** coordinar evaluaciones  

**Criterios de aceptación (BDD):**

- **Given** un candidato en proceso  

 **When** se define fecha y hora  

 **Then** se agenda la entrevista  

- **Given** entrevistadores asignados  

 **When** se confirma la entrevista  

 **Then** el sistema envía notificaciones  

**Prioridad:** Media  

**Story Points:** 5  

---

### US-06: Automatizar correos

**Como** recruiter  

**Quiero** automatizar comunicaciones  

**Para** ahorrar tiempo  

**Criterios de aceptación (BDD):**

- **Given** una regla configurada  

 **When** ocurre el evento  

 **Then** el sistema envía el correo automáticamente  

- **Given** correos enviados  

 **When** el recruiter revisa historial  

 **Then** puede ver el registro  

**Prioridad:** Media  

**Story Points:** 8  

---

### US-07: Generar resumen CV con IA

**Como** recruiter  

**Quiero** ver un resumen automático del CV  

**Para** evaluar rápidamente candidatos  

**Criterios de aceptación (BDD):**

- **Given** un CV cargado  

 **When** el sistema lo procesa  

 **Then** genera un resumen automático  

- **Given** un resumen generado  

 **When** el recruiter accede  

 **Then** lo visualiza  

**Prioridad:** Baja  

**Story Points:** 13  

---

### US-08: Visualizar pipeline

**Como** recruiter  

**Quiero** ver candidatos por etapa  

**Para** gestionar el proceso  

**Criterios de aceptación (BDD):**

- **Given** una vacante activa  

 **When** se accede al pipeline  

 **Then** se visualizan candidatos por etapa  

- **Given** un candidato  

 **When** cambia de etapa  

 **Then** el sistema actualiza su estado  

**Prioridad:** Alta  

**Story Points:** 5  

---

## 2. Backlog de Producto

| ID    | User Story                     | Prioridad | Story Points |

|------|------------------------------|----------|-------------|

| US-01 | Crear vacante                | Alta     | 5           |

| US-02 | Publicar vacante             | Alta     | 5           |

| US-03 | Registrar candidato          | Alta     | 5           |

| US-04 | Evaluar candidato            | Alta     | 8           |

| US-08 | Visualizar pipeline          | Alta     | 5           |

| US-05 | Agendar entrevista           | Media    | 5           |

| US-06 | Automatizar correos          | Media    | 8           |

| US-07 | IA resumen CV                | Baja     | 13          |

### Estrategia de priorización

Se priorizó usando enfoque MVP:

- Primero funcionalidades core  

- Luego gestión y colaboración  

- Finalmente IA  

---

## 3. Prompts utilizados y conclusiones

### Prompt 1

Generar user stories con BDD

### Prompt 2

Generar backlog priorizado

### Conclusión

Los prompts permitieron:

- Generar backlog accionable  

- Definir criterios claros  

- Alinear negocio y tecnología  

---

## 4. Tickets técnicos

### US-01: Crear vacante

#### T-01: API backend (POST /jobs)

- Endpoint `POST /jobs`
- Validación de datos
- Persistencia en base de datos

**Requisitos no funcionales:**

- **RBAC:**
  - Solo usuarios con rol `recruiter` pueden invocar `POST /jobs`
  - La validación de permisos debe realizarse en backend

- **Auditoría y trazabilidad:**
  - Registrar `user_id` del creador
  - Registrar `timestamp` de creación
  - Registrar cambios relevantes asociados a la creación
  - Incluir `correlation_id` para trazabilidad extremo a extremo

- **Eventos:**
  - Emitir evento `JobCreated`
  - Esquema mínimo del evento: `job_id`, `company_id`, `created_at`
  - Publicar el evento en el bus de eventos para consumo por otros subsistemas  

---

#### T-02: UI formulario

- Formulario de creación  

- Validaciones frontend  

- Botón guardar  

---

#### T-03: Base de datos

Tabla: JobPosition  

Campos:

- id: UUID  

- company_id: UUID (FK)  

- hiring_manager_id: UUID (FK)  

- recruiter_id: UUID (FK)  

- title: string  

- department: string  

- location: string  

- employment_type: enum  

- status: enum (default: draft)  

- description: text  

- requirements: text  

- created_at: timestamp (default current)  

- published_at: timestamp (nullable)  

---

## 5. Estimación

| Ticket | Descripción     | Story Points |

|--------|----------------|-------------|

| T-01   | API backend    | 3           |

| T-02   | UI formulario  | 5           |

| T-03   | Base de datos  | 2           |

**Total:** 10 puntos  

### Metodología

Escala Fibonacci (1,2,3,5,8,13)

