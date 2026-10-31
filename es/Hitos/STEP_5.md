## Objetivo

Convertir lo que falta en una lista de la compra.

## Prompt

```
Lee SPEC.md y mira el código actual. Implementa la pantalla Compra y el botón del detalle de receta. En el detalle, añade el botón "Añadir faltantes a la compra", visible solo si faltan ingredientes: al pulsarlo se añaden a la lista de la compra los ingredientes faltantes con su faltante como cantidad, y se muestra el aviso "Añadido a la lista de la compra". Si un ingrediente ya está en la lista sin comprar, se suma la cantidad en la misma línea (no se duplica). En Compra, una lista con cantidad y unidad y una casilla para marcar como comprado; los comprados se muestran tachados y al final. Si no hay nada, muestra "No hay nada que comprar". Usa los textos exactos de SPEC.md. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

Cierra y vuelve a abrir la app antes de empezar, para que la lista de la compra esté vacía. Si pulsas el botón más de una vez en la misma receta, las cantidades se siguen sumando: es lo esperado.

- [ ]  En "Ramen del Baratie", pulsar el botón muestra el aviso y en **Compra** aparecen "Fideos de trigo · 200 g" y "Caldo de pescado · 500 ml"
- [ ]  Añadir también los faltantes del "Guiso del Thousand Sunny" deja "Caldo de pescado · 800 ml" en **una sola línea**
- [ ]  Marcar "Fideos de trigo" como comprado lo muestra tachado y al final
- [ ]  En "Onigiri de salmón de Sanji" (disponible) el botón no aparece

## Extra opcional

```
Añade en Compra el botón "Pasar comprados a la despensa": suma esas cantidades a la despensa y los quita de la lista.
```

## Si te atascas

```
Revisa tu implementación contra la comprobación de este hito, sobre todo que las cantidades repetidas se sumen en una sola línea.
```

