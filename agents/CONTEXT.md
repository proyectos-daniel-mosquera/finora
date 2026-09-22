# Finora — Contexto y guía maestra del proyecto

## 1. Propósito de este documento

Este archivo contiene el contexto completo y las decisiones principales del proyecto **Finora**, una aplicación de finanzas personales para **web y móvil**.

Debe servir como documento de referencia para cualquier IA, asistente de programación o desarrollador que participe en el proyecto.

La IA debe leer este documento antes de proponer cambios importantes, instalar dependencias, modificar la arquitectura o comenzar una nueva funcionalidad.

---

# 2. Producto

## Nombre

**Finora**

## Idea

Finora será una aplicación de finanzas personales que ayude al usuario a:

- Registrar sus ingresos.
- Organizar su dinero por cuentas.
- Definir presupuestos.
- Distribuir los ingresos mediante porcentajes configurables.
- Registrar gastos.
- Organizar gastos por categorías.
- Visualizar en qué se está gastando el dinero.
- Controlar el cumplimiento de presupuestos.
- Recibir alertas cuando un presupuesto se acerque o supere sus límites.
- Crear metas de ahorro.
- Registrar aportes a las metas.
- Visualizar el progreso de las metas.
- Celebrar hitos de ahorro.

La aplicación debe evolucionar posteriormente hacia funciones más avanzadas, pero inicialmente se construirá un **MVP sólido y bien estructurado**.

---

# 3. Objetivo del proyecto

Finora tiene dos objetivos simultáneos:

1. Crear una aplicación que pueda ser realmente útil para gestionar finanzas personales.
2. Servir como un proyecto de portafolio profesional que demuestre buenas prácticas modernas de desarrollo de software.

Por eso no se busca únicamente que "funcione".

También se busca demostrar:

- Arquitectura limpia y razonable.
- TypeScript.
- React Native.
- Desarrollo multiplataforma.
- Buen manejo del estado.
- Consumo de backend.
- Seguridad.
- Validación de datos.
- Diseño de base de datos.
- Autenticación.
- Testing.
- Git.
- Documentación.
- Buenas prácticas de ingeniería.
- Capacidad para llevar un proyecto desde cero hasta producción.

---

# 4. Perfil del desarrollador

El desarrollador principal tiene experiencia previa principalmente en:

- PHP.
- Laravel.
- JavaScript.
- HTML.
- CSS.
- Tailwind CSS.
- AlpineJS.
- MySQL/PostgreSQL.
- Docker.
- Linux/Fedora.
- Git/GitLab.
- REST APIs.
- Webhooks.
- Jobs, queues, scheduler y Artisan.

Tiene un nivel aproximado de desarrollador **semi-experimentado**.

### Importante

El desarrollador **NO tiene experiencia previa significativa con React Native**.

Por lo tanto, el desarrollo de Finora debe funcionar también como proceso de aprendizaje.

La IA debe actuar como **mentor/senior software engineer**, no simplemente como generador de código.

Cuando se tome una decisión técnica importante, explicar:

1. El problema.
2. Las alternativas principales.
3. La decisión.
4. Por qué se toma.
5. Cómo se implementa.
6. Qué trade-offs existen.

Evitar explicaciones innecesariamente académicas, pero no ocultar conceptos importantes.

---

# 5. Stack tecnológico definido

## Frontend

- React Native.
- Expo.
- TypeScript.
- Expo Router.
- React Native Web.

La aplicación debe poder ejecutarse inicialmente en:

- Android.
- iOS.
- Web.

## Styling

Se ha considerado y está previsto utilizar:

- NativeWind.

Pero **no instalarlo hasta que corresponda según la etapa del proyecto**.

## Backend

Se ha decidido utilizar:

- Supabase.

Supabase será utilizado como backend/BaaS y proporcionará principalmente:

- PostgreSQL.
- Authentication.
- Row Level Security (RLS).
- API.
- Storage cuando sea necesario.
- Edge Functions cuando sean necesarias.
- Automatizaciones/backend jobs cuando correspondan.

## Datos y servidor

Se prevé utilizar:

- TanStack Query para server state.
- Zod para validación y schemas.

## Control de versiones

- Git.
- GitHub.

## Herramientas futuras potenciales

Dependiendo de las necesidades del proyecto:

- Sentry.
- Push notifications.
- CI/CD.
- Testing automatizado.
- Expo Application Services (EAS).
- Edge Functions.
- IA para análisis financieros.

No instalar herramientas simplemente porque "son buenas".

Cada dependencia debe tener una razón concreta.

---

# 6. Decisión importante: React Native + Expo

Se evaluaron diferentes alternativas:

- React + Ionic + Capacitor.
- React Web + React Native.
- Flutter.
- React Native + Expo.

La decisión para Finora es:

**React Native + Expo + TypeScript + React Native Web.**

## Razón

El desarrollador ya tiene experiencia web y Laravel.

React Native permite ampliar su perfil hacia desarrollo móvil mientras reutiliza conocimientos de React/TypeScript.

Expo simplifica:

- Desarrollo local.
- Android.
- iOS.
- Web.
- Build.
- Configuración nativa.
- Integración con funcionalidades del dispositivo.

React Native Web permitirá compartir parte de la aplicación con web.

### Importante

No se debe asumir que absolutamente toda la UI tiene que ser idéntica en web y móvil.

Lo que se debe intentar compartir principalmente:

- Tipos.
- Validaciones.
- Servicios.
- Acceso a Supabase.
- Lógica de negocio.
- Hooks.
- Reglas de dominio.

La UI puede adaptarse cuando las plataformas tengan necesidades diferentes.

---

# 7. Estado actual del proyecto

El proyecto ya fue creado.

Ruta local:

```text
~/Develop/finora

Nombre del proyecto:

finora

La estructura inicial actual es aproximadamente:

finora/
├── AGENTS.md
├── CLAUDE.md
├── node_modules/
├── README.md
├── tsconfig.json
├── app.json
├── expo-env.d.ts
├── package.json
├── scripts/
├── assets/
├── LICENSE
├── package-lock.json
└── src/
    ├── app/
    │   ├── _layout.tsx
    │   ├── index.tsx
    │   └── explore.tsx
    ├── components/
    │   ├── animated-icon.module.css
    │   ├── animated-icon.tsx
    │   ├── animated-icon.web.tsx
    │   ├── app-tabs.tsx
    │   ├── app-tabs.web.tsx
    │   ├── external-link.tsx
    │   ├── hint-row.tsx
    │   ├── themed-text.tsx
    │   ├── themed-view.tsx
    │   ├── ui/
    │   │   └── collapsible.tsx
    │   └── web-badge.tsx
    ├── constants/
    │   └── theme.ts
    ├── hooks/
    │   ├── use-color-scheme.ts
    │   ├── use-color-scheme.web.ts
    │   └── use-theme.ts
    └── global.css

La plantilla de Expo utiliza:

src/app/

y no:

app/

en la raíz.

No mover src/app a la raíz sin una razón técnica.

8. Versiones conocidas al iniciar el proyecto

Al crear Finora, las versiones reportadas por package.json fueron:

Node.js: v22.22.2
npm: 10.9.7
Git: 2.55.0

Expo: ~57.0.24
React Native: 0.86.3
React: 19.2.3
React DOM: 19.2.3
React Native Web: ~0.21.0
Expo Router: ~57.0.22
TypeScript: ~6.0.3

Estas versiones corresponden al estado inicial del proyecto y pueden cambiar mediante actualizaciones futuras.

Cuando se necesite tomar una decisión relacionada con versiones actuales de Expo, React Native, Supabase o alguna librería, verificar primero la documentación oficial actual.

No asumir que un tutorial antiguo sigue siendo válido.

9. Estado actual: limpieza de la plantilla

La plantilla de Expo contiene componentes y pantallas de demostración.

Se decidió limpiar la plantilla antes de comenzar a desarrollar Finora.

Archivos candidatos a eliminar por ser código de demostración:

src/app/explore.tsx

src/components/animated-icon.module.css
src/components/animated-icon.tsx
src/components/animated-icon.web.tsx
src/components/app-tabs.tsx
src/components/app-tabs.web.tsx
src/components/external-link.tsx
src/components/hint-row.tsx
src/components/ui/collapsible.tsx
src/components/web-badge.tsx
src/components/themed-text.tsx
src/components/themed-view.tsx

Sin embargo, antes de eliminarlos definitivamente se debe revisar el contenido de:

src/app/_layout.tsx
src/app/index.tsx
src/constants/theme.ts

Especialmente para entender las dependencias de la plantilla.

No eliminar archivos arbitrariamente.

10. Filosofía de arquitectura

Finora debe tener una arquitectura profesional, pero sin caer en overengineering.

La regla principal es:

La arquitectura debe servir al problema, no el problema a la arquitectura.

Se busca aplicar conceptos de:

SOLID.
Separación de responsabilidades.
Dependency Inversion cuando aporte valor.
Clean Architecture de forma pragmática.
Repository Pattern.
Separación entre UI, lógica de negocio y acceso a datos.
Validación en límites del sistema.
Tipado estricto.

Pero no se deben crear diez capas para una funcionalidad que solo necesita dos.

11. Arquitectura conceptual

La arquitectura objetivo puede representarse inicialmente así:

UI
 ↓
Hook / Controller
 ↓
Use Case / Business Logic
 ↓
Repository
 ↓
Supabase

No todas las funcionalidades tienen que utilizar obligatoriamente todas las capas.

La IA debe evaluar cada caso.

Ejemplo

Una pantalla no debería realizar directamente consultas complejas a Supabase si eso provoca que la lógica de acceso a datos quede distribuida por toda la aplicación.

Preferiblemente:

Screen
  ↓
Hook
  ↓
Use Case
  ↓
Repository
  ↓
Supabase

Esto facilita:

Testing.
Mantenimiento.
Cambio de proveedor.
Reutilización.
Separación de responsabilidades.
12. Estructura objetivo aproximada

La estructura final podría evolucionar hacia algo similar a:

finora/
├── src/
│   ├── app/
│   ├── components/
│   ├── features/
│   ├── hooks/
│   ├── lib/
│   ├── services/
│   ├── types/
│   └── utils/
│
├── assets/
├── tests/
├── app.json
├── package.json
├── tsconfig.json
├── .env.example
├── README.md
└── ...

Esta estructura es orientativa.

No crear todas estas carpetas inmediatamente.

Cada carpeta debe aparecer cuando exista una necesidad real.

13. Principios de código
TypeScript

Utilizar TypeScript de forma estricta.

Evitar:

any

salvo casos realmente justificados.

Preferir:

interfaces.
types.
unions.
generics.
schemas de Zod.
tipos derivados cuando sea apropiado.
14. Validación

Zod será utilizado para validar datos en los límites importantes de la aplicación.

Ejemplo conceptual:

Input
 ↓
Zod Schema
 ↓
Validated Data
 ↓
Business Logic

No confiar exclusivamente en TypeScript para validar datos provenientes de:

formularios.
APIs.
Supabase.
almacenamiento local.
parámetros externos.
15. Server State

Se planea utilizar TanStack Query para manejar:

fetching.
caching.
loading states.
error states.
refetching.
mutations.
invalidación de queries.

No utilizar Redux o Zustand automáticamente.

Primero distinguir:

UI state

Ejemplos:

Modal abierto/cerrado.
Tab seleccionado.
Estado visual de un formulario.
Server state

Ejemplos:

Gastos.
Ingresos.
Presupuestos.
Metas.
Cuentas.
Domain/business state

Ejemplos:

Porcentaje disponible para ahorro.
Cálculo de presupuesto.
Reglas de alerta.
Progreso de una meta.

Cada tipo de estado debe tener la herramienta apropiada.

16. MVP

El MVP inicialmente debe incluir:

1. Registro y autenticación
Registro.
Login.
Logout.
Manejo de sesión.
Protección de rutas.
Perfil básico.
2. Ingresos

El usuario puede registrar:

Monto.
Fecha.
Periodicidad.
Cuenta asociada.
Descripción cuando sea necesario.

Periodicidades potenciales:

Mensual.
Quincenal.
Semanal.
Otra configuración razonable.
3. Presupuesto

El usuario podrá definir cómo distribuir sus ingresos.

Ejemplo:

20% → Ahorro
50% → Necesidades
30% → Gastos personales

Pero estos porcentajes deben ser configurables.

El sistema debe validar que la distribución sea coherente.

4. Cuentas

Ejemplos:

Cuenta bancaria.
Efectivo.
Cuenta de ahorros.
Otras cuentas financieras.

Cada cuenta debe poder asociarse con movimientos.

5. Categorías

Ejemplos:

Alimentación
Transporte
Vivienda
Servicios
Entretenimiento
Salud
Educación
Otros

Las categorías deben poder evolucionar posteriormente.

6. Gastos

Registrar:

Monto.
Fecha.
Categoría.
Cuenta.
Descripción.
Información necesaria para análisis posteriores.
7. Dashboard

Debe mostrar información útil como:

Ingresos.
Gastos.
Ahorros.
Balance disponible.
Distribución por categorías.
Estado de presupuesto.
Progreso de metas.
8. Alertas de presupuesto

El sistema debe poder detectar niveles como:

50%
80%
100%
120%

Ejemplo:

< 50%   → normal
50-79%  → seguimiento
80-99%  → advertencia
100%    → presupuesto alcanzado
> 100%  → presupuesto excedido

Estos valores son configurables y pueden evolucionar.

9. Metas de ahorro

Una meta puede tener:

Nombre.
Monto objetivo.
Fecha objetivo.
Monto actual.
Aportes.
Progreso.
10. Hitos de ahorro

Ejemplos:

25%
50%
75%
100%

Cuando se alcance un hito se puede mostrar una celebración visual.

17. Funcionalidades posteriores

No forman parte del MVP inicial.

Se consideran para futuras versiones:

Gastos recurrentes.
Ingresos recurrentes.
Metas avanzadas.
Notificaciones push.
Recordatorios.
Reportes.
Exportación de información.
PWA.
Funcionalidades offline.
Integraciones externas.
IA.
Insights financieros.
Análisis automático de hábitos.
Recomendaciones basadas en datos.
18. IA

La IA NO forma parte del MVP inicial.

Primero se debe construir una base de datos financiera correctamente estructurada.

Posteriormente la IA podría analizar:

Patrones de gasto.
Categorías con mayor crecimiento.
Cumplimiento de presupuesto.
Tendencias.
Posibles anomalías.
Comportamiento de ahorro.

Principio:

Primero datos estructurados y confiables; después IA.

No agregar IA simplemente como elemento decorativo del portafolio.

19. Modelo de datos inicial

El modelo conceptual considerado es:

profiles
  ├── accounts
  ├── incomes
  ├── budgets
  │      └── budget_categories
  ├── categories
  ├── expenses
  ├── savings_goals
  │      └── savings_goal_contributions
  └── notifications

El modelo todavía NO está cerrado.

Podría evolucionar hacia conceptos como:

transactions
recurring_expenses
recurring_incomes
financial_goals

si el dominio lo requiere.

No crear tablas anticipadamente sin una necesidad funcional clara.

20. Seguridad

La seguridad es una parte importante del proyecto.

Supabase debe utilizar:

Row Level Security (RLS).

Regla fundamental:

Un usuario nunca debe poder acceder a los datos financieros de otro usuario.

Las tablas que contengan información perteneciente a usuarios deben tener políticas RLS apropiadas.

No confiar únicamente en filtros realizados desde React Native.

Ejemplo incorrecto conceptualmente:

Frontend:
"Traer únicamente los gastos del usuario X"

La seguridad real debe estar respaldada por:

Supabase/PostgreSQL/RLS
21. Manejo de errores

Todas las funcionalidades importantes deben contemplar:

Loading state.
Error state.
Empty state.
Success state.
Validación.
Errores de red.
Errores de backend.
Errores inesperados.

Evitar pantallas que simplemente queden en blanco cuando una petición falla.

22. UX

Finora debe tener una experiencia sencilla.

Principios:

Información financiera clara.
Pocas acciones innecesarias.
Formularios simples.
Feedback inmediato.
Estados vacíos útiles.
Confirmación de acciones destructivas.
Diseño responsive.
Accesibilidad básica.
Diferencias apropiadas entre web y móvil.

No diseñar únicamente pensando en desktop.

23. Git

Git debe utilizarse desde el inicio.

Los commits deben ser pequeños y significativos.

Ejemplos:

chore: initialize Finora with Expo
chore: remove Expo demo components
feat: add authentication screen
feat: implement Supabase authentication
feat: add expense creation
fix: validate expense amount
refactor: extract expense repository
test: add budget calculation tests

Evitar commits como:

cambios
cosas
final
final2
arreglo
24. Dependencias

No instalar muchas dependencias al comienzo.

Cada dependencia debe responder a una necesidad.

Stack previsto:

Expo
React Native
TypeScript
Expo Router
React Native Web
NativeWind
Supabase
TanStack Query
Zod

Pero deben incorporarse progresivamente.

No instalar:

Redux.
Zustand.
Axios.
librerías de formularios.
librerías de UI.
librerías de gráficos.
etc.

sin evaluar primero si realmente aportan valor.

25. Testing

El proyecto debe incorporar testing progresivamente.

Prioridades:

Unit tests

Para:

Cálculos de presupuesto.
Distribución de ingresos.
Progreso de metas.
Reglas de alertas.
Funciones puras.
Integration tests

Para:

Flujos importantes.
Repositories.
Integración con backend cuando corresponda.
E2E

Puede incorporarse posteriormente para flujos críticos.

No hace falta implementar todo el sistema de testing el primer día.

26. Calidad y tooling

Se busca incorporar progresivamente:

ESLint.
Formateo consistente.
TypeScript strict.
Testing.
Variables de entorno.
.env.example.
CI/CD.
Revisión de errores.
Sentry u otra solución de observabilidad.
27. Variables de entorno

Nunca subir secretos al repositorio.

Se debe utilizar:

.env

y proporcionar:

.env.example

La configuración de Supabase debe manejarse correctamente.

Las claves públicas necesarias para el cliente pueden tener un tratamiento diferente de secretos del servidor, pero nunca debe asumirse que una variable es secreta únicamente por su nombre.

Los secretos reales deben permanecer fuera del repositorio.

28. Orden de desarrollo esperado

El proyecto debe construirse progresivamente.

Orden aproximado:

1. Limpiar plantilla Expo
2. Entender Expo Router
3. Definir arquitectura base
4. Configurar TypeScript/ESLint/formato según necesidad
5. Diseñar modelo de datos
6. Crear proyecto/configuración de Supabase
7. Authentication
8. Protección de rutas
9. Perfil
10. Cuentas
11. Categorías
12. Ingresos
13. Presupuestos
14. Gastos
15. Dashboard
16. Alertas
17. Metas de ahorro
18. Hitos/celebraciones
19. Testing
20. Mejoras UX
21. Preparación para producción

El orden puede cambiar si aparece una dependencia técnica importante.

29. Regla de desarrollo

Antes de implementar una funcionalidad importante, seguir esta secuencia:

Problema
 ↓
Requisitos
 ↓
Modelo de datos
 ↓
Reglas de negocio
 ↓
Arquitectura
 ↓
Implementación
 ↓
Validación
 ↓
Tests
 ↓
Refactor

No comenzar escribiendo componentes sin entender el problema.

30. Regla para la IA

La IA debe comportarse como un senior engineer / mentor.

Debe:
Explicar decisiones.
Detectar riesgos.
Señalar inconsistencias.
Proponer alternativas.
Evitar overengineering.
Mantener el contexto del proyecto.
Priorizar seguridad.
Priorizar mantenibilidad.
Considerar web y móvil.
Revisar compatibilidad de versiones cuando sea necesario.
Explicar conceptos de React Native porque el desarrollador está aprendiendo.
Preferir soluciones actuales y documentadas.
Advertir cuando una solución provenga de un tutorial antiguo.
Mantener consistencia arquitectónica.
No debe:
Cambiar la arquitectura sin explicarlo.
Instalar dependencias innecesarias.
Crear carpetas porque sí.
Generar código enorme sin explicar lo esencial.
Usar any indiscriminadamente.
Poner lógica de negocio compleja dentro de componentes.
Exponer secretos.
Ignorar RLS.
Asumir que web y móvil tienen exactamente las mismas necesidades.
Implementar IA antes de tener datos estructurados.
Copiar patrones de Laravel literalmente en React Native.
31. Cómo explicar React Native al desarrollador

El desarrollador viene de Laravel/PHP.

Las explicaciones pueden utilizar analogías con conceptos conocidos, pero dejando claro que no son equivalencias exactas.

Ejemplo:

Laravel Routes
       ↓
Expo Router

Blade/View
       ↓
React Native Component

Controller/Service
       ↓
Hook / Use Case / Service

Eloquent/Repository
       ↓
Repository + Supabase

Database
       ↓
PostgreSQL/Supabase

Estas analogías son únicamente pedagógicas.

32. Decisiones que todavía NO están cerradas

No asumir como definitivas:

Modelo final de base de datos.
Sistema final de categorías.
Diseño visual.
Sistema definitivo de navegación.
Sistema de formularios.
Sistema de gráficos.
Sistema de notificaciones.
Estrategia offline.
Arquitectura de IA.
CI/CD definitivo.
Estructura exacta de todas las carpetas.

Estas decisiones deben tomarse cuando exista suficiente contexto.

33. Filosofía general

Finora debe priorizar:

Claridad
+
Seguridad
+
Mantenibilidad
+
Buena UX
+
Aprendizaje
+
Valor de portafolio

sobre:

Cantidad de tecnologías
+
Cantidad de funcionalidades
+
Complejidad innecesaria

El objetivo no es construir una aplicación artificialmente compleja.

El objetivo es construir una aplicación real, bien diseñada y defendible técnicamente en una entrevista.

34. Estado de trabajo actual

El proyecto está recién creado.

La tarea inmediata es:

Revisar src/app/_layout.tsx.
Revisar src/app/index.tsx.
Revisar src/constants/theme.ts.
Entender las dependencias de la plantilla.
Eliminar código de demostración innecesario.
Crear una base limpia para Finora.
Hacer un commit de limpieza.
Diseñar la arquitectura inicial.
Continuar con la implementación del MVP.

No comenzar todavía con Supabase ni con funcionalidades de negocio hasta terminar esta etapa de preparación.

35. Regla final

Cuando haya una duda sobre una decisión técnica, no asumir automáticamente.

La IA debe presentar, cuando sea relevante:

Problema:
...

Opciones:
A. ...
B. ...

Recomendación:
...

Motivo:
...

Trade-offs:
...

La decisión final debe buscar un equilibrio entre:

Buenas prácticas profesionales.
Simplicidad.
Aprendizaje del desarrollador.
Mantenibilidad.
Escalabilidad razonable.
Valor como proyecto de portafolio.

Finora debe crecer de manera incremental y consciente.