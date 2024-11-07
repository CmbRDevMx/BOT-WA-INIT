Para usar el bot en pc de bajo rendimiento cuando la instalación está bien, pero el sharp sigue mandando errores

doc de instalador en caso no seas windows solo sigue el paso de tu SO y el resto se mantiene

https://pnpm.io/es/installation#:~:text=If%EE%80%80%20pnpm%EE%80%81%20is%20broken%20and

1.INSTALA EL EJECUTADOR DE PNPM PARA WINDOWS POWERSHELL

copia y pega el siguiente
iwr https://get.pnpm.io/install.ps1 -useb | iex

espera a que se instale instale el pnpm

2 PROCEDE A EJECUTAR LA INSTALACION DEL BUILDER BOT PNPM

pnpm create builderbot@latest

Completa la instalación a tu gusto y lee los requisitos de ejecution que este tiene como 

cd direccion de directorio
npm install
npm run dev o npm start

3 Reinstala mediante pnpm SHARP

pnpm install sharp

espera a que acabe la instalacion este puede tardar

4 REALIZA LA EJECUCION

npm run dev o npm start

UBUNTU
**pnpm** es un gestor de paquetes para Node.js rápido y eficiente, que ahorra espacio en disco y mejora el rendimiento utilizando enlaces simbólicos para compartir dependencias comunes entre proyectos. Aquí te muestro cómo instalarlo en **Ubuntu** de manera detallada:

### Opción 1: Instalación de pnpm usando npm (Método recomendado)
Una de las formas más fáciles de instalar **pnpm** es utilizando **npm**, el gestor de paquetes de Node.js que generalmente ya está instalado cuando instalas Node.js. Si tienes **Node.js** y **npm** instalados, puedes instalar **pnpm** globalmente usando el siguiente comando:

1. **Actualiza `npm`** (opcional, pero recomendado):
   Asegúrate de tener la versión más reciente de `npm` para evitar problemas de compatibilidad.
   ```bash
   npm install -g npm
   ```

2. **Instala pnpm** globalmente:
   Usa el siguiente comando para instalar **pnpm** globalmente en tu sistema:
   ```bash
   npm install -g pnpm
   ```

3. **Verifica la instalación de pnpm**:
   Después de instalar **pnpm**, puedes verificar que esté instalado correctamente ejecutando:
   ```bash
   pnpm -v
   ```
   Esto te mostrará la versión de **pnpm** instalada.

### Opción 2: Instalación de pnpm usando el script de instalación oficial
**pnpm** también ofrece un script de instalación fácil de usar que no requiere npm. Este método es útil si aún no tienes **npm** o **Node.js** instalados, o si prefieres no usar npm para gestionar **pnpm**.

1. **Ejecuta el script de instalación**:
   Ejecuta el siguiente comando para instalar **pnpm** a través del script oficial. Este método descarga el script directamente desde el sitio web de **pnpm** y lo ejecuta en tu sistema:
   ```bash
   curl -fsSL https://get.pnpm.io/install.sh | sh -
   ```

2. **Agrega pnpm al `PATH`** (si es necesario):
   Una vez instalado, el script te pedirá que agregues **pnpm** a tu variable `PATH` para que esté disponible en la terminal. Para hacerlo, añade lo siguiente a tu archivo de configuración de shell (`~/.bashrc`, `~/.zshrc`, etc.):
   ```bash
   export PATH="$HOME/.local/share/pnpm:$PATH"
   ```

3. **Recarga tu terminal**:
   Recarga tu terminal para que los cambios surtan efecto:
   ```bash
   source ~/.bashrc
   ```

4. **Verifica la instalación**:
   Asegúrate de que **pnpm** esté correctamente instalado ejecutando:
   ```bash
   pnpm -v
   ```

### Opción 3: Instalación usando `Homebrew`
Si ya tienes **Homebrew** instalado en tu sistema, puedes instalar **pnpm** directamente usando este gestor de paquetes:

1. **Instala pnpm usando Homebrew**:
   ```bash
   brew install pnpm
   ```

2. **Verifica la instalación**:
   ```bash
   pnpm -v
   ```

### Opción 4: Instalación usando Corepack (Node.js 16.13.0 o superior)
Si estás usando **Node.js** 16.13.0 o superior, puedes utilizar **Corepack**, una herramienta que gestiona diferentes gestores de paquetes, incluyendo **pnpm**. Para activar **Corepack** y usar **pnpm**, sigue estos pasos:

1. **Habilitar Corepack**:
   ```bash
   corepack enable
   ```

2. **Instalar pnpm**:
   Luego, instala la última versión de **pnpm** usando **Corepack**:
   ```bash
   corepack prepare pnpm@latest --activate
   ```

3. **Verificar la instalación**:
   ```bash
   pnpm -v
   ```

### Opción 5: Instalación manual con el archivo binario
Si prefieres no usar un gestor de paquetes, también puedes instalar **pnpm** descargando directamente el binario.

1. **Descarga el binario más reciente** desde la [página de lanzamientos de pnpm](https://github.com/pnpm/pnpm/releases).
   Ejemplo para la versión más reciente (puede cambiar según la versión disponible):
   ```bash
   curl -fsSL https://github.com/pnpm/pnpm/releases/download/v8.0.0/pnpm-linux-x64 -o pnpm
   ```

2. **Haz que el archivo sea ejecutable**:
   ```bash
   chmod +x pnpm
   ```

3. **Mueve el archivo a una carpeta que esté en el `PATH`**:
   ```bash
   sudo mv pnpm /usr/local/bin/
   ```

4. **Verifica la instalación**:
   ```bash
   pnpm -v
   ```

### Uso básico de pnpm

Una vez instalado, puedes usar **pnpm** de manera muy similar a **npm**, pero con mejoras en la administración de paquetes.

1. **Instalar dependencias** (en lugar de `npm install`):
   ```bash
   pnpm install
   ```

2. **Instalar un paquete globalmente**:
   ```bash
   pnpm add -g <paquete>
   ```

3. **Instalar un paquete como dependencia de desarrollo**:
   ```bash
   pnpm add -D <paquete>
   ```

4. **Instalar una versión específica de un paquete**:
   ```bash
   pnpm add <paquete>@<versión>
   ```

5. **Listar los paquetes globales instalados**:
   ```bash
   pnpm list -g
   ```

6. **Eliminar un paquete**:
   ```bash
   pnpm remove <paquete>
   ```

### Ventajas de pnpm sobre npm/yarn
- **Eficiencia de espacio**: Las dependencias comunes solo se instalan una vez en tu sistema y luego se usan enlaces simbólicos, lo que reduce significativamente el uso de espacio en disco.
- **Velocidad**: La instalación de paquetes es mucho más rápida que en npm, especialmente en proyectos grandes.
- **Mejor manejo de dependencias**: pnpm tiene un manejo más estricto de las dependencias, evitando problemas donde diferentes versiones de un mismo paquete se mezclan.

### Conclusión
**pnpm** es una alternativa poderosa y eficiente a npm y yarn. Puedes instalarlo fácilmente en Ubuntu usando diversos métodos, y una vez instalado, su uso es bastante similar a los otros gestores de paquetes, con grandes mejoras en rendimiento y uso de espacio.