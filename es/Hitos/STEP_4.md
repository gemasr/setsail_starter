## Objetivo

Ver qué recetas se pueden preparar y qué ingredientes faltan.

## Prompt

```
Lee SPEC.md y mira el código actual. Implementa la pantalla Recetas y la pantalla de detalle de receta. En Recetas, una lista de tarjetas con el nombre, la descripción corta y una etiqueta: "Disponible" si todos los ingredientes están en la despensa en cantidad suficiente, o "Faltan N ingredientes" ("Falta 1 ingrediente" en singular) si no. La etiqueta se actualiza al cambiar la despensa. Tocar una receta abre su detalle, con flecha de volver: nombre, descripción, la misma etiqueta, la sección "Ingredientes" (cada línea con cantidad y unidad; los que faltan, resaltados con color y con texto, indicando el faltante, por ejemplo "Pollo · 500 g (faltan 500 g)") y la sección "Pasos" como lista numerada. Todavía no añadas el botón de añadir a la compra. Usa los textos exactos de SPEC.md. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

- [ ]  Hay 6 recetas; "Onigiri de salmón de Sanji" y "Tortilla del Going Merry" muestran **Disponible**
- [ ]  "Guiso del Thousand Sunny" muestra **Faltan 3 ingredientes**
- [ ]  En "Carne a lo grande de Luffy" se ve el pollo resaltado con "faltan 500 g"
- [ ]  Si añades "Nata" 250 en la despensa, "Mellorine para Nami y Robin" pasa a **Disponible**

## Resultado esperado con los datos iniciales

| Receta | Estado | Faltantes |
| --- | --- | --- |
| Onigiri de salmón de Sanji | Disponible | n/a |
| Tortilla del Going Merry | Disponible | n/a |
| Carne a lo grande de Luffy | Falta 1 ingrediente | Pollo 500 g |
| Mellorine para Nami y Robin | Falta 1 ingrediente | Nata 250 ml |
| Ramen del Baratie | Faltan 2 ingredientes | Fideos 200 g, Caldo 500 ml |
| Guiso del Thousand Sunny | Faltan 3 ingredientes | Cerdo 400 g, Zanahoria 3 ud, Caldo 300 ml |

## Si te atascas

```
Revisa tu implementación contra la tabla de resultado esperado y corrige las diferencias.
```