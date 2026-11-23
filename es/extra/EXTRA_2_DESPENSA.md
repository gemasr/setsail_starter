## Objetivo

La pantalla de Despensa funcionando, con datos reales.

## Prompt

```
Lee SPEC.md y mira el código actual. Implementa la pantalla Despensa: una lista de los ingredientes de la despensa con su cantidad y unidad (por ejemplo "Huevo · 6 ud"), cargada con los datos de ejemplo. Añade el botón "Añadir ingrediente", que abre un formulario con el nombre (elegido entre los ingredientes conocidos) y la cantidad, y un botón "Guardar". Tocar un elemento permite editar su cantidad. No se puede guardar una cantidad vacía o 0. Si se añade un ingrediente que ya existe, se suma la cantidad en la misma línea. Si la despensa está vacía, muestra "La despensa está vacía". Usa los textos exactos de SPEC.md. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

- [ ]  Ves "Huevo · 6 ud" y "Arroz · 1000 g"
- [ ]  Añades "Nata" con 250 y aparece "Nata · 250 ml"
- [ ]  Añades "Huevo" con 2 y la línea pasa a "Huevo · 8 ud" (sin duplicar)

Si cierras y vuelves a abrir la app, los datos vuelven a los de ejemplo: es lo esperado, porque viven en memoria.

## Si te atascas

```
Revisa tu implementación contra los criterios de comprobación de este hito y corrige lo que falle.
```