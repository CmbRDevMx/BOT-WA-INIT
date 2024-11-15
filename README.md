LINUX INSTALACION:
Aquí tienes una guía rápida y sencilla con los comandos bien explicados para que puedas seguirlos sin complicaciones:

### 1. **Actualizar el sistema**
Primero, asegúrate de que tu sistema está actualizado:
```bash
sudo apt update
sudo apt upgrade
```

### 2. **Instalar NVM (Node Version Manager)**
Descarga e instala **NVM** para gestionar versiones de Node.js:
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
```
### ENTERATE DE LAS NUEVAS VERSIONES AQUI DE NVM: 
https://github.com/nvm-sh/nvm/releases.
Donde si hay una nueva solo cambiaras el numero de la version del comando que en el caso anterior es:[ v0.40.1](https://github.com/nvm-sh/nvm/releases)
________________________________________________

Verifica que **NVM** se instaló correctamente:
```bash
nvm --version
```

### 3. **Listar versiones disponibles de Node.js**
Con **NVM**, puedes ver todas las versiones de **Node.js** disponibles:
```bash
nvm ls-remote
```

### 4. **Instalar una versión específica de Node.js**
Elige una versión (en este caso 20.18.0) e instálala:
```bash
nvm install 20.18.0
```

### 5. **Actualizar npm**
Después de instalar **Node.js**, actualiza **npm** a su última versión:
```bash
npm install -g npm
```

### 6. **Instalar pnpm**
Instala **pnpm**, un gestor de paquetes alternativo y eficiente:
```bash
npm install -g pnpm
```

---

## **Creando el Bot**

### 1. **Crear y entrar en el directorio de trabajo**
Crea un directorio para tu bot y muévete a él:
```bash
mkdir workspace && cd workspace
```

### 2. **Crear el bot usando pnpm**
Inicia la creación de tu bot con **pnpm**:
```bash
pnpm create builderbot@latest
```

¡Con esto, ya tendrás tu bot básico listo para ser configurado y ejecutado!


EXTRAS:

Para usar el bot en pc de bajo rendimiento cuando la instalación está bien, pero el sharp sigue mandando errores

doc de instalador en caso no seas windows solo sigue el paso de tu SO y el resto se mantiene

https://pnpm.io/es/installation#:~:text=If%EE%80%80%20pnpm%EE%80%81%20is%20broken%20and

1.INSTALA EL EJECUTADOR DE PNPM PARA WINDOWS POWERSHELL

copia y pega el siguiente
iwr https://get.pnpm.io/install.ps1 -useb | iex

espera a que se instale instale el pnpm

2 PROCEDE A EJECUTAR LA INSTALACION DEL BUILDER BOT PNPM

pnpm create builderbot@latest

3 Reinstala mediante pnpm SHARP

pnpm install sharp

espera a que acabe la instalacion este puede tardar

4 REALIZA LA EJECUCION

pnpm run dev o pnpm startstart

## TERMUX SIN DISTRO PD
Este error de `.netrc parser` en Termux generalmente ocurre debido a un problema con la configuración del archivo `.netrc`. Aquí tienes unos pasos para resolver este problema y proceder con la instalación de NVM:

### 1. Verificar y corregir el archivo `.netrc`

El archivo `.netrc` almacena credenciales de autenticación y configuración de red. Vamos a comprobar si existe y si tiene un formato válido:

1. **Verifica si existe el archivo `.netrc`:**

   ```bash
   ls -a ~ | grep .netrc
   ```

2. **Edita o elimina el archivo `.netrc` si existe:** 

   Si el archivo `.netrc` está presente y contiene configuraciones incorrectas, edítalo o renómbralo:

   ```bash
   mv ~/.netrc ~/.netrc_backup
   ```

   Esto renombrará el archivo, evitando que cause problemas sin eliminarlo permanentemente.

### 2. Intentar nuevamente la instalación de NVM

Una vez que hayas renombrado o corregido el archivo `.netrc`, vuelve a ejecutar el comando de instalación de NVM:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
```

### 3. Proceder con la configuración

Si la descarga e instalación funcionan esta vez, continúa con los pasos de configuración de NVM mencionados anteriormente para que se cargue en cada nueva sesión de Termux:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
```

Luego, recarga la configuración de tu shell y verifica la instalación:

```bash
source ~/.bashrc
nvm --version
```

Esto debería resolver el problema del `.netrc` y permitir la instalación adecuada de NVM en Termux.
