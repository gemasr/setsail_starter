## Objetivo

Ver qué recetas se pueden preparar y qué ingredientes faltan.

## Prompt

```
Lee SPEC.md y mira el código actual. Implementa la pantalla Recipes y la pantalla de detalle de receta. En Recipes, una lista de tarjetas con el nombre, la descripción corta y una etiqueta: "Available" si todos los ingredientes están en la despensa en cantidad suficiente, o "Missing N ingredients" ("Missing 1 ingredient" en singular) si no. La etiqueta se actualiza al cambiar la despensa. Tocar una receta abre su detalle, con flecha de volver: nombre, descripción, la misma etiqueta, la sección "Ingredients" (cada línea con cantidad y unidad; los que faltan, resaltados con color y con texto, indicando el faltante, por ejemplo "Chicken · 500 g (missing 500 g)") y la sección "Steps" como lista numerada. Todavía no añadas el botón de añadir a la compra. Usa los textos exactos de SPEC.md. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

- [ ]  Hay 6 recetas; "Sanji's Salmon Onigiri" y "Going Merry Potato Omelette" muestran **Available**
- [ ]  "Thousand Sunny Stew" muestra **Missing 3 ingredients**
- [ ]  En "Luffy's Giant Meat" se ve el pollo resaltado con "missing 500 g"
- [ ]  Si añades "Cream" 250 en la despensa, "Mellorine for Nami and Robin" pasa a **Available**

## Resultado esperado con los datos iniciales

| Receta | Estado | Faltantes |
| --- | --- | --- |
| Sanji's Salmon Onigiri | Available | n/a |
| Going Merry Potato Omelette | Available | n/a |
| Luffy's Giant Meat | Missing 1 ingredient | Chicken 500 g |
| Mellorine for Nami and Robin | Missing 1 ingredient | Cream 250 ml |
| Baratie Ramen | Missing 2 ingredients | Wheat noodles 200 g, Fish stock 500 ml |
| Thousand Sunny Stew | Missing 3 ingredients | Pork 400 g, Carrot 3 pcs, Fish stock 300 ml |

## Si te atascas

```
Revisa tu implementación contra la tabla de resultado esperado y corrige las diferencias.
```