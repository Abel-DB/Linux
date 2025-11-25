# Visualización de Ficheros y Directorios en Linux

La visualización de ficheros y directorios es una de las tareas más básicas y esenciales en la línea de comandos de Linux. Dominar estas herramientas te permitirá inspeccionar, identificar, ordenar y examinar el contenido del sistema de archivos de forma eficiente.

---

# 1. Comando principal: `ls`

El comando `ls` se utiliza para **listar archivos y directorios**.

### ✔ Uso básico

```bash
ls
```

Lista el contenido del directorio actual (sin archivos ocultos).

---

# 2. Opciones importantes de ls

## 2.1. Mostrar archivos ocultos (-a)

```bash
ls -a
```

## 2.2. Vista detallada (-l)

```bash
ls -l
```

## 2.3. Detallado + ocultos (-la)

```bash
ls -la
```

## 2.4. Ordenar por fecha (-t)

```bash
ls -lt
```

## 2.5. Ordenar al revés (-r)

```bash
ls -lr
```

## 2.6. Tamaños legibles (-h)

```bash
ls -lh
```

Vista completa recomendada

```bash
ls -lah

---
```

# 3. Identificación del tipo de fichero con ls

El primer carácter indica el tipo de fichero:

| Símbolo | Tipo de archivo           |
| ------- | ------------------------- |
| d       | Directorio                |
| -       | Archivo regular           |
| l       | Enlace simbólico          |
| c       | Dispositivo de caracteres |
| b       | Dispositivo de bloques    |
| s       | Socket                    |
| p       | FIFO / Pipe               |


Ejemplo:

```bash
drwxr-xr-x   carpeta/
-rw-r--r--   archivo.txt
lrwxrwxrwx   enlace -> archivo.txt
```

---

# 4. Visualización del contenido de archivos

## 4.1. cat — Ver archivo completo

```bash
cat archivo.txt
```

## 4.2. tac — Al revés (de abajo hacia arriba)

```bash
tac archivo.txt
```

## 4.3. less — Mejor opción para archivos grandes

```bash
less archivo.txt
```

Controles esenciales:

- ↑ / ↓ → navegar
- Space → avanzar página
- /texto → buscar
- n → siguiente resultado
- q → salir

## 4.4. more — Similar a less pero básico

```bash
more archivo.txt
```

## 4.5. Primeras líneas (head)

```bash
head archivo.txt
```

Primeras 20 líneas:

```bash
head -n 20 archivo.txt
```

## 4.6. Últimas líneas (tail)

```bash
tail archivo.txt
```

Últimas 20 líneas:

```bash
tail -n 20 archivo.txt
```

Modo seguimiento para logs:

```bash
tail -f archivo.log
```

---

# 5. Ver el tipo real de un archivo

`file`

```bash
file archivo.txt
file imagen.png
file script.sh
```

Salida típica:

```bash
script.sh: Bourne-Again shell script
imagen.png: PNG image data
```

---

# 6. Mostrar la ruta actual (absoluta)

```bash
pwd
```

---

# 7. Filtros útiles para visualizar archivos

## 7.1. Usar comodines

Archivos `.txt`:

```bash
ls *.txt
```

Archivos que empiezan con “pro”:

```bash
ls pro*
```

## 7.2. Ordenar por tamaño

```bash
ls -lSh
```

## 7.3. Listar solo directorios

```bash
ls -d */
```

## 7.4. Listar solo archivos

```bash
ls -p | grep -v /
```

---

# 8. Información detallada con stat

```bash
stat archivo.txt
```

Muestra:

- tamaño
- permisos
- propietario
- fechas de acceso y modificación
- tipo de archivo

---

# 9. Buenas prácticas

- Usa ls -lah como comando estándar para visualizar un directorio.
- Usa less en lugar de cat para archivos grandes.
- Usa tail -f para monitorear logs en tiempo real.
- Filtra con comodines para agilizar búsquedas.
