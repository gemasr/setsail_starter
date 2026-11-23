# Sanji's Galley: "¿Qué puedo cocinar hoy?"

Una app de cocina para el cocinero del Thousand Sunny. Muestra lo que hay en la despensa, qué recetas se pueden preparar con lo que hay y construye una lista de la compra con lo que falta. Los datos viven en memoria y se cargan desde los datos de ejemplo al arrancar la app.

> Para el agente: este documento es la fuente de verdad para los datos, las reglas y los textos. Implementa solo lo que se te pida en cada momento; no adelantes trabajo de otros pasos. Los textos visibles de la app están en inglés; el código (clases, variables, paquetes) sigue en inglés según AGENTS.md.

## Modelo de datos

| Entidad | Campos |
|---|---|
| `Ingredient` | `id`, `name`, `unit` (`g`, `ml` o `pcs`) |
| `PantryItem` | `ingredient`, `quantity` (número > 0) |
| `Recipe` | `id`, `name`, `description` (una línea), `steps` (lista ordenada), `ingredients` (ingrediente + cantidad necesaria) |
| `ShoppingItem` | `ingredient`, `quantity` (a comprar), `purchased` (sí/no) |

## Reglas de negocio
- Ingrediente disponible para una receta: la cantidad en la despensa es mayor o igual que la cantidad necesaria (si no está en la despensa, es 0).
- Receta disponible: todos sus ingredientes están disponibles.
- Faltante de un ingrediente: cantidad necesaria menos cantidad en la despensa, solo si es positivo.
- Añadir faltantes a la compra: por cada ingrediente con faltante, añade un ShoppingItem con esa cantidad. Si el ingrediente ya está en la lista (sin comprar), suma la cantidad a esa línea en vez de crear una duplicada.
- La despensa no puede tener dos líneas del mismo ingrediente: añadir uno existente suma a su cantidad.

## Textos de la UI (exactos)

| Elemento | Texto |
|---|---|
| Destinos de navegación | `Pantry`, `Recipes`, `Shopping` |
| Añadir a la despensa | `Add ingredient`, `Save` |
| Etiquetas del formulario | `Ingredient`, `Quantity` |
| Etiqueta de disponible | `Available` |
| Etiqueta de faltantes | `Missing N ingredients` / `Missing 1 ingredient` |
| Botón del detalle | `Add missing to shopping list` |
| Aviso tras añadir | `Added to the shopping list` |
| Estados vacíos | `The pantry is empty`, `Nothing to buy` |
| Secciones del detalle de receta | `Ingredients`, `Steps` |
| Accesibilidad | `Back` (descripción de la flecha de volver) |
| Opcional | `Move purchased to pantry` |

Formato de cantidades: `Nombre · cantidad unidad`, por ejemplo `Egg · 6 pcs` o `Rice · 1000 g`. En el detalle de una receta, un ingrediente que falta se muestra como `Chicken · 500 g (missing 500 g)`.

## Datos de ejemplo

### Ingredientes
| id | Nombre | Unidad |
|---|---|---|
| egg | Egg | pcs |
| rice | Rice | g |
| nori | Nori seaweed | pcs |
| salmon | Salmon | g |
| chicken | Chicken | g |
| pork | Pork | g |
| onion | Onion | pcs |
| carrot | Carrot | pcs |
| potato | Potato | pcs |
| soy | Soy sauce | ml |
| noodles | Wheat noodles | g |
| stock | Fish stock | ml |
| milk | Milk | ml |
| cream | Cream | ml |
| sugar | Sugar | g |

### Despensa inicial
| Ingrediente | Cantidad |
|---|---|
| Egg | 6 |
| Rice | 1000 |
| Nori seaweed | 10 |
| Salmon | 200 |
| Onion | 3 |
| Potato | 4 |
| Soy sauce | 200 |
| Milk | 1000 |
| Sugar | 500 |

(No hay pollo, cerdo, zanahoria, fideos, caldo de pescado ni nata.)

### Recetas

Las seis recetas de ejemplo (con sus ingredientes y pasos) están en `SAMPLE_RECIPES.md`. Lee ese archivo solo cuando te pidan implementar las recetas o los datos de ejemplo; no lo necesitas para nada más.
