# Navegación en Linux: Rutas Relativas y Absolutas

## Introducción

En Linux, **navegar por el sistema de archivos** significa moverse entre carpetas (directorios) y acceder a los archivos que contiene.  
Para hacerlo correctamente, es importante entender cómo funcionan las **rutas absolutas** y **rutas relativas**, ya que ellas indican la ubicación exacta de un archivo o directorio dentro del sistema.

El sistema de archivos de Linux tiene una estructura **jerárquica**, organizada como un árbol que comienza desde el **directorio raíz (`/`)**, y desde allí se ramifican todos los demás directorios y archivos.

---

## Concepto de Ruta

Una **ruta (path)** es la dirección que señala la posición de un archivo o carpeta dentro del sistema.

Por ejemplo:

```bash
/home/abel/Documentos/proyecto
```

En esta ruta:
- `/` → Representa el **directorio raíz**.
- `home` → Contiene los directorios de los usuarios.
- `abel` → Carpeta personal del usuario “abel”.
- `Documentos/proyecto` → Subcarpetas dentro del directorio del usuario.

---

## Rutas Absolutas

Una **ruta absoluta** describe la ubicación **completa** de un archivo o carpeta **a partir del directorio raíz (`/`)**.  
Siempre comienza con una **barra inclinada (`/`)**.

### Características:
- No dependen de tu posición actual en el sistema.
- Empiezan siempre con `/`.
- Son más seguras y precisas al usarlas en scripts o tareas automatizadas.

### Ejemplos:

```bash
cd /home/abel/Documentos
ls /etc
cat /var/log/syslog
```

## Rutas Relativas

Una ruta relativa indica la ubicación **con respecto al directorio actual**.
No empieza con /, sino que parte del punto donde te encuentras.

### Características:

- Dependen del directorio en el que estás (puedes verlo con `pwd`).
- Son más cortas y cómodas para moverte dentro de un mismo árbol de directorios.
- Usan referencias como `.` y `..` para orientarse.

### Referencias importantes

| Símbolo | Significado                            |
| ------- | -------------------------------------- |
| `.`     | Directorio actual                      |
| `..`    | Directorio padre (uno superior)        |
| `~`     | Directorio personal del usuario actual |

### Ejemplos de rutas relativas

Supongamos que estás en `/home/abel/Documentos`:

```bash
cd proyectos          # Entra a la carpeta "proyectos" dentro de Documentos
cd ..                 # Sube al directorio padre: /home/abel
cd ./Documentos       # Vuelve a entrar al directorio Documentos
cd ~/Descargas        # Ir directamente al directorio Descargas del usuario
ls ../Imágenes        # Lista los archivos en la carpeta Imágenes, que está un nivel arriba
```

## Comandos útiles de navegación

| Comando | Descripción                                           | Ejemplo                    |
| ------- | ----------------------------------------------------- | -------------------------- |
| `pwd`   | Muestra el directorio actual                          | `pwd`                      |
| `ls`    | Lista los archivos y carpetas dentro de un directorio | `ls -l`                    |
| `cd`    | Cambia de directorio                                  | `cd /home/abel/Documentos` |
| `cd ..` | Sube al directorio padre                              | `cd ..`                    |
| `cd ~`  | Va al directorio personal del usuario                 | `cd ~`                     |

## Ejemplo práctico

Supongamos la siguiente estructura:

```bash
/home/abel
├── Documentos
│   └── proyectos
│       └── script.py
└── Descargas
```

Si estás en `/home/abel/Documentos`:

- Para ir a `proyectos`, usas una **ruta relativa**:

```bash
cd proyectos
```

- Para ir directamente desde cualquier lugar a esa carpeta, usas una **ruta absoluta**:

```bash
cd /home/abel/Documentos/proyectos
```

- Para subir al directorio padre (`/home/abel`):

```bash
cd ..
```

## Resumen

| Tipo de Ruta | Empieza con | Depende del directorio actual | Ejemplo                 |
| ------------ | ----------- | ----------------------------- | ----------------------- |
| Absoluta     | `/`         | No                          | `/home/abel/Documentos` |
| Relativa     | No          | Sí                          | `../Descargas`          |

## Buenas prácticas

- Usa rutas absolutas cuando necesites precisión (por ejemplo, en scripts).
- Usa rutas relativas cuando trabajes manualmente en una carpeta específica.
- Antes de ejecutar un comando, verifica tu ubicación con pwd.
- Usa ls para confirmar los archivos y carpetas disponibles en tu ubicación actual.

Dominar las rutas relativas y absolutas es fundamental para trabajar con eficacia en Linux.
Te permitirá moverte con confianza, evitar errores de ubicación y comprender mejor la estructura jerárquica del sistema.
