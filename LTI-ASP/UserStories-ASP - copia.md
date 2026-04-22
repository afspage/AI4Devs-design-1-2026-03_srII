\# UserStories-ASP



\## 1. User Stories



\### US-01: Crear vacante

\*\*Como\*\* recruiter  

\*\*Quiero\*\* crear una vacante con descripción y requisitos  

\*\*Para\*\* iniciar un proceso de selección estructurado  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* que el recruiter está autenticado en el sistema  

&#x20; \*\*When\*\* crea una vacante con título, descripción y requisitos  

&#x20; \*\*Then\*\* la vacante se guarda en estado "draft"



\- \*\*Given\*\* una vacante en estado draft  

&#x20; \*\*When\*\* se asigna un hiring manager  

&#x20; \*\*Then\*\* la vacante queda disponible para aprobación



\*\*Prioridad:\*\* Alta  

\*\*Story Points:\*\* 5  



\---



\### US-02: Publicar vacante

\*\*Como\*\* recruiter  

\*\*Quiero\*\* publicar una vacante en distintos canales  

\*\*Para\*\* atraer candidatos  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* una vacante aprobada  

&#x20; \*\*When\*\* el recruiter selecciona canales de publicación  

&#x20; \*\*Then\*\* la vacante se publica en los canales seleccionados



\- \*\*Given\*\* una vacante no aprobada  

&#x20; \*\*When\*\* el recruiter intenta publicarla  

&#x20; \*\*Then\*\* el sistema bloquea la acción



\*\*Prioridad:\*\* Alta  

\*\*Story Points:\*\* 5  



\---



\### US-03: Registrar candidato

\*\*Como\*\* recruiter  

\*\*Quiero\*\* registrar candidatos manualmente o desde fuentes externas  

\*\*Para\*\* gestionarlos en el proceso de selección  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* que el recruiter accede al módulo de candidatos  

&#x20; \*\*When\*\* ingresa los datos básicos del candidato  

&#x20; \*\*Then\*\* el sistema crea el perfil del candidato



\- \*\*Given\*\* un candidato creado  

&#x20; \*\*When\*\* se adjunta un CV  

&#x20; \*\*Then\*\* el sistema guarda el archivo y lo asocia al candidato



\*\*Prioridad:\*\* Alta  

\*\*Story Points:\*\* 5  



\---



\### US-04: Evaluar candidato

\*\*Como\*\* interviewer  

\*\*Quiero\*\* completar un scorecard  

\*\*Para\*\* evaluar objetivamente al candidato  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* una entrevista completada  

&#x20; \*\*When\*\* el interviewer ingresa puntuaciones por competencia  

&#x20; \*\*Then\*\* el sistema guarda el scorecard



\- \*\*Given\*\* un scorecard completo  

&#x20; \*\*When\*\* el interviewer envía su evaluación  

&#x20; \*\*Then\*\* se registra la recomendación final



\*\*Prioridad:\*\* Alta  

\*\*Story Points:\*\* 8  



\---



\### US-05: Agendar entrevista

\*\*Como\*\* recruiter  

\*\*Quiero\*\* agendar entrevistas  

\*\*Para\*\* coordinar evaluaciones con el equipo  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* un candidato en proceso  

&#x20; \*\*When\*\* el recruiter define fecha y hora  

&#x20; \*\*Then\*\* se crea la entrevista en el sistema



\- \*\*Given\*\* una entrevista agendada  

&#x20; \*\*When\*\* se asignan entrevistadores  

&#x20; \*\*Then\*\* el sistema envía notificaciones



\*\*Prioridad:\*\* Media  

\*\*Story Points:\*\* 5  



\---



\### US-06: Automatizar correos

\*\*Como\*\* recruiter  

\*\*Quiero\*\* automatizar comunicaciones  

\*\*Para\*\* ahorrar tiempo y mejorar la experiencia del candidato  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* una regla de automatización configurada  

&#x20; \*\*When\*\* ocurre el evento definido  

&#x20; \*\*Then\*\* el sistema envía el correo automáticamente



\- \*\*Given\*\* un correo enviado automáticamente  

&#x20; \*\*When\*\* el recruiter revisa el historial  

&#x20; \*\*Then\*\* puede ver el registro del envío



\*\*Prioridad:\*\* Media  

\*\*Story Points:\*\* 8  



\---



\### US-07: Generar resumen CV con IA

\*\*Como\*\* recruiter  

\*\*Quiero\*\* ver un resumen automático del CV  

\*\*Para\*\* evaluar más rápido a los candidatos  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* un CV cargado  

&#x20; \*\*When\*\* el sistema procesa el documento  

&#x20; \*\*Then\*\* se genera un resumen automático



\- \*\*Given\*\* un resumen generado  

&#x20; \*\*When\*\* el recruiter accede al perfil  

&#x20; \*\*Then\*\* puede visualizar el resumen



\*\*Prioridad:\*\* Baja  

\*\*Story Points:\*\* 13  



\---



\### US-08: Visualizar pipeline

\*\*Como\*\* recruiter  

\*\*Quiero\*\* ver candidatos por etapa  

\*\*Para\*\* gestionar el proceso de selección  



\*\*Criterios de aceptación (BDD):\*\*



\- \*\*Given\*\* una vacante activa  

&#x20; \*\*When\*\* el recruiter accede al pipeline  

&#x20; \*\*Then\*\* visualiza candidatos por etapa



\- \*\*Given\*\* un candidato en el pipeline  

&#x20; \*\*When\*\* se mueve a otra etapa  

&#x20; \*\*Then\*\* el sistema actualiza su estado



\*\*Prioridad:\*\* Alta  

\*\*Story Points:\*\* 5  



\---



\## 2. Backlog de Producto



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



\### Estrategia de priorización



Se priorizó utilizando enfoque MVP:



\- Primero funcionalidades core del ATS

\- Luego gestión y colaboración

\- Finalmente automatización e IA



\---



\## 3. Prompts utilizados y conclusiones



\### Prompt 1

"Dado el diseño de un ATS, genera user stories con criterios de aceptación en formato Given/When/Then."



\### Resultado

Se obtuvieron historias bien estructuradas con criterios claros y testeables.



\---



\### Prompt 2

"Genera un backlog priorizado con enfoque MVP para un sistema ATS."



\### Resultado

Se logró una priorización coherente basada en valor de negocio.



\---



\### Conclusión



Los prompts fueron efectivos porque:



\- Traducen el diseño en tareas accionables

\- Permiten generar criterios claros para QA

\- Alinean desarrollo con objetivos del negocio



\---



\## 4. Tickets técnicos



\### US-01: Crear vacante



\#### T-01: API backend

\- Endpoint POST /jobs

\- Validación de datos

\- Persistencia en base de datos



\#### T-02: UI formulario

\- Formulario de creación

\- Validaciones frontend

\- Botón guardar



\#### T-03: Base de datos

\- Tabla JobPosition

\- Campos: id, title, description, status



\---



\## 5. Estimación



| Ticket | Descripción           | Story Points |

|--------|----------------------|-------------|

| T-01   | API backend          | 3           |

| T-02   | UI formulario        | 5           |

| T-03   | Base de datos        | 2           |



\*\*Total:\*\* 10 puntos



\### Metodología utilizada



Se utilizó escala Fibonacci (1,2,3,5,8,13) para reflejar complejidad e incertidumbre.

