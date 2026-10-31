## Objetivo

Comprobar la app con journeys que describen lo que hace una persona usuaria. En este hito el agente escribe los journeys y los ejecuta: fíjate en cómo los redacta, qué comandos de Android CLI usa para recorrer la app y cómo cuenta el resultado.

Los journeys se guardan en la carpeta `journeys/` de la raíz del proyecto, como indica `AGENTS.md`.

Verás que los pasos del XML están en inglés (`Tap`, `Verify`...) aunque los textos de la app estén en español. Es el formato que usa Android CLI: las acciones que empiezan por `Check` o `Verify` se tratan como comprobaciones, y el resto como interacciones.

## Nivel 1: un journey sencillo

```
Escribe un journey que compruebe lo siguiente y ejecútalo: en la receta "Ramen del Baratie", al pulsar "Añadir faltantes a la compra", aparece el aviso "Añadido a la lista de la compra" y en Compra aparecen "Fideos de trigo · 200 g" y "Caldo de pescado · 500 ml". Guárdalo en journeys/, usa Android CLI para ejecutarlo y cuéntame el resultado.
```

## Nivel 2: comprobar un cambio de estado

```
Escribe un journey que compruebe lo siguiente y ejecútalo: al añadir 250 ml de nata a la despensa, la receta "Mellorine para Nami y Robin" pasa de "Falta 1 ingrediente" a "Disponible". Usa Android CLI para ejecutarlo.
```

## Nivel 3: el caso difícil

```
Escribe y ejecuta un journey que compruebe lo siguiente: añado a la compra los faltantes de "Ramen del Baratie" y luego los de "Guiso del Thousand Sunny"; en Compra debe aparecer "Caldo de pescado · 800 ml" en una sola línea. Usa Android CLI para ejecutarlo.
```

Este es el que más suele fallar a la primera: las cantidades repetidas deben sumarse en una sola línea.

## Comprobación

- [ ]  Hay un journey en `journeys/` por cada nivel
- [ ]  Los journeys se ejecutan y pasan
- [ ]  Si falla, pide al agente que explique por qué y lo corrija

## Si te atascas

```
Muéstrame qué paso del journey falla y por qué.
```

Si un paso falla porque el selector coincide con varios elementos (por ejemplo, un texto que aparece en un título y en un botón), pídele al agente:

```
Usa un selector más concreto, o comprueba ese paso con una captura de pantalla.
```
