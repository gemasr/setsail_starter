## Objetivo

Dar al agente conocimiento actualizado con una skill y usarla para montar el esqueleto de navegación de la app.

## Antes del prompt

El agente usará la skill `navigation-3`, que le enseña a configurar bien Jetpack Navigation 3.

1. Comprueba que la skill está instalada:

   ```
   android skills list
   ```

2. Si `navigation-3` no aparece en la lista, instálala:

   ```
   android skills add navigation-3
   ```

3. Abre el agente en la carpeta del proyecto, en una **sesión nueva**.

## Prompt

```
Usa la skill navigation-3. Mira el código actual del proyecto y monta el esqueleto de la app: barra de navegación inferior con tres destinos (Pantry, Recipes, Shopping), en ese orden, cada uno con una pantalla provisional que muestre solo su título. El destino inicial es Recipes. Usa los textos exactos de SPEC.md. No implementes nada más. Cuando termines, compila, ejecútala en el emulador y comprueba la pantalla usando Android CLI, y dime qué has verificado.
```

## Comprobación

- [ ]  El agente dice que ha usado la skill `navigation-3`
- [ ]  La app compila y abre en **Recipes**
- [ ]  Puedes navegar entre **Pantry**, **Recipes** y **Shopping**

## Si te atascas

```
Revisa tu implementación contra el prompt del hito y dime qué falta.
```
