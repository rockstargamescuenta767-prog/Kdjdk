# Web TV — convierte cualquier página en app para TV box

## Cómo generar el APK
1. Instalá Android Studio (gratis) en una PC.
2. File > Open > elegí la carpeta `TVWebApp`. Esperá a que sincronice Gradle (si pide actualizar versiones, aceptá).
3. Build > Build APK(s). El archivo queda en `app/build/outputs/apk/debug/app-debug.apk`.
4. Pasalo al TV box por pendrive, o con `adb install app-debug.apk` si tenés el box en la red.
   (En el box hay que habilitar "Fuentes desconocidas" / "Instalar apps desconocidas").

## Uso
- La primera vez te pide la URL (por ejemplo `youtube.com/tv`). Se guarda y desde ahí abre directo esa página a pantalla completa.
- Cambiar la URL: tecla **Menú** del control, o **mantené apretado Atrás**.
- Atrás navega hacia atrás dentro de la página; si no hay historial, apretalo dos veces para salir.

## Para tener varias "apps" de distintas páginas
Cambiá `applicationId` en `app/build.gradle.kts` (por ejemplo `com.tvwebapp.netflix`) y el `app_name` en
`res/values/strings.xml`, y compilá otro APK. Cada uno se instala como app aparte.

## Limitaciones
- El control remoto navega con las flechas; las páginas pensadas para mouse pueden ser incómodas.
  Si te pasa, usá un mouse/teclado USB o Bluetooth, o una app de puntero para el box.
- Sitios con DRM (Netflix, Disney+, etc.) pueden no reproducir dentro de un WebView.
- 
