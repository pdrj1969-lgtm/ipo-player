# iPod OS - Aplicación Nativa Android (Kotlin & Jetpack Compose)

Proyecto oficial de Android que implementa el reproductor iPod con acabado industrial y widgets idénticos al diseño de Google Stitch.

## Arquitectura del Proyecto

* **Interfaz de Usuario (UI)**:
  * **Jetpack Compose + Material3**: Renderizado de chasis de aluminio cepillado con degradados y tornillos en las esquinas.
  * **Click Wheel Rotativa**: Detección de gestos angulares (`atan2`) con respuesta háptica nativa (`Vibrator` / `HapticFeedbackConstants.CLOCK_TICK`).
  * **Doble Modo de Pantalla**:
    * **LCD Retro**: Pantalla dividida con rejilla matricial de píxeles, navegación jerárquica a la izquierda y preview de carátula/canciones a la derecha.
    * **OLED Oscuro**: Carátula en perspectiva 3D, badges `MIX`, `TODO`, `AAC 320k` y control de línea de tiempo.
* **Motor de Audio en Segundo Plano**:
  * **AndroidX Media3 (ExoPlayer + MediaSessionService)**:
    * Reproducción garantizada sin cortes con pantalla apagada o móvil bloqueado.
    * Controles estilizados en la pantalla de bloqueo y barra de notificaciones del sistema Android.
* **Carga Selectiva & Base de Datos**:
  * **Storage Access Framework (SAF)**: Selector para importar múltiples archivos sueltos a la vez o carpetas completas de álbumes/artistas.
  * **Room Database**: Almacenamiento persistente local de pistas, metadatos y carátulas.
* **Editor de Metadatos**:
  * Diálogo para editar título, artista, álbum, año, número de pista y asignar carátulas.
* **Widgets de Inicio**:
  * **Micro Wheel (2×2)** desarrollado con **Jetpack Glance**: Muestra el diseño metálico, estado de reproducción y la rueda con la carátula integrada para controlar la música desde la pantalla principal sin abrir la app.

---

## Estructura de Archivos Clave

* **Actividad Principal**: [MainActivity.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/MainActivity.kt)
* **Click Wheel Táctil**: [ClickWheel.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/ui/components/ClickWheel.kt)
* **Pantalla LCD Retro**: [LcdScreen.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/ui/components/LcdScreen.kt)
* **Pantalla OLED Moderna**: [OledScreen.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/ui/components/OledScreen.kt)
* **Chasis de Aluminio**: [HardwareCasing.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/ui/components/HardwareCasing.kt)
* **Servicio de Segundo Plano**: [PlaybackService.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/playback/PlaybackService.kt)
* **Base de Datos Room**: [AppDatabase.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/data/local/AppDatabase.kt)
* **Widget 2x2 Glance**: [MicroWheelWidget.kt](file:///C:/Users/pdrj1/.gemini/antigravity/scratch/ipod-android-app/app/src/main/java/com/retro/ipod/widget/MicroWheelWidget.kt)

---

## Cómo abrirlo y generar el APK

1. Abre **Android Studio**.
2. Selecciona **Open** y elige la carpeta:
   `C:\Users\pdrj1\.gemini\antigravity\scratch\ipod-android-app`
3. Conecta tu teléfono Android con cable USB (o inicia el emulador).
4. Pulsa el botón verde **Run (Play)** ▶ para instalarla en tu teléfono.
5. Para generar el archivo `.apk` instalable: Menú **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
