# Extra step: mover lo comprado a la despensa

Es un paso **opcional**, por si te sobra tiempo. Esta vez no hay prompt para copiar: te contamos qué tiene que pasar y el prompt lo escribes tú.

## Objetivo

Añadir una funcionalidad completa y comprobarla con un journey: lo que marcas como comprado en **Shopping** pasa a **Pantry**, y las recetas se actualizan.

## Antes de empezar

1. Continúa en la carpeta del Hito 4. Si no lo hiciste, descarga [dv-mad-step-4.zip](https://github.com/gemasr/sanjis_galley/archive/refs/tags/dv-mad-step-4.zip) y descomprímelo en una **carpeta nueva**.
2. Abre el agente en esa carpeta, en una **sesión nueva**.

## Qué tienes que conseguir

- En **Shopping** hay un botón `Move purchased to pantry` (el texto está en `SPEC.md`).
- Al pulsarlo, las cantidades de los ingredientes comprados se suman a la despensa.
- La despensa sigue sin tener dos líneas del mismo ingrediente.
- Los ingredientes comprados desaparecen de la lista de la compra; los no comprados se quedan.
- Hay un journey en `journeys/` que comprueba el flujo completo, desde una receta a la que le faltan ingredientes hasta que aparece como `Available`.

## Antes de escribir el prompt

Piensa qué necesita saber el agente y qué sabe ya por `AGENTS.md` y `SPEC.md`:

- ¿Cuándo se ve el botón? `SPEC.md` no lo dice: decídelo tú.
- ¿Cómo vas a saber que ha terminado bien?
- ¿Qué no quieres que haga?

## Comprobación

Cierra y vuelve a abrir la app antes de empezar, para partir de los datos de ejemplo.

- [ ]  Añade los faltantes de "Baratie Ramen", marca solo "Wheat noodles" como comprado y muévelo: "Fish stock" sigue en **Shopping** y a la receta le falta 1 ingrediente
- [ ]  En **Pantry**, añade 100 ml de "Fish stock". Después marca "Fish stock" como comprado y muévelo: aparece "Fish stock · 600 ml" en **una sola línea**
- [ ]  **Shopping** muestra "Nothing to buy" y "Baratie Ramen" aparece como "Available"
- [ ]  Tu journey está en `journeys/` y pasa

## Si te atascas

- Compara tu prompt con los de los hitos anteriores: ¿dices qué hay que hacer, con qué reglas y cómo comprobarlo?
- Pide al agente que revise su implementación contra una casilla concreta que falle, contándole qué esperabas y qué has visto.
- Si lo que falla es el journey, pídele que te muestre en qué paso falla y por qué.
