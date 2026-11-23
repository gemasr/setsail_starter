## Objetivo

Instalar la skill de Android CLI, crear el proyecto Android y dejarlo compilando y ejecutándose en el emulador.

## Antes del prompt

El agente necesita leer `AGENTS.md` para saber cómo trabajar y necesita la skill `android-cli` para saber cómo usar Android CLI, así que ambas tienen que estar listas antes de lanzar el prompt.

1. Ejecuta `android init` en una terminal. Configura Android CLI e instala la skill `android-cli` para tu agente.
2. Crea una carpeta vacía llamada `SanjisGalley`.
3. Copia dentro `AGENTS.md` (de la carpeta `util` del starter) y `SPEC.md` (de la carpeta `es`).
4. Abre el agente en esa carpeta.

## Prompt

```
Crea un proyecto Android nuevo con Android CLI siguiendo las convenciones de AGENTS.md. Llámalo SanjisGalley y créalo en esta misma carpeta, conservando AGENTS.md y SPEC.md. Usa Android 16 (API 36) como compileSdk y targetSdk. Cuando termines, compílalo, ejecútalo en el emulador usando Android CLI y dime qué has verificado.
```

## Comprobación

- [ ]  `AGENTS.md` y `SPEC.md` siguen en la raíz del proyecto
- [ ]  El proyecto compila
- [ ]  Se ejecuta en el emulador y muestra la pantalla inicial

## Si te atascas

Pide al agente:

```
Compila y dime qué falla.
```
