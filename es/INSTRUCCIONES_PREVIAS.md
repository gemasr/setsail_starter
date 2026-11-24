# Set Sail for the Grand Line — Preparación previa

Llega con tres cosas funcionando: **Android CLI**, **un agente de IA en la terminal** y **un emulador** (o un móvil con depuración USB).

- **Tiempo:** unos 30–40 minutos, casi todo descargas (varios GB). Usa una buena conexión.
- **No crees ningún proyecto:** lo haremos juntos en el workshop.
- **¿Ya tienes algo instalado?** Sáltate ese paso.

> **Windows:** instala Android CLI con `winget install --id Google.AndroidCLI` o con el instalador de la [página oficial](https://developer.android.com/tools/agents).

## 1. Instalar Android Studio y Android CLI

1. Instala [Android Studio](https://developer.android.com/studio) (estable) y **ábrelo una vez**: el asistente de configuración descarga el SDK de Android.
2. Instala Android CLI desde la [página oficial](https://developer.android.com/tools/agents).
3. En una **terminal nueva**:

```
android update
android -V && java -version && adb version
```

✅ Deberías ver tres versiones. Si falla `java` o `adb`, mira [Problemas frecuentes](#problemas-frecuentes).

## 2. Instalar un agente de IA

**¿Ya usas un agente de línea de comandos (Claude Code, Copilot CLI…)? Sáltate este paso.**

¿Sin agente? Instala Antigravity CLI, que es gratis con una cuenta de Google:

```
# macOS / Linux
curl -fsSL https://antigravity.google/cli/install.sh | bash

# Windows (PowerShell)
irm https://antigravity.google/cli/install.ps1 | iex
```

Después ejecuta `agy` e inicia sesión con tu cuenta de Google.

✅ El agente arranca y has iniciado sesión.

Otras opciones, costes y cuota: mira el [apéndice](#apéndice-agentes-y-cuota).

## 3. Descargas pesadas (lánzalas y déjalas correr)

**3.1 · Emulador, desde Android Studio.** Abre **Device Manager → Create Device**, elige un teléfono y selecciona la imagen **Android 16 (API 36)** con Google APIs (Studio la descarga por ti). Después arráncalo con ▶.

✅ El emulador arranca. Puedes usar un móvil con depuración USB en su lugar.

**3.2 · Calentar Gradle** (opcional, recomendado: ahorra varios minutos en el Hito 1). Después borra la carpeta `WarmUp`:

```
android create --name WarmUp --output WarmUp
cd WarmUp
./gradlew assembleDebug        # Windows: gradlew.bat assembleDebug
```

## 4. Comprobación final

En una terminal nueva:

```
android info
android emulator list
```

Estás listo si:

- [ ] `android info` muestra la ruta de tu SDK.
- [ ] `android emulator list` muestra tu emulador.

## Problemas frecuentes

| Síntoma | Qué probar |
| --- | --- |
| `android: command not found` | Cierra y abre la terminal. Si sigue igual, añade al PATH la carpeta de instalación de Android CLI. |
| `java: command not found` | Instala un JDK, o añade al PATH el que incluye Android Studio y define `JAVA_HOME` apuntando a él. Abre una terminal nueva. |
| `adb: command not found` | Añade al PATH la carpeta `platform-tools` de tu SDK (`android info` te da la ruta). Abre una terminal nueva. |
| El emulador va muy lento o aparece «La aplicación no responde» | Falta de memoria. Cierra aplicaciones pesadas, luego `android emulator stop <nombre>` y `android emulator start <nombre>`. |
| El agente dice que has alcanzado la cuota | Espera a que se renueve (en Antigravity es semanal) o prueba con otro agente. |
| Cualquier otro error | Copia el mensaje completo y envíalo a la organización antes del workshop, para que te pongan en contacto conmigo y lo resolvamos con calma. |

## Apéndice: agentes y cuota

Sirve cualquier agente que funcione desde la consola. Este workshop solo se ha probado con **Copilot CLI, Claude Code y Antigravity CLI**; con otros puede que algo no funcione igual.

| Agente | Coste | Qué tener en cuenta |
| --- | --- | --- |
| Antigravity CLI (`agy`) | Gratis con cuenta de Google, con cuota semanal limitada | Es el sustituto de Gemini CLI. La cuota gratuita es más ajustada que la antigua; [Google no publica cifras exactas](https://www.cloudzero.com/blog/google-antigravity-pricing/). Dentro de la sesión, `/usage` muestra lo que te queda. |
| OpenCode | Gratis con los modelos incluidos (OpenCode Zen); también acepta tu propia clave | Los [modelos gratuitos](https://www.desarrollolibre.net/blog/ia/opencode-complete-guide-to-the-code-agent-with-artificial-intelligence) tienen límites, rotan y pueden ir más lentos. Instalación: `curl -fsSL https://opencode.ai/install \| sh`, luego `opencode` y `/models`. En Windows, sigue su documentación oficial. |
| Claude Code | De pago (suscripción de Claude o clave de API) | No tiene plan gratuito. Sigue su guía oficial de instalación. |
| GitHub Copilot CLI | Incluido en Copilot Free, con uso mensual muy limitado | Desde junio de 2026 se factura por créditos de IA; el límite gratuito es bajo. Sigue su guía oficial de instalación. |

**Con un plan gratuito:** haz una única prueba corta y no gastes cuota los días previos.

**Si se te acaba la cuota durante el workshop:** no tienes que empezar de nuevo. Los Hitos 3 y 4 parten de un checkpoint (un zip que descargas), así que puedes engancharte directamente.
