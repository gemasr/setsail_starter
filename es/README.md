# Set Sail to the Grand Line

Taller para aprender a trabajar con **Android CLI** y con **agentes de código** construyendo una app Android de principio a fin.

No vas a escribir el código a mano. Vas a aprender a darle al agente el contexto adecuado (qué construir, con qué convenciones) y a usar las herramientas de Android CLI para que el agente cree, ejecute, mire y compruebe la app por sí mismo.

## Qué vamos a construir

**Sanji's Galley**, una app de cocina para el cocinero del Thousand Sunny. Responde a una pregunta: *¿qué puedo cocinar hoy?*

- **Despensa:** los ingredientes que tienes, con su cantidad.
- **Recetas:** qué recetas puedes preparar con lo que hay y cuáles no, y qué ingredientes te faltan.
- **Compra:** una lista con lo que falta para poder cocinar.

Es una app pequeña a propósito. Los datos viven en memoria y se cargan desde unos datos de ejemplo al arrancar, sin base de datos: si cierras la app, los datos vuelven a los de ejemplo, y es lo esperado. Lo importante del taller no es la app, sino cómo se trabaja con el agente.

## Qué vas a aprender

| Tema | Dónde lo verás |
|---|---|
| Darle contexto estable al agente con `AGENTS.md` (convenciones) y `SPEC.md` (qué construir) | Todos los hitos |
| Crear un proyecto con `android create` | Hito 1 |
| Compilar, instalar y lanzar la app con `android run`, sobre un emulador gestionado con `android emulator` | Hito 1 en adelante |
| Dar al agente conocimiento actualizado con las skills (`android skills`) y la documentación oficial (`android docs`) | Hito 2 |
| Que el agente vea la app con `android layout` y `android screen capture` | Hitos 3 a 5 |
| Que el agente pruebe la app con `android input` y los journeys | Hito 6 |

## Antes de empezar

Para aprovechar el taller tienes que llegar con tres cosas funcionando: **Android CLI**, **un agente de IA en la terminal** y **un emulador** (o un móvil con depuración USB). Sigue la guía de [preparación previa](INSTRUCCIONES_PREVIAS.md): casi todo el tiempo son descargas, así que hazlo con calma y con antelación. No hace falta que crees ningún proyecto de antemano.

## Durante el workshop

Durante el workshop seguiremos estas instrucciones **juntos**, así que espera a que lo hagamos antes de empezar. Puedes echarles un vistazo antes, pero no te adelantes.

### Cómo se trabaja

1. Cada hito tiene un **objetivo**, un **prompt** que copias al agente, una lista de **comprobaciones** para verificar el resultado y una ayuda **si te atascas**.
2. El agente lee `AGENTS.md` y `SPEC.md` en la raíz del proyecto. Ahí están las reglas del juego; el prompt solo dice qué hacer en cada paso.
3. El agente implementa **solo lo que pide el hito** y, cuando termina, compila y te cuenta qué ha verificado.
4. Tú compruebas el resultado con las casillas del hito, igual que lo haría una persona usuaria.

Consejo: empieza una **sesión nueva del agente en cada hito**. Cada hito trae su prompt completo, y las conversaciones largas gastan más tokens.

### Hitos

| Hito | Qué consigues |
|---|---|
| [Hito 1](Hitos/STEP_1.md) | El proyecto Android creado con Android CLI, compilando y ejecutándose en el emulador |
| [Hito 2](Hitos/STEP_2.md) | El modelo de datos, los datos de ejemplo y el esqueleto de navegación con tres destinos |
| [Hito 3](Hitos/STEP_3.md) | La pantalla de Despensa funcionando: ver, añadir y editar ingredientes |
| [Hito 4](Hitos/STEP_4.md) | Las recetas y su detalle, con lo que se puede cocinar y lo que falta |
| [Hito 5](Hitos/STEP_5.md) | La lista de la compra, construida a partir de los faltantes |
| [Hito 6](Hitos/STEP_6.md) | Journeys: el agente escribe y ejecuta pruebas que recorren la app como una persona usuaria |

## Qué hay en esta carpeta

| Archivo | Para qué sirve |
|---|---|
| `INSTRUCCIONES_PREVIAS.md` | Qué instalar y comprobar antes del taller |
| `Hitos/` | Los pasos del taller, uno por archivo |
| `SPEC.md` | La especificación de la app: datos, reglas de negocio y textos exactos |
| `../util/AGENTS.md` | Las convenciones del proyecto para el agente (arquitectura, librerías, cómo trabajar) |

Copia `SPEC.md` y `AGENTS.md` a la raíz de tu proyecto antes de lanzar el prompt del Hito 1. Los pasos exactos están en [Hito 1](Hitos/STEP_1.md).
