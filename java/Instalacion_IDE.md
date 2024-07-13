## Instalación de IntelliJ IDEA

IntelliJ IDEA es uno de los entornos de desarrollo integrado (IDE) más populares para programar en Java. A continuación, se describen los pasos para instalar IntelliJ IDEA en tu sistema.

### Paso 1: Descargar IntelliJ IDEA

1. **Accede a la página de descarga**:
   - Abre tu navegador y ve a la [página oficial de descarga de IntelliJ IDEA](https://www.jetbrains.com/idea/download/).

2. **Selecciona la versión**:
   - Hay dos versiones disponibles: Ultimate (de pago) y Community (gratuita). Para la mayoría de los desarrolladores que están comenzando, la versión Community es suficiente. Haz clic en el botón de descarga correspondiente a la versión Community.

### Paso 2: Instalar IntelliJ IDEA en Windows

1. **Ejecuta el instalador**:
   - Una vez que se haya completado la descarga, ejecuta el archivo descargado (`ideaIC-<version>.exe`).

2. **Sigue las instrucciones del instalador**:
   - Aparecerá un asistente de instalación. Haz clic en "Next" para continuar.
   - Elige la carpeta de instalación y haz clic en "Next".
   - Selecciona las opciones adicionales, como crear accesos directos y asociar archivos `.java` con IntelliJ IDEA. Haz clic en "Next".
   - Haz clic en "Install" para iniciar la instalación.

3. **Finaliza la instalación**:
   - Una vez que la instalación se haya completado, puedes optar por ejecutar IntelliJ IDEA inmediatamente marcando la casilla correspondiente y haciendo clic en "Finish".

### Paso 2: Instalar IntelliJ IDEA en macOS

1. **Abre el archivo DMG**:
   - Una vez que se haya completado la descarga, abre el archivo descargado (`ideaIC-<version>.dmg`).

2. **Arrastra IntelliJ IDEA a la carpeta de Aplicaciones**:
   - En la ventana que se abre, arrastra el icono de IntelliJ IDEA a la carpeta "Applications".

3. **Inicia IntelliJ IDEA**:
   - Ve a la carpeta "Applications" y haz doble clic en IntelliJ IDEA para iniciar el IDE.

### Paso 2: Instalar IntelliJ IDEA en Linux

1. **Extrae el archivo tar.gz**:
   - Abre una terminal y navega al directorio donde descargaste el archivo (`ideaIC-<version>.tar.gz`).
   - Usa el siguiente comando para extraer el archivo:
     ```sh
     tar -xzf ideaIC-<version>.tar.gz
     ```

2. **Mueve el directorio extraído**:
   - Mueve el directorio extraído a una ubicación conveniente, por ejemplo `/opt`:
     ```sh
     sudo mv idea-IC-<version> /opt/idea
     ```

3. **Ejecuta IntelliJ IDEA**:
   - Navega al directorio `bin` dentro del directorio de IntelliJ IDEA:
     ```sh
     cd /opt/idea/bin
     ```
   - Ejecuta el script `idea.sh`:
     ```sh
     ./idea.sh
     ```

### Paso 3: Configuración inicial de IntelliJ IDEA

1. **Selecciona configuración**:
   - Al iniciar IntelliJ IDEA por primera vez, se te pedirá que importes configuraciones anteriores. Si es tu primera vez usando IntelliJ IDEA, selecciona "Do not import settings" y haz clic en "OK".

2. **Configura la apariencia**:
   - Selecciona el tema de la interfaz de usuario (UI) que prefieras (por ejemplo, Darkula para un tema oscuro o IntelliJ para un tema claro).

3. **Instala plugins adicionales**:
   - IntelliJ IDEA te dará la opción de instalar plugins adicionales durante la configuración inicial. Puedes instalarlos ahora o más tarde a través del repositorio de plugins.

4. **Comienza un nuevo proyecto**:
   - Una vez que la configuración inicial esté completa, puedes comenzar un nuevo proyecto seleccionando "Create New Project".
