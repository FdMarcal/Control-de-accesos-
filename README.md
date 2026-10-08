# AutoAccess - Control de Placas en CodeAssist-Android IDE

Esta aplicación está completamente configurada para compilarse en la aplicación **CodeAssist - Android IDE** directamente desde tu dispositivo Android, o en Android Studio.

## Especificaciones Técnicas
- **Lenguaje:** Kotlin 1.9+
- **Min SDK:** 26 (Android 8.0 Oreo)
- **Target SDK:** 33 (Android 13 Tiramisu)
- **Compile SDK:** 33
- **Arquitectura:** MVVM + Room Database + CameraX + Google ML Kit Text Recognition

## Características Implementadas
1. **Lista de Residentes (Propietarios):**
   - Capacidad de registrar, editar y borrar residentes.
   - Soporte para **múltiples placas vehiculares** por residente mediante `TypeConverters` JSON en Room.
2. **Lista de Visitantes:**
   - Registro, edición y eliminación de visitas.
   - **Captura automática de fecha y hora exacta** en que se agregó el individuo y su placa vehicular (`entryTimestamp`).
3. **Escáner de Cámara con Reconocimiento Óptico (ML Kit):**
   - Utiliza CameraX y ML Kit para extraer la placa en tiempo real.
   - **Comparación automática:**
     - Si la placa pertenece a un residente registrado, muestra mensaje de acceso autorizado con nombre y departamento.
     - Si NO pertenece a propietarios, ofrece un acceso directo para registrarla en la lista de Visitantes (con hora actual precargada) o asignarla a un propietario.

## Pasos para Abrir y Generar el APK en CodeAssist-Android
1. Descarga el archivo ZIP del proyecto con el botón "Descargar Proyecto (.ZIP)".
2. En tu dispositivo Android, abre tu gestor de archivos y descomprime la carpeta en `/storage/emulated/0/CodeAssist/projects/` (o la carpeta de proyectos de CodeAssist).
3. Abre **CodeAssist**, pulsa en **Open Project** y selecciona la carpeta descomprimida.
4. Concede los permisos de almacenamiento y cámara.
5. Pulsa el botón **Play / Run (▶)** en la barra superior.
6. CodeAssist compilará el código Kotlin y generará el archivo **app-debug.apk** en `app/build/outputs/apk/debug/`, mostrando de inmediato la ventana para instalar el APK en tu Android.
