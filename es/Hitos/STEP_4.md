## Objetivo

Comprobar la app con journeys que describen lo que hace una persona usuaria. En este hito el agente escribe los journeys y los ejecuta: fíjate en cómo los redacta, qué comandos de Android CLI usa para recorrer la app y cómo cuenta el resultado.

Los journeys se guardan en la carpeta `journeys/` de la raíz del proyecto, como indica `AGENTS.md`.

Los pasos que empiezan por `Check` o `Verify` son comprobaciones; el resto, interacciones.

## Antes del prompt

Empieza desde el checkpoint del Hito 4 (la app, todavía sin journeys):

1. Descarga [dv-mad-step-4.zip](https://github.com/gemasr/sanjis_galley/archive/refs/tags/dv-mad-step-4.zip) y descomprímelo en una **carpeta nueva**.
2. Abre el agente en esa carpeta, en una **sesión nueva**.

No existe ningún comando de `android` que ejecute un journey por sí solo: el agente lee el XML y recorre la app con `android input`, `android layout` y `android screen capture`, como explica la skill `android-cli`.

## Nivel 1: un journey sencillo (obligatorio)

```
Escribe un journey que compruebe lo siguiente y ejecútalo: en la receta "Baratie Ramen", al pulsar "Add missing to shopping list", aparece el aviso "Added to the shopping list" y en Shopping aparecen "Wheat noodles · 200 g" y "Fish stock · 500 ml". Guárdalo en journeys/, usa Android CLI para ejecutarlo y cuéntame el resultado.
```

Abre el journey que el agente guardó en `journeys/`: es XML normal.

## Nivel 2 (opcional): comprobar un cambio de estado

```
Escribe un journey que compruebe lo siguiente y ejecútalo: al añadir 250 ml de nata a la despensa, la receta "Mellorine for Nami and Robin" pasa de "Missing 1 ingredient" a "Available". Usa Android CLI para ejecutarlo.
```

## Nivel 3 (opcional): el caso difícil

```
Escribe y ejecuta un journey que compruebe lo siguiente: añado a la compra los faltantes de "Baratie Ramen" y luego los de "Thousand Sunny Stew"; en Shopping debe aparecer "Fish stock · 800 ml" en una sola línea. Usa Android CLI para ejecutarlo.
```

Este es el que más suele fallar a la primera: las cantidades repetidas deben sumarse en una sola línea.

## Comprobación

- [ ]  Hay un journey del nivel 1 en `journeys/` y pasa
- [ ]  Sabes decir qué comandos de Android CLI usó el agente en cada paso
- [ ]  Si hiciste los niveles 2 y 3, hay un journey en `journeys/` por cada uno y pasan
- [ ]  Si falla, pide al agente que explique por qué y lo corrija

## Si te atascas

```
Muéstrame qué paso del journey falla y por qué.
```

Si un paso falla porque el selector coincide con varios elementos (por ejemplo, un texto que aparece en un título y en un botón), pídele al agente:

```
Usa un selector más concreto, o comprueba ese paso con una captura de pantalla.
```
