# Set Sail to the Grand Line — Preparación previa

Oct 26, 2026 · @Gema

## Qué vamos a hacer

Para aprovechar el workshop del 7 de noviembre tienes que llegar con tres cosas funcionando: **Android CLI**, **un agente de IA en la terminal** y **un emulador** (o un móvil con depuración USB). Reserva un rato tranquilo: casi todo el tiempo son descargas.

No hace falta que crees ningún proyecto. Lo construiremos juntos desde cero durante el workshop, y las instrucciones valen sea cual sea el agente que elijas.

## Lo que necesitas

- Un portátil con macOS, Linux o Windows y buena conexión: se descargan varios GB.
- [Android Studio](https://developer.android.com/studio) en su versión estable, abierto al menos una vez para que termine de descargar el SDK de Android. Lo usaremos para el emulador y para abrir el proyecto al final.
- Una cuenta para el agente que elijas (por ejemplo, de Google para Antigravity CLI). Más abajo tienes las opciones.
- Si usas **Windows**, lee los avisos del Paso 1: hay dos limitaciones conocidas en este momento.

## Paso 1 · Instalar Android CLI

1. Descarga Android CLI desde la [página oficial](https://developer.android.com/tools/agents) y sigue las instrucciones para tu sistema.
2. Abre una terminal nueva y actualiza a la última versión:

```
android update
```

3. Comprueba que funciona:

```
android -V
android info
```

`android info` te dice qué SDK de Android está usando.

**Comprueba también que Java está en el PATH.** Algunas funciones de Android CLI y el script `gradlew` de los proyectos lo necesitan. Ejecuta en una terminal nueva:

```
java -version
```

Si no lo reconoce, instala un JDK o añade al PATH el que incluye Android Studio, y define la variable `JAVA_HOME` apuntando a él. Después abre otra terminal y repite la comprobación.

**Comprueba también `adb`.** El agente lo usa para manejar la app en el emulador durante los journeys. Ejecuta:

```
adb version
```

Si no lo reconoce, está en la carpeta `platform-tools` de tu SDK (la ruta del SDK te la da `android info`). Añádela al PATH, abre otra terminal y repite la comprobación.

**Avisos para Windows** (según la [documentación oficial](https://developer.android.com/tools/agents/android-cli)): por ahora no se admite descargar Android CLI desde PowerShell, y el comando `android emulator` está desactivado. En ese caso crea el emulador desde Android Studio (Device Manager) o usa un móvil con depuración USB.

## Paso 2 · Elegir e instalar un agente

**Si ya tienes instalado un agente de línea de comandos con suscripción, sáltate este paso.** Es solo para quienes no tienen suscripción y no usan ningún agente actualmente.

Elige **uno solo**. Para seguir el workshop sirve cualquiera de estos; si no quieres pagar, las opciones gratuitas son Antigravity CLI y OpenCode.

| Agente | Coste | Qué tener en cuenta |
| --- | --- | --- |
| Antigravity CLI (`agy`) | Gratis con cuenta de Google, con cuota semanal limitada | Es el sustituto de Gemini CLI. La cuota gratuita es más ajustada que la antigua; [Google no publica cifras exactas](https://www.cloudzero.com/blog/google-antigravity-pricing/). |
| OpenCode | Gratis con los modelos incluidos (OpenCode Zen); también acepta tu propia clave | Los [modelos gratuitos](https://www.desarrollolibre.net/blog/ia/opencode-complete-guide-to-the-code-agent-with-artificial-intelligence) tienen límites, rotan y pueden ir más lentos. |
| Claude Code | De pago (suscripción de Claude o clave de API) | No tiene plan gratuito. |
| GitHub Copilot CLI | Incluido en Copilot Free, con uso mensual muy limitado | Desde junio de 2026 se factura por créditos de IA; con el plan gratuito el límite es bajo. |
| Gemini CLI | Ya no es gratuito con cuenta personal de Google desde el 18 de junio de 2026 | [Google lo ha sustituido](https://github.com/google-gemini/gemini-cli/discussions/28017) por Antigravity CLI. |

### Instalar Antigravity CLI

```
# macOS / Linux
curl -fsSL https://antigravity.google/cli/install.sh | bash

# Windows (PowerShell)
irm https://antigravity.google/cli/install.ps1 | iex
```

Ejecuta `agy` e inicia sesión con tu cuenta de Google. Dentro de la sesión, `/usage` te muestra cuánta cuota te queda.

### Instalar OpenCode

```
curl -fsSL https://opencode.ai/install | sh
```

Ejecuta `opencode` y escribe `/models` para ver los modelos gratuitos disponibles. En Windows, sigue la documentación oficial de OpenCode.

### Claude Code o Copilot CLI

Sigue la guía oficial de instalación de cada herramienta e inicia sesión con tu cuenta.

**Consejo:** con un plan gratuito, haz una única prueba corta y no gastes cuota los días previos.

## Paso 3 · Preparar un emulador

Primero descarga la plataforma de Android 16 (API 36) y la imagen del sistema para el emulador. Son varios GB, así que es lo que más tarda: hazlo con tiempo y buena conexión.

```
android sdk install platforms/android-36
android sdk install system-images/android-36/google_apis/<arquitectura>
```

Sustituye `<arquitectura>` según tu equipo:

- `arm64-v8a`: Mac con chip Apple (M1 o posterior) y portátiles con procesador ARM.
- `x86_64`: Mac con procesador Intel y la mayoría de equipos Windows y Linux.

Después, para el emulador, en macOS y Linux:

```
android emulator create
android emulator list
```

Arranca el dispositivo una vez con `android emulator start <nombre>` para comprobar que funciona. En Windows, créalo desde Android Studio (Device Manager).

## Paso 4 · Descargar la documentación y las skills

La primera vez que se usan, `android docs` y `android skills` descargan su índice y pueden tardar un par de minutos. Hazlo ahora para no esperar durante el workshop:

```
android docs search "navigation 3"
android skills list
```

Si la primera búsqueda se queda colgada o falla con un error de índice, espera a que termine, ciérrala y vuelve a ejecutarla.

## Comprobación final

Si puedes marcar todo esto, estás listo:

- [ ] `android -V` muestra una versión.
- [ ] `android info` indica la ruta de tu SDK de Android.
- [ ] `java -version` y `adb version` funcionan en una terminal nueva.
- [ ] `android docs search "navigation 3"` y `android skills list` devuelven resultados.
- [ ] Tu agente arranca y has iniciado sesión.
- [ ] La plataforma de Android 16 está instalada: `android sdk list` muestra `platforms/android-36`.
- [ ] Un emulador arranca, o tienes un móvil con depuración USB.
- [ ] Prueba con el agente: en una carpeta vacía, pídele «Ejecuta `android --help` y dime en una frase qué puede hacer». Si lo ejecuta y te contesta, todo está bien conectado.

## Problemas frecuentes

| Síntoma | Qué probar |
| --- | --- |
| `android: command not found` | Cierra y abre la terminal. Si sigue igual, comprueba que la carpeta de instalación está en tu PATH. |
| Windows: falla la descarga desde PowerShell o `android emulator` no funciona | Son limitaciones conocidas. Descarga desde la página oficial y crea el emulador desde Android Studio. |
| El emulador va muy lento, la app se queda colgada o aparece «La aplicación no responde» | Suele ser falta de memoria: los emuladores nuevos traen solo 2 GB de RAM. Cierra aplicaciones pesadas, reinicia el emulador (`android emulator stop <nombre>` y después `android emulator start <nombre>`) y vuelve a probar. |
| El agente dice que has alcanzado la cuota | Espera a que se renueve (en Antigravity es semanal) o prueba con otro agente. |
| Cualquier otro error | Copia el mensaje completo y mándamelo antes del workshop, así lo resolvemos con calma. |
