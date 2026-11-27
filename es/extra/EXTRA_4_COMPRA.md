## Objetivo

Convertir lo que falta en una lista de la compra.

## Prompt

```
Lee SPEC.md y mira el código actual. Implementa la pantalla Shopping y el botón del detalle de receta. En el detalle, añade el botón "Add missing to shopping list", visible solo si faltan ingredientes: al pulsarlo se añaden a la lista de la compra los ingredientes faltantes con su faltante como cantidad, y se muestra el aviso "Added to the shopping list". Si un ingrediente ya está en la lista sin comprar, se suma la cantidad en la misma línea (no se duplica). En Shopping, una lista con cantidad y unidad y una casilla para marcar como comprado; los comprados se muestran tachados y al final. Si no hay nada, muestra "Nothing to buy". Usa los textos exactos de SPEC.md. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

Cierra y vuelve a abrir la app antes de empezar, para que la lista de la compra esté vacía. Si pulsas el botón más de una vez en la misma receta, las cantidades se siguen sumando: es lo esperado.

- [ ]  En "Baratie Ramen", pulsar el botón muestra el aviso y en **Shopping** aparecen "Wheat noodles · 200 g" y "Fish stock · 500 ml"
- [ ]  Añadir también los faltantes del "Thousand Sunny Stew" deja "Fish stock · 800 ml" en **una sola línea**
- [ ]  Marcar "Wheat noodles" como comprado lo muestra tachado y al final
- [ ]  En "Sanji's Salmon Onigiri" (disponible) el botón no aparece

## Si te atascas

```
Revisa tu implementación contra la comprobación de este hito, sobre todo que las cantidades repetidas se sumen en una sola línea.
```

