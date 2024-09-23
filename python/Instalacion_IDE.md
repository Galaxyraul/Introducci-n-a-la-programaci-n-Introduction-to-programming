## Instalación de Python en Visual Studio Code (VSCode)

Visual Studio Code (VSCode) es un editor de código ligero pero potente que es ideal para desarrollar en múltiples lenguajes, incluido Python. A continuación, se describen los pasos para instalar Python en VSCode.

### Paso 1: Instalar Visual Studio Code

1. **Descargar VSCode**:
   - Ve a la [página de descarga de VSCode](https://code.visualstudio.com/Download) y descarga el instalador correspondiente a tu sistema operativo (Windows, macOS o Linux).

2. **Instalar VSCode**:
   - **En Windows**: Ejecuta el archivo `.exe` descargado y sigue las instrucciones del instalador.
   - **En macOS**: Abre el archivo `.dmg` descargado y arrastra VSCode a la carpeta "Applications".
   - **En Linux**: Extrae el archivo `.tar.gz` descargado y mueve el contenido a una ubicación conveniente, como `/usr/share` o `/opt`. También puedes instalarlo usando un gestor de paquetes como `apt` o `snap`.

### Paso 2: Instalar Python

1. **Descargar Python**:
   - Ve a la [página de descargas de Python](https://www.python.org/downloads/) y descarga la última versión estable de Python.

2. **Instalar Python**:
   - **En Windows**: Ejecuta el instalador `.exe` y asegúrate de marcar la opción "Add Python to PATH". Luego sigue las instrucciones del instalador.
   - **En macOS**: Abre el archivo `.pkg` descargado y sigue las instrucciones del instalador.
   - **En Linux**: Usa un gestor de paquetes para instalar Python. Por ejemplo, en Debian/Ubuntu, puedes usar `sudo apt-get install python3`.

3. **Verificar la instalación**:
   - Abre una terminal (o el símbolo del sistema en Windows) y ejecuta `python --version` o `python3 --version` para verificar que Python se ha instalado correctamente.

### Paso 3: Configurar Python en VSCode

1. **Abrir VSCode**:
   - Abre Visual Studio Code.

2. **Instalar la extensión de Python**:
   - Ve a la vista de Extensiones haciendo clic en el icono de extensiones en la barra lateral izquierda o presionando `Ctrl+Shift+X` (Windows/Linux) o `Cmd+Shift+X` (macOS).
   - Busca "Python" en la barra de búsqueda.
   - Instala la extensión oficial de Python proporcionada por Microsoft.

3. **Seleccionar el intérprete de Python**:
   - Abre la paleta de comandos presionando `Ctrl+Shift+P` (Windows/Linux) o `Cmd+Shift+P` (macOS).
   - Escribe `Python: Select Interpreter` y selecciona la opción.
   - Selecciona el intérprete de Python que deseas utilizar. VSCode debería detectar automáticamente las instalaciones de Python en tu sistema.

4. **Configurar el entorno de desarrollo**:
   - Crea un nuevo archivo Python o abre un proyecto existente.
   - VSCode te pedirá instalar otras herramientas útiles como linters y formateadores (por ejemplo, pylint o black). Sigue las recomendaciones para mejorar tu flujo de trabajo.

### Paso 4: Probar la configuración

1. **Crear un archivo Python**:
   - Crea un nuevo archivo con la extensión `.py`, por ejemplo, `hello.py`.

2. **Escribir un código de prueba**:
   - Abre `hello.py` y escribe el siguiente código:
     ```python
     print("Hello, VSCode!")
     ```

3. **Ejecutar el código**:
   - Abre la terminal integrada en VSCode presionando `Ctrl+` (Windows/Linux) o `Cmd+` (macOS).
   - Ejecuta el script escribiendo `python hello.py` o `python3 hello.py` en la terminal.
