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

**1. Sanji's Salmon Onigiri**: *Rice balls stuffed with salmon, perfect for the road.*
- Ingredientes: Rice 300 g, Salmon 150 g, Nori seaweed 3 pcs
- Pasos: 1) Cook the rice and let it cool slightly. 2) Pan-sear the salmon and flake it. 3) Shape the rice balls with a little salmon in the center. 4) Wrap them with the nori seaweed.

**2. Going Merry Potato Omelette**: *Juicy omelette with potato and onion.*
- Ingredientes: Egg 4 pcs, Potato 2 pcs, Onion 1 pcs
- Pasos: 1) Peel the potato and onion and slice them thinly. 2) Slowly poach the potato and onion over low heat. 3) Beat the eggs and mix them with the potatoes. 4) Set the omelette on both sides.

**3. Luffy's Giant Meat**: *Glazed chicken in abundance, just how the captain likes it.*
- Ingredientes: Chicken 500 g, Soy sauce 50 ml, Onion 1 pcs
- Pasos: 1) Marinate the chicken with the soy sauce. 2) Brown the chicken with the chopped onion. 3) Cook over medium heat until glazed.

**4. Baratie Ramen**: *Ramen with fish stock and egg.*
- Ingredientes: Wheat noodles 200 g, Fish stock 500 ml, Egg 2 pcs, Onion 1 pcs, Soy sauce 20 ml
- Pasos: 1) Heat the stock with the soy sauce. 2) Cook the noodles separately and drain them. 3) Boil the eggs for 7 minutes and peel them. 4) Assemble the bowl with noodles, stock, egg and chopped onion.

**5. Thousand Sunny Stew**: *Pork, potato and carrot stew for the whole crew.*
- Ingredientes: Pork 400 g, Potato 2 pcs, Carrot 3 pcs, Onion 1 pcs, Fish stock 300 ml
- Pasos: 1) Brown the chopped pork with the onion. 2) Add the diced potato and carrot. 3) Cover with the fish stock. 4) Simmer until everything is tender.

**6. Mellorine for Nami and Robin**: *Creamy ice cream, served with a Sanji pose.*
- Ingredientes: Milk 500 ml, Cream 250 ml, Sugar 100 g, Egg 3 pcs
- Pasos: 1) Heat the milk with the cream without letting it boil. 2) Beat the yolks with the sugar and mix them into the hot milk. 3) Cook, stirring, until thickened, then let it cool. 4) Freeze, stirring every 30 minutes.
