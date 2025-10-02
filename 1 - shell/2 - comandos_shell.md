
# Apunte: ¿Qué es un **Comando en Linux**?

## Concepto General
Un **comando en Linux** es una **instrucción que le damos a la Shell** para que realice una acción concreta sobre el sistema operativo.  
Cada comando es interpretado por la Shell, que se encarga de comunicarse con el **núcleo del sistema (kernel)** para ejecutar la acción solicitada.

Los comandos permiten al usuario:  
- Navegar entre carpetas y directorios.  
- Crear, mover, copiar o eliminar archivos y carpetas.  
- Gestionar usuarios y permisos.  
- Instalar, actualizar o eliminar software.  
- Consultar información del sistema, procesos o recursos disponibles.  
- Automatizar tareas mediante scripts.  

En pocas palabras, **un comando es la manera principal de interactuar con Linux desde la Shell**.

---

## Estructura básica de un comando
Un comando en Linux suele tener la siguiente forma:

```bash
comando [opciones] [argumentos]
```

### Partes del comando

1. **comando** → La acción a ejecutar.

- Ejemplos: `ls`, `cd`, `mkdir`, `touch`, `pwd`, `cp`.

2. **opciones (flags)** → Modifican o especifican el comportamiento del comando.

- Se escriben con un guion `-` o doble guion `--`.

- Ejemplo:

  - `ls -l` → Lista archivos en formato detallado.

  - `ls --all` → Muestra todos los archivos, incluyendo los ocultos.

3. **argumentos** → Son los objetos sobre los que actúa el comando, como archivos, carpetas o rutas.

- Ejemplo: `cd Documentos` → Cambia al directorio llamado “Documentos”.

- Ejemplo: `cp archivo.txt /home/usuario/Documentos` → Copia un archivo a otra carpeta.

---

## Ejemplos de comandos con señalamiento de partes

1. Listar archivos y carpetas

```bash
ls -l /home/usuario
```

- **Comando**: `ls` → Lista los archivos y carpetas.

- **Opción**: `-l` → Muestra la lista en formato detallado (permisos, propietario, tamaño, fecha).

- **Argumento**: `/home/usuario` → Directorio sobre el cual se aplica el comando.

```bash
ls -a
```

- **Comando**: `ls`

- **Opción**: `-a` → Muestra también los archivos ocultos.

- **Argumento**: Ninguno (se aplica al directorio actual).


2. Navegar entre carpetas

```bash
cd Documentos
```

**Comando**: `cd` → Cambia de directorio.

**Opción**: Ninguna

**Argumento**: `Documentos` → Directorio al que se quiere acceder.

```bash
cd ..
```

**Comando**: `cd`

**Opción**: Ninguna

**Argumento**: `..` → Directorio padre (sube un nivel).


3. Crear archivos y carpetas

```bash
mkdir proyectos
```

- **Comando**: `mkdir` → Crear un directorio.

- **Opción**: Ninguna

- **Argumento**: `proyectos` → Nombre de la carpeta a crear.

```bash
touch notas.txt
```

**Comando**: `touch` → Crear archivo vacío.

**Opción**: Ninguna

**Argumento**: `notas.txt` → Nombre del archivo a crear.

4. Copiar, mover y eliminar

```bash
cp archivo.txt respaldo.txt
```

- **Comando**: `cp` → Copiar archivo o carpeta.

- **Opción**: Ninguna

- **Argumentos**:

  - `archivo.txt` → Archivo de origen

  - `respaldo.txt` → Archivo de destino

```bash
rm -r carpeta
```

- **Comando**: `rm` → Eliminar archivos o carpetas.

- **Opción**: `-r` → Eliminar recursivamente (incluye todo el contenido de la carpeta)

- **Argumento**: `carpeta` → Carpeta a eliminar

5. Consultar información del sistema

```bash
pwd
```

- **Comando**: `pwd` → Muestra el directorio actual.

- **Opción**: Ninguna

- **Argumento**: Ninguno

```bash
df -h
```

- **Comando**: `df` → Muestra espacio en disco.

- **Opción**: `-h` → Formato legible (ej. MB, GB)

- **Argumento**: Ninguno (por defecto muestra todos los discos)

---

## Tipos de comandos en Linux

En Linux, los comandos se dividen en **4 tipos principales**: internos, externos, alias y funciones.
Saber su tipo ayuda a entender **cómo se ejecutan y cómo identificarlos**.


1. **Comandos internos (Built-in)**

- Son **comandos integrados en la Shell**, no necesitan un archivo externo para funcionar.

- Se usan para **configurar la Shell o manipular variables internas**, y se ejecutan rápido.

Cómo identificarlos:

```bash
type cd
```

Resultado:

```bash
cd is a shell builtin
```

**Lista representativa de comandos internos**:

- `cd` → Cambiar de directorio

- `echo` → Mostrar texto o variables

- `exit` → Cerrar la sesión de la Shell

- `pwd` → Mostrar directorio actual

- `alias` → Crear alias de comandos


2. **Comandos externos**

- Son **programas o archivos ejecutables** que existen en el sistema, normalmente en `/bin` o `/usr/bin`.

- La Shell los llama cuando se escriben, pero no forman parte de la Shell.

**Cómo identificarlos**:

```bash
type cat
```

Resultado:

```bash
cat is /usr/bin/cat
```

**Lista representativa de comandos externos**:

- `cat` → Mostrar contenido de archivos

- `find` → Buscar archivos en carpetas

- `cp` → Copiar archivos o carpetas

- `mv` → Mover o renombrar archivos

- `rm` → Eliminar archivos o carpetas


3. **Alias**

- Son **comandos personalizados creados por el usuario** para abreviar o modificar otro comando.

- Permiten **ahorrar tiempo** y crear comandos más fáciles de recordar.

**Cómo identificarlos**:

```bash
type ll
```

Resultado:

```bash
ll is an alias for ls -lh
```

**Lista representativa de alias**:

`ll` → `ls -lh`

`la` → `ls -lAh`

**Crear tus propios alias**

- **Sintaxis básica**:

```bash
alias nombre_alias="comando_a_ejecutar"
```

- **Ejemplo simple**:

```bash
alias limpiar="clear; echo 'Pantalla limpia'"
```

- limpiar → nombre del alias

- clear → limpia la terminal

- echo 'Pantalla limpia' → muestra un mensaje después de limpiar

Uso:

```bash
limpiar
```

Salida en pantalla:

```bash
Pantalla limpia
```


4. **Funciones de Shell**

- Son **bloques de comandos agrupados** definidos por el usuario para automatizar tareas repetitivas.

- Pueden recibir **argumentos** como un comando normal.

**Cómo identificarlas**:

```bash
type saludo
```

Resultado:

```bash
saludo is a shell function
```

Antes del resultado anterior debemos crear la funcion dentro de la shell

```bash
saludo() {
    echo "Hola, $1"
}
```

- `saludo` → nombre de la función

- `$1` → primer argumento que le pases al ejecutar la función

Ejecutando la función:

```bash
saludo Abel
```

Salida:

```bash
Hola, Abel
```
