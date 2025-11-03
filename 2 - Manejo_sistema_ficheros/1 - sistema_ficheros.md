# Introducción al Sistema de Ficheros en Linux

En **Linux**, todo se organiza bajo un único sistema jerárquico de archivos que **comienza en la raíz `/`**.  
A diferencia de otros sistemas operativos (como Windows, donde existen unidades separadas como `C:` o `D:`), en Linux **todos los archivos, directorios y dispositivos** forman parte de una sola estructura de árbol.

Este modelo se basa en la idea de que **todo es un archivo**:  
programas, dispositivos, procesos, configuraciones, discos, etc.  
Cada elemento se representa como un archivo dentro del sistema de ficheros.

---

## Estructura jerárquica del sistema de ficheros

El sistema de archivos de Linux está organizado en forma de **árbol invertido**, con el directorio raíz `/` en la parte superior y el resto de directorios colgando de él.

Ejemplo visual:

```bash
/
├── bin
├── boot
├── dev
├── etc
├── home
│   ├── usuario1
│   └── usuario2
├── lib
├── media
├── mnt
├── opt
├── root
├── sbin
├── tmp
├── usr
└── var
```

Cada carpeta tiene una función específica dentro del sistema.  
Por ejemplo:

- `/home`: Archivos personales de los usuarios.  
- `/etc`: Archivos de configuración del sistema.  
- `/bin`: Comandos esenciales del sistema.  
- `/var`: Archivos variables, como registros o logs.  
- `/dev`: Dispositivos del hardware representados como archivos.  

---

## ¿Por qué se llama “sistema de ficheros”?

Porque define **cómo se almacenan, organizan y acceden** los datos dentro de un dispositivo de almacenamiento.  
El sistema de ficheros administra los espacios, nombres, permisos y estructura de los archivos y carpetas.

Linux puede trabajar con diferentes tipos de sistemas de ficheros:
- **ext4** (el más común)
- **XFS**
- **Btrfs**
- **FAT32**
- **exFAT**
- **NTFS** (para compatibilidad con Windows)

---

## El comando `tree`

El comando `tree` permite **visualizar la estructura jerárquica del sistema de archivos** en forma de árbol, mostrando las carpetas y subcarpetas de manera ordenada.

### Sintaxis básica

```bash
tree [opciones] [directorio]
```

### Ejemplo práctico

```bash
tree -L 2 /home
```

Salida aproximada:

```bash
/home
├── usuario1
│   ├── documentos
│   └── descargas
└── usuario2
    └── proyectos
```

## Opciones comunes

```bash
| Opción        | Descripción                                           | Ejemplo            |
| ------------- | ----------------------------------------------------- | ------------------ |
| `-L N`        | Limita la profundidad del árbol hasta el nivel **N**. | `tree -L 2 /etc`   |
| `-d`          | Muestra solo **directorios** (oculta archivos).       | `tree -d /usr`     |
| `-a`          | Muestra archivos **ocultos** (que comienzan con `.`). | `tree -a /home`    |
| `-f`          | Muestra la **ruta completa** de cada archivo.         | `tree -f /home`    |
| `--dirsfirst` | Muestra **directorios antes** que archivos.           | `tree --dirsfirst` |
| `-h`          | Muestra el **tamaño legible** de cada archivo.        | `tree -h /var`     |
```

### Ejemplo combinado

```bash
tree -L 1 -d --dirsfirst /
```

Salida posible:

```bash
/
├── bin
├── boot
├── dev
├── etc
│   ├── apt
│   ├── systemd
│   └── ssh
├── home
│   ├── usuario1
│   └── usuario2
└── var
    ├── cache
    ├── log
    └── tmp
```

## Instalación del comando `tree`

En muchas distribuciones de Linux no viene preinstalado.
Puedes instalarlo de la siguiente manera con el comando de tu sistema:

```bash
sudo apt install tree
```

## En resumen

- El sistema de ficheros de Linux es una estructura jerárquica que organiza todos los elementos del sistema bajo el directorio raíz /.
- Todo es un archivo, desde programas hasta dispositivos.
- El comando tree permite visualizar fácilmente esa estructura en formato de árbol.
- Es una herramienta ideal para entender la organización del sistema y explorar carpetas de forma ordenada y rápida.
