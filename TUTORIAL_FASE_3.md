# Tutorial de creación del Front-End Android: GUALI MÓVIL

**Universidad:** Universidad Mariano Gálvez de Guatemala  
**Curso:** Programación II  
**Fase:** 3  
**Estudiante:** Miguel Antonio Cruz Santos  
**Carné:** 3190-20-15868  
**Repositorio público:** https://github.com/mcruzs5-hub/ProyectoAndroid

## 1. Objetivo y alcance

Construir una interfaz Android de un entrenador de programación en Java. Incluye menú de **Lecciones**, **Configuración**, **Historial** y **Ayuda**; título de lección activa, panel informativo, editor de código, acciones **Compilar**/**Ejecutar** y consola. **Este prototipo es visual**: los botones de compilar y ejecutar muestran respuestas de demostración, no ejecutan un compilador Java real ni consumen una API REST.

## 2. Requisitos previos

- Windows compatible con Android Studio, conexión a Internet y espacio para SDK/emulador.
- Android Studio descargado desde https://developer.android.com/studio
- Android SDK, Android SDK Build-Tools, Android Emulator y Android Virtual Device.
- JDK integrado de Android Studio para Gradle; compatibilidad de código Java 17 definida en `app/build.gradle`.
- Cuenta en GitHub y navegador. En las capturas se utilizó un emulador **Medium Phone API 37** y Android SDK Platform 37.

## 3. Instalación de Android Studio

1. Entrar en https://developer.android.com/studio y descargar el instalador para Windows.
2. Ejecutarlo, seleccionar Android Studio y Android Virtual Device, avanzar con **Next**, **Install** y **Finish**.
3. Abrir Android Studio y completar el asistente de primera configuración.

![Instalación completada](capturas/01-instalacion.png)

## 4. Instalación del SDK y del emulador

1. Desde el asistente inicial o **Tools > SDK Manager**, instalar los componentes de Android SDK.
2. Comprobar la instalación de Build-Tools y Platform-Tools; en la evidencia se instalaron Build-Tools 36 y SDK Platform 37.
3. Abrir **Tools > Device Manager** y crear un dispositivo virtual de tipo teléfono.
4. En este proyecto se utilizó `Medium_Phone_API_37.0`.

![Configuración SDK y emulador](capturas/02-sdk-emulador.png)

## 5. Importación y estructura del proyecto

1. En Android Studio elegir **Open** y seleccionar la carpeta raíz del proyecto, que contiene `settings.gradle`, `build.gradle` y `app`.
2. Seleccionar **Trust Project** si se solicita y permitir la sincronización de Gradle.
3. Ubicar `app/src/main/java/gt/edu/umg/gualimovil/MainActivity.java` y `app/src/main/AndroidManifest.xml`.
4. Comprobar `app/build.gradle` con el identificador `gt.edu.umg.gualimovil`, `compileSdk 35`, `minSdk 26`, `targetSdk 35` y Java 17.

![Proyecto Android Studio](capturas/03-proyecto-abierto.png)

## 6. Desarrollo de la interfaz en Java

El proyecto construye la interfaz directamente desde `MainActivity.java`, por lo que **no utiliza necesariamente un archivo `activity_main.xml`**. Se utiliza `ScrollView` como contenedor desplazable y `LinearLayout` para organizar controles. La actividad agrega con Java un `TextView` de encabezado, botones del menú, panel de lección activa, editor de código, botones de acción y consola. La llamada `setContentView(scroll)` establece la vista creada.

1. Crear o abrir `MainActivity` que hereda de `Activity`.
2. Crear el `ScrollView` y el `LinearLayout` principal.
3. Añadir el encabezado **GUALI MÓVIL | Programación II**.
4. Crear botones **Lecciones**, **Config.**, **Historial**, **Ayuda**.
5. Agregar el panel de la lección activa y un editor `EditText` multilínea.
6. Agregar los botones **Compilar** y **Ejecutar**, y una zona de consola.
7. Configurar los controladores de clic para navegación y mensajes de demostración.

![Código fuente MainActivity](capturas/04-codigo-java.png)

![Construcción de interfaz sin XML](capturas/05-interfaz-java.png)

## 7. Configuración, sincronización y solución de incidencias

1. Abrir `app/build.gradle` y verificar SDK y compatibilidad Java.
2. Elegir **File > Sync Project with Gradle Files**.
3. La primera sincronización presentó un problema de descarga con `SocketTimeoutException: Read timed out`; posteriormente hubo una incidencia durante el asistente de actualización de Gradle.
4. Se revisó la configuración y se evitó mantener una actualización incompatible; la evidencia final confirma que se consiguió ejecutar la aplicación en el emulador.
5. No actualizar automáticamente el Android Gradle Plugin justo antes de entregar si el proyecto ya ejecuta.

![Configuración Gradle](capturas/06-configuracion-gradle.png)

## 8. Compilación y prueba en el emulador

1. Seleccionar **Medium Phone API 37.0** en la barra superior.
2. Presionar **Run app** (triángulo verde) y comprobar el proceso de construcción.
3. Una vez instalado, verificar en el teléfono virtual el encabezado y las secciones de interfaz.
4. Comprobar que aparecen menú de navegación, lección activa, editor, botones Compilar/Ejecutar y consola.
5. La captura final muestra la aplicación visible y ejecutándose. **No representa validación de compilación de código Java dentro de la app**.

![Proceso de construcción](capturas/07-compilacion.png)

![Aplicación funcionando](capturas/08-pantalla-ejecutada.png)

## 9. Publicación en GitHub

1. Abrir el repositorio público: https://github.com/mcruzs5-hub/ProyectoAndroid
2. Seleccionar **Add file > Upload files** para cargar `TUTORIAL_FASE_3.md` y la carpeta `capturas/`.
3. Subir también el proyecto completo de Android Studio (`app/`, Gradle y configuraciones). **Usar la copia exacta de Android Studio que se ejecutó satisfactoriamente**.
4. Confirmar los cambios con **Commit changes**.
5. Abrir el archivo Markdown publicado y comprobar que todas las imágenes se visualicen. Enlace esperado después de publicarlo: https://github.com/mcruzs5-hub/ProyectoAndroid/blob/main/TUTORIAL_FASE_3.md (si la rama predeterminada es `main`).

## 10. Entrega y limitaciones

El enunciado exige un PDF con carátula, nombre, carné y URL pública del tutorial; un repositorio público con tutorial y capturas; y el código fuente completo del proyecto Android Studio. Comprimir todo como `proyecto-fase-3-3190-20-15868.zip`. Verificar el repositorio y el ZIP antes de enviar.

**Limitación técnica:** el desarrollo corresponde a un Front-End Android, no implementa compilación real mediante `guali-dev.jar` ni integración de datos con el backend de la fase 2.
