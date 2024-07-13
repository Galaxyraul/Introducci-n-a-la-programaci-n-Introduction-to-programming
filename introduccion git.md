Además del pseudocódigo, una de las herramientas más poderosas con las que contamos es el control de versiones. ¿Pero qué es este concepto que se nos presenta? Descubramoslo.

## Control de Versiones

La definición típica y clásica del control de versiones es la siguiente:

*"Se llama control de versiones a la gestión de los diversos cambios que se realizan sobre los elementos de algún producto o una configuración del mismo. Una versión, revisión o edición de un producto, es el estado en el que se encuentra el mismo en un momento dado de su desarrollo o modificación."*

En resumen, el control de versiones nos permite controlar los cambios que sufre un proyecto permitiendo guardarlos y deshacerlos.

Esto, en el ámbito de la programación, supone una herramienta que nos permite evaluar cómo evoluciona nuestro código y recuperar versiones anteriores en caso de que hayamos cometido errores.

## Control de Versiones: Git

Git es una herramienta de control de versiones distribuida que permite a los desarrolladores gestionar los cambios en el código fuente a lo largo del tiempo. Es una herramienta fundamental en el desarrollo de software moderno, facilitando tanto el trabajo individual como la colaboración en equipo.

### ¿Qué es Git?

Git es un sistema de control de versiones distribuido. A diferencia de los sistemas de control de versiones centralizados, Git permite que cada desarrollador tenga una copia completa del historial del proyecto en su propia máquina. Esto no solo mejora la velocidad y eficiencia, sino que también permite trabajar de manera offline y realizar operaciones avanzadas de fusión y ramificación.

### Comandos Básicos de Git

1. **Inicializar un repositorio Git**
   ```bash
   git init
   ```
   Este comando inicializa un nuevo repositorio Git en el directorio actual.

2. **Clonar un repositorio existente**
   ```bash
   git clone <URL-del-repositorio>
   ```
   Clona un repositorio existente desde una URL especificada.

3. **Ver el estado del repositorio**
   ```bash
   git status
   ```
   Muestra el estado de los archivos en el repositorio, indicando los cambios que han sido añadidos, modificados o eliminados.

4. **Agregar archivos al área de preparación**
   ```bash
   git add <archivo>
   git add .
   ```
   Agrega archivos individuales o todos los archivos modificados al área de preparación para ser confirmados.

5. **Confirmar los cambios**
   ```bash
   git commit -m "Mensaje descriptivo del cambio"
   ```
   Confirma los cambios en el área de preparación con un mensaje descriptivo.

6. **Ver el historial de confirmaciones**
   ```bash
   git log
   ```
   Muestra el historial de confirmaciones en el repositorio.

7. **Crear una nueva rama**
   ```bash
   git branch <nombre-de-la-rama>
   ```
   Crea una nueva rama con el nombre especificado.

8. **Cambiar a una rama diferente**
   ```bash
   git checkout <nombre-de-la-rama>
   ```
   Cambia a la rama especificada.

9. **Fusionar cambios de una rama a otra**
   ```bash
   git merge <nombre-de-la-rama>
   ```
   Fusiona los cambios de la rama especificada en la rama actual.

10. **Actualizar el repositorio local con los cambios del remoto**
    ```bash
    git pull
    ```
    Actualiza el repositorio local con los cambios del repositorio remoto.

11. **Enviar cambios al repositorio remoto**
    ```bash
    git push
    ```
    Envía los cambios confirmados en el repositorio local al repositorio remoto.

## Instalación de Git

Git es una herramienta fundamental para el control de versiones y es compatible con la mayoría de los sistemas operativos. A continuación, se explica cómo instalar Git en Windows, macOS y Linux.

### Instalación en Windows

1. **Descargar el Instalador:**
   - Ve a la [página oficial de descargas de Git](https://git-scm.com/downloads).
   - Selecciona Windows y descarga el instalador.

2. **Ejecutar el Instalador:**
   - Ejecuta el archivo descargado y sigue las instrucciones del asistente de instalación.
   - Durante la instalación, puedes aceptar las opciones predeterminadas o personalizar las configuraciones según tus necesidades. Es recomendable dejar la mayoría de las opciones por defecto.

3. **Verificar la Instalación:**
   - Abre el `Símbolo del sistema` o `PowerShell`.
   - Escribe el siguiente comando y presiona Enter:
     ```bash
     git --version
     ```
   - Deberías ver la versión de Git instalada en tu sistema.

### Instalación en macOS

1. **Usar Homebrew:**
   - Si tienes Homebrew instalado, puedes instalar Git fácilmente ejecutando el siguiente comando en la terminal:
     ```bash
     brew install git
     ```

2. **Descargar el Instalador:**
   - Alternativamente, puedes descargar el instalador desde la [página oficial de descargas de Git](https://git-scm.com/downloads) y seguir las instrucciones de instalación.

3. **Verificar la Instalación:**
   - Abre la `Terminal`.
   - Escribe el siguiente comando y presiona Enter:
     ```bash
     git --version
     ```
   - Deberías ver la versión de Git instalada en tu sistema.

### Instalación en Linux

Para instalar Git en Linux, los comandos pueden variar ligeramente según la distribución que estés utilizando.

1. **Ubuntu/Debian:**
   ```bash
   sudo apt update
   sudo apt install git
   ```

2. **Fedora:**
   ```bash
   sudo dnf install git
   ```

3. **Arch Linux:**
   ```bash
   sudo pacman -S git
   ```

4. **Verificar la Instalación:**
   - Abre la terminal.
   - Escribe el siguiente comando y presiona Enter:
     ```bash
     git --version
     ```
   - Deberías ver la versión de Git instalada en tu sistema.

### Configuración Inicial de Git

Después de instalar Git, es recomendable configurarlo con tu nombre y correo electrónico. Estos se utilizarán para identificar las confirmaciones que realices.

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@example.com"
```

Para verificar tu configuración, puedes usar:

```bash
git config --list
```

### Ejercicios Prácticos

#### Ejercicio 1: Inicialización y Confirmaciones Básicas

<details>
<summary>Enunciado</summary>

1. Crea un nuevo directorio en tu computadora llamado `mi_proyecto`.
2. Inicializa un repositorio Git en este directorio.
3. Crea un archivo llamado `README.md` y agrega el texto `# Mi Proyecto`.
4. Agrega y confirma el archivo `README.md` en el repositorio.
</details>

<details>
<summary>Solución</summary>

```bash
mkdir mi_proyecto
cd mi_proyecto
git init
echo "# Mi Proyecto" > README.md
git add README.md
git commit -m "Agregar archivo README.md con título inicial"
```
</details>

#### Ejercicio 2: Trabajando con Ramas

<details>
<summary>Enunciado</summary>

1. Crea una nueva rama llamada `feature1`.
2. Cambia a la rama `feature1`.
3. Crea un archivo llamado `feature.txt` y agrega el texto `Esta es una nueva característica`.
4. Agrega y confirma el archivo `feature.txt` en la rama `feature1`.
5. Cambia de vuelta a la rama `main`.
</details>

<details>
<summary>Solución</summary>

```bash
git branch feature1
git checkout feature1
echo "Esta es una nueva característica" > feature.txt
git add feature.txt
git commit -m "Agregar archivo feature.txt con descripción de nueva característica"
git checkout main
```
</details>

#### Ejercicio 3: Fusionando Ramas

<details>
<summary>Enunciado</summary>

1. Desde la rama `main`, fusiona los cambios de la rama `feature1`.
2. Verifica que el archivo `feature.txt` esté presente en la rama `main`.
</details>

<details>
<summary>Solución</summary>

```bash
git merge feature1
ls
# Verifica que el archivo feature.txt esté presente
```
</details>

#### Ejercicio 4: Resolviendo Conflictos de Fusión

<details>
<summary>Enunciado</summary>

1. Crea una nueva rama llamada `feature2`.
2. En la rama `main`, edita el archivo `README.md` y cambia el texto a `# Mi Proyecto Principal`.
3. Confirma los cambios en la rama `main`.
4. Cambia a la rama `feature2` y edita el archivo `README.md` para que el texto sea `# Mi Proyecto Alternativo`.
5. Confirma los cambios en la rama `feature2`.
6. Intenta fusionar la rama `feature2` en la rama `main` y resuelve cualquier conflicto que surja.
</details>

<details>
<summary>Solución</summary>

```bash
git branch feature2
git checkout main
echo "# Mi Proyecto Principal" > README.md
git add README.md
git commit -m "Actualizar título del README en la rama main"
git checkout feature2
echo "# Mi Proyecto Alternativo" > README.md
git add README.md
git commit -m "Actualizar título del README en la rama feature2"
git checkout main
git merge feature2
# Resolver conflictos editando README.md y confirmando el resultado
git add README.md
git commit -m "Resolver conflicto de fusión en README.md"
```
</details>

#### Ejercicio 5: Utilizando `.gitignore`

<details>
<summary>Enunciado</summary>

1. Crea un archivo `.gitignore` en tu repositorio.
2. Añade una regla para ignorar todos los archivos con la extensión `.log`.
3. Crea un archivo llamado `debug.log` y verifica que no aparezca como un archivo no seguido por Git.
</details>

<details>
<summary>Solución</summary>

```bash
echo "*.log" > .gitignore
git add .gitignore
git commit -m "Agregar archivo .gitignore para ignorar archivos .log"
touch debug.log
git status
# Verifica que debug.log no aparezca como un archivo no seguido
```
</details>
