## Objetivo

Comprobar la app con journeys que describen lo que hace una persona usuaria. En este hito el agente ejecuta un journey que ya está escrito y después puedes pedirle que escriba los suyos: fíjate en qué comandos de Android CLI usa para recorrer la app y cómo cuenta el resultado.

Los journeys se guardan en la carpeta `journeys/` de la raíz del proyecto, como indica `AGENTS.md`.

Verás que los pasos del XML están en inglés (`Tap`, `Verify`...) aunque los textos de la app estén en español. Es el formato que usa Android CLI: las acciones que empiezan por `Check` o `Verify` se tratan como comprobaciones, y el resto como interacciones.

## Antes del prompt

Empieza desde el checkpoint del Hito 4, que ya incluye el journey del nivel 1 en `journeys/`:

1. Descarga [dv-mad-step-4.zip](https://github.com/gemasr/sanjis_galley/archive/refs/tags/dv-mad-step-4.zip) y descomprímelo en una **carpeta nueva**.
2. Abre el agente en esa carpeta, en una **sesión nueva**.

No existe ningún comando de `android` que ejecute un journey por sí solo: el agente lee el XML y recorre la app con `android input`, `android layout` y `android screen capture`, como explica la skill `android-cli`.

## Nivel 1: ejecutar un journey (obligatorio)

Abre `journeys/ramen-faltantes-a-la-compra.xml` y léelo antes: es XML normal.

```
Ejecuta el journey de journeys/ramen-faltantes-a-la-compra.xml usando Android CLI y cuéntame el resultado. Enséñame qué comandos de Android CLI has usado en cada paso.
```

## Nivel 2 (opcional): comprobar un cambio de estado

```
Escribe un journey que compruebe lo siguiente y ejecútalo: al añadir 250 ml de nata a la despensa, la receta "Mellorine para Nami y Robin" pasa de "Falta 1 ingrediente" a "Disponible". Usa Android CLI para ejecutarlo.
```

## Nivel 3 (opcional): el caso difícil

```
Escribe y ejecuta un journey que compruebe lo siguiente: añado a la compra los faltantes de "Ramen del Baratie" y luego los de "Guiso del Thousand Sunny"; en Compra debe aparecer "Caldo de pescado · 800 ml" en una sola línea. Usa Android CLI para ejecutarlo.
```

Este es el que más suele fallar a la primera: las cantidades repetidas deben sumarse en una sola línea.

## Comprobación

- [ ]  El nivel 1 se ejecuta y pasa
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
