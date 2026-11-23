## Objetivo

La pantalla de Pantry funcionando, con datos reales.

## Prompt

```
Lee SPEC.md y mira el código actual. Implementa la pantalla Pantry: una lista de los ingredientes de la despensa con su cantidad y unidad (por ejemplo "Egg · 6 pcs"), cargada con los datos de ejemplo. Añade el botón "Add ingredient", que abre un formulario con el nombre (elegido entre los ingredientes conocidos) y la cantidad, y un botón "Save". Tocar un elemento permite editar su cantidad. No se puede guardar una cantidad vacía o 0. Si se añade un ingrediente que ya existe, se suma la cantidad en la misma línea. Si la despensa está vacía, muestra "The pantry is empty". Usa los textos exactos de SPEC.md. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

- [ ]  Ves "Egg · 6 pcs" y "Rice · 1000 g"
- [ ]  Añades "Cream" con 250 y aparece "Cream · 250 ml"
- [ ]  Añades "Egg" con 2 y la línea pasa a "Egg · 8 pcs" (sin duplicar)

Si cierras y vuelves a abrir la app, los datos vuelven a los de ejemplo: es lo esperado, porque viven en memoria.

## Si te atascas

```
Revisa tu implementación contra los criterios de comprobación de este hito y corrige lo que falle.
```