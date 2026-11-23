## Objetivo

Encontrar un fallo visual dejando que el agente mire la app con `android layout` y `android screen capture`.

## Antes del prompt

A partir de aquí la app ya está construida: empiezas desde un checkpoint en lugar de escribir tú las pantallas de Pantry, Recipes y Shopping.

1. Descarga el checkpoint del Hito 3: [dv-mad-step-3.zip](https://github.com/gemasr/sanjis_galley/archive/refs/tags/dv-mad-step-3.zip).
2. Descomprímelo en una **carpeta nueva**. No reutilices la de los hitos anteriores.
3. Abre el agente en esa carpeta, en una **sesión nueva**. La carpeta ya contiene `AGENTS.md` y `SPEC.md`.
4. Compílala y ejecútala en el emulador, con el agente o con `android run`.

## El síntoma

Abre la pestaña **Pantry**. El botón "Add ingredient" no aparece por ningún lado, así que no puedes añadir nada, y el primer elemento de la lista se dibuja encima de la barra de estado. La app compila y no se cierra, así que no hay ningún mensaje de error que leer.

No te contamos la causa. La idea es que el agente la encuentre mirando la pantalla.

## Prompt

```
En la pantalla Pantry el botón "Add ingredient" no se ve y la lista empieza bajo la barra de estado. Usa android layout y android screen capture para ver cómo se muestra la pantalla en el emulador, averigua por qué, corrígelo y comprueba el resultado con los mismos comandos. Cuéntame qué has encontrado y qué has cambiado.
```

## Comprobación

- [ ]  El agente usó `android layout` y `android screen capture` antes de tocar el código
- [ ]  El agente explica la causa con sus palabras
- [ ]  En Pantry, el botón "Add ingredient" se ve y la lista empieza bajo la barra de estado
- [ ]  El resto de la app sigue funcionando

## Si te atascas

```
Muéstrame el layout y la captura que estás mirando, y dime qué ves en ellos.
```

Si te quedas sin cuota, o quieres comparar, la solución está en la rama [dv-mad-step-3-solution](https://github.com/gemasr/sanjis_galley/compare/dv-mad-step-3...dv-mad-step-3-solution). Descarga su zip, o aplica el diff, y pasa al siguiente hito.
