¡Claro! A continuación, te doy una guía completa sobre el uso de **NVM (Node Version Manager)** en Ubuntu, cubriendo cómo listar las versiones de Node.js disponibles, cómo instalar una versión específica, y más detalles sobre su uso.

### 1. Listar las versiones disponibles de Node.js

Para ver todas las versiones de Node.js que puedes instalar con NVM, usa el siguiente comando:
```bash
nvm ls-remote
```
Este comando te mostrará una lista extensa con todas las versiones de Node.js disponibles para instalar, organizadas en **LTS** (Long Term Support) y versiones regulares. Las versiones **LTS** son recomendadas para la mayoría de los proyectos, ya que tienen un ciclo de soporte prolongado y son más estables.

#### Filtrar solo las versiones LTS:
Si solo quieres ver las versiones LTS disponibles, puedes usar:
```bash
nvm ls-remote --lts
```

### 2. Instalar una versión específica de Node.js

Para instalar una versión específica de Node.js, utiliza el comando `nvm install` seguido de la versión que desees. Por ejemplo, para instalar la versión **18.16.0**, ejecuta:
```bash
nvm install 18.16.0
```

Si prefieres instalar la versión más reciente (no LTS), usa el siguiente comando:
```bash
nvm install node
```
Esto instalará la versión más reciente de Node.js disponible.

#### Instalar la versión LTS más reciente:
Para instalar la versión **LTS** más reciente:
```bash
nvm install --lts
```

### 3. Cambiar entre versiones instaladas

Si ya tienes varias versiones de Node.js instaladas y quieres cambiar entre ellas, puedes usar:
```bash
nvm use <versión>
```
Ejemplo:
```bash
nvm use 16.14.0
```
Este comando cambiará a la versión especificada de Node.js. Después de cambiar, todas las sesiones de terminal usarán esa versión de Node.js hasta que cambies nuevamente.

### 4. Establecer una versión predeterminada

Si quieres que una versión específica de Node.js se use cada vez que abras una nueva terminal, puedes establecerla como la versión predeterminada con el siguiente comando:
```bash
nvm alias default <versión>
```
Ejemplo:
```bash
nvm alias default 18.16.0
```
Esto configurará la versión 18.16.0 como la predeterminada.

### 5. Ver las versiones instaladas en tu sistema

Para ver qué versiones de Node.js ya tienes instaladas en tu sistema, usa:
```bash
nvm ls
```
Esto listará las versiones que has instalado, indicando también cuál es la versión actual en uso y cuál es la predeterminada.

### 6. Ver la versión actual en uso

Si en algún momento no estás seguro de qué versión de Node.js estás usando en tu terminal, puedes verificarlo con:
```bash
nvm current
```

### 7. Desinstalar una versión de Node.js

Si deseas desinstalar una versión específica de Node.js que ya no necesitas, puedes hacerlo con:
```bash
nvm uninstall <versión>
```
Ejemplo:
```bash
nvm uninstall 16.14.0
```
Esto eliminará esa versión de Node.js de tu sistema.

### 8. Usar NVM en un archivo de proyecto (archivo `.nvmrc`)

Si estás trabajando en un proyecto que requiere una versión específica de Node.js, puedes crear un archivo `.nvmrc` en el directorio raíz de tu proyecto. Este archivo debe contener solo el número de la versión de Node.js que deseas utilizar en ese proyecto, por ejemplo:
```
18.16.0
```

Luego, puedes ejecutar el siguiente comando dentro del directorio del proyecto para asegurarte de que estás usando la versión correcta de Node.js:
```bash
nvm use
```
Esto leerá la versión del archivo `.nvmrc` y cambiará automáticamente a esa versión.

### 9. Comandos adicionales útiles

- **Listar versiones disponibles localmente**:
  ```bash
  nvm ls
  ```

- **Forzar la reinstalación de `npm` si es necesario** (si has encontrado algún problema con `npm`):
  ```bash
  nvm install-latest-npm
  ```

- **Actualizar NVM**: Si deseas actualizar a la última versión de NVM, puedes ejecutar el mismo comando de instalación:
  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
  ```

- **Ver más información sobre un comando de NVM**:
  ```bash
  nvm help
  ```

### 10. Notas adicionales

- **Global packages**: Ten en cuenta que cada versión de Node.js tiene su propio conjunto de paquetes globales instalados. Si necesitas instalar un paquete global para todas las versiones de Node.js que gestiones, tendrás que hacerlo en cada versión individualmente.
  
- **Rendimiento**: NVM es especialmente útil si trabajas en varios proyectos que requieren diferentes versiones de Node.js, ya que puedes cambiar fácilmente entre versiones y probar tu código en diferentes entornos.

---

Con esta guía, deberías poder administrar tus versiones de Node.js fácilmente en Ubuntu usando **NVM**, instalando y cambiando entre versiones según lo necesites.