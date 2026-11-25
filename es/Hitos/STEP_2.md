## Objetivo

Ver cómo el agente busca e instala una skill para tener conocimiento actualizado, y cómo la usa para montar el esqueleto de navegación de la app.

## Antes del prompt

El agente necesita la skill `navigation-3`, que le enseña a configurar bien Jetpack Navigation 3. **No la instales tú**: el prompt le pide que la busque y la instale con Android CLI.

Abre el agente en la carpeta del proyecto, en una **sesión nueva**.

## Prompt

```
Busca con Android CLI una skill para Navigation 3. Si no la tienes instalada, instálala. Lee la skill y úsala. Mira el código actual del proyecto y monta el esqueleto de la app: barra de navegación inferior con tres destinos (Pantry, Recipes, Shopping), en ese orden, cada uno con una pantalla provisional que muestre solo su título. El destino inicial es Recipes. Usa los textos exactos de SPEC.md. No implementes nada más. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

- [ ]  El agente buscó la skill con `android skills find`
- [ ]  El agente instaló `navigation-3` con `android skills add`, o comprobó que ya la tenía
- [ ]  El agente leyó la skill antes de escribir código
- [ ]  La app compila y abre en **Recipes**
- [ ]  Puedes navegar entre **Pantry**, **Recipes** y **Shopping**

## Si te atascas

```
Revisa tu implementación contra el prompt del hito y dime qué falta.
```
