# Información de los comandos en Linux

Cuando trabajas en la Shell de Linux, es fundamental saber cómo obtener información sobre los comandos, sus opciones, argumentos y funcionamiento. Esto te ayuda a aprender rápidamente y usar correctamente cualquier comando.

## 1. `--help` (ayuda rápida)

`--help` es una opción estándar que tienen casi todos los comandos de Linux y permite ver un resumen rápido de cómo usar el comando, sus opciones y argumentos. Es útil para aprender comandos nuevos o recordar cómo funcionan sin abrir el manual completo (`man`).

### Sintaxis general

```bash
comando --help
```

- **comando** → nombre del comando que quieres consultar

- **--help** → opción que activa la ayuda rápida

**Ejemplos prácticos**

Ejemplo 1: `ls --help`

```bash
ls --help
```

Salida tipica:

```bash
Modo de empleo: ls [OPCIÓN]... [FICHERO]...
Muestra información acerca de los FICHEROs (del directorio actual por defecto).
Ordena las entradas alfabéticamente si no se especifica ninguna de las
opciones -cftuvSUX ni --sort.

Los argumentos obligatorios para las opciones largas son también obligatorios
para las opciones cortas.
  -a, --all                  no oculta las entradas que comienzan con .
  -A, --almost-all           no muestra las entradas . y .. implícitas
      --author               con -l, imprime el autor de cada fichero
  -b, --escape               imprime escapes en estilo C para los caracteres no
                             gráficos
      --block-size=SIZE      with -l, scale sizes by SIZE when printing them;
                             e.g., '--block-size=M'; see SIZE format below
```

Desglose:

- **Comando**: `ls`

- **Opción**: `--help`

- **Argumentos**: ninguno (pueden añadirse archivos o directorios)

- **Opciones disponibles**: `-a`, `-A`, `-b`

Ejemplo 2: `grep --help`

```bash
grep --help
```

Salida tipica:

```bash
Modo de empleo: grep [OPCIÓN]... PATRONES [FICHERO]...
Busca PATRONES en cada FICHERO.
Ejemplo: grep -i 'hola mundo' menu.h main.c
PATRONES puede contener varios patrones separados por líneas nuevas.

Selección e interpretación de patrón:
  -E, --extended-regexp     PATRONES son expresiones regulares extendidas (ERE)
  -F, --fixed-strings       PATRONES son cadenas
  -G, --basic-regexp        PATRONES son expresiones regulares básicas (BRE)
  -P, --perl-regexp         PATRONES son expresiones regulares en Perl
  -e, --regexp=PATRONES     utiliza PATRONES para encontrar coincidencias
  -f, --file=FICHERO        obtiene PATRONES de FICHERO
```

Desglose:

- **Comando**: `grep`

- **Opción**: `--help`

- **Argumentos**: PATRONES (lo que buscas) y [FICHERO] (archivo o archivos)

- **Opciones destacadas**: -E, -F, -G, -P, -e, -f

**Observaciones importantes**

1. `--help` **no modifica archivos ni realiza ninguna acción**, solo muestra información.

2. La información que muestra puede variar según la versión del comando y la distribución de Linux.

3. A veces se puede usar `-h` en lugar de `--help`, aunque `no todos los comandos lo soportan`.

---

## 2. `man` (manual completo)

`man` es la herramienta que permite acceder al **manual completo de un comando** en Linux. A diferencia de `--help`, que da un resumen rápido, `man` muestra información detallada sobre:

- Qué hace el comando  
- Opciones y argumentos disponibles  
- Ejemplos de uso  
- Notas sobre archivos de configuración y entorno  

---

### Sintaxis general

```bash
man comando
```

- comando → nombre del comando que quieres consultar

**Ejemplos prácticos**

Ejemplo 1: `man ls`

```bash
man ls
```

- Abre el manual completo de `ls`.

- Información típica que encontrarás:

  - Descripción del comando

  - Lista de opciones (-A, -a, -b, etc.)

  - Ejemplos de uso

  - Notas adicionales sobre comportamiento y entorno

Ejemplo 2: `man grep`

```bash
man grep
```

- Abre el manual completo de `grep`.

- Información incluida:

  - Descripción del comando y su propósito

  - Opciones y argumentos (-V, -e, -F, etc.)

  - Ejemplos de búsqueda

  - Explicación de patrones y expresiones regulares

**Navegación dentro de man**

- `flecha arriba/abajo` → moverse línea por línea

- `Page Up / Page Down` → moverse página por página

- `/palabra` → buscar palabra dentro del manual

- `n` → siguiente coincidencia en la búsqueda

- `q` → salir del manual

**Observaciones importantes**

1. `man` muestra **información detallada**, ideal para aprender un comando a fondo.

2. Algunos comandos tienen **más de un manual**, organizados en secciones. Por ejemplo:

  - `ls (1)` → comandos de usuario

  - `printf (3)` → funciones de librerías

3. Puedes abrir manuales de secciones específicas usando:

```bash
man 1 printf
```

---

## 3. `info` (manual más detallado y estructurado)

`info` es otra herramienta de Linux para consultar documentación de comandos.  
A diferencia de `man`, que muestra un manual lineal, `info` ofrece un **manual más estructurado**, dividido en secciones y nodos, lo que facilita navegar entre temas complejos.

---

### Sintaxis general

```bash
info comando
```

- `comando` → nombre del comando que quieres consultar

**Ejemplos prácticos**

Ejemplo 1: `info ls`

```bash
info ls
```

- Abre la documentación de `ls` con estructura jerárquica.

- Información que suele incluir:

  - Descripción general del comando

  - Opciones y argumentos

  - Ejemplos prácticos

  - Notas sobre funcionamiento avanzado

Ejemplo 2: `info tar`

```bash
info tar
```

- Permite navegar entre secciones: compresión, extracción, archivos y opciones avanzadas.

- Muy útil para comandos con muchas funcionalidades, como `tar`, `grep` o `find`.

**Navegación dentro de `info`**

- `n` → ir al siguiente nodo o sección

- `p` → ir al nodo o sección anterior

- `u` → ir al nodo superior

- `f` → buscar un nodo por nombre

- `q` → salir del manual

**Nota**: Los nodos funcionan como capítulos y subcapítulos, haciendo más fácil saltar entre temas relacionados.

**Observaciones importantes**

1. `info` proporciona **más detalle y estructura** que `man`, especialmente útil para comandos complejos.

2. No todos los comandos tienen documentación en `info`, pero la mayoría de los comandos principales de GNU sí.

3. Puedes combinar con búsquedas dentro de los nodos usando `/palabra`.

---

4. `whatis` (descripción corta)

`whatis` permite obtener una **descripción breve de un comando**, generalmente de una sola línea.  
Es útil cuando solo quieres **recordar rápidamente qué hace un comando** sin abrir el manual completo.

---

### Sintaxis general

```bash
whatis comando
```

- **comando** → nombre del comando que quieres consultar

**Ejemplos prácticos**

```bash
whatis ls
```

Salida tipica:

```bash
ls (1)               - list directory contents
```

- Muestra que `ls` es un **comando de usuario (sección 1)** y su función principal.

```bash
whatis grep
```

```bash
grep (1)             - print lines that match patterns
```

**Observaciones importantes**

1. Solo devuelve **una línea de descripción**, por lo que es ideal para consultas rápidas.

2. La información proviene de la base de datos de descripciones de comandos (`whatis database`).

3. Si no encuentra el comando, puede que necesites **actualizar la base de datos** con:

---

## 5. `apropos` (buscar comandos por palabra clave)

`apropos` busca comandos cuya **descripción contenga una palabra clave**, ideal si **no recuerdas el nombre exacto del comando**.

---

### Sintaxis general

```bash
apropos palabra_clave
```

- **palabra_clave** → término relacionado con la función que buscas.

Ejemplos prácticos

```bash
apropos copy
```

Salida tipica:

```bash
debconf-copydb (1)   - Copia una base de datos de debconf
Clone (3pm)          - recursively copy Perl datatypes
acl_copy_entry (3)   - copy an ACL entry
acl_copy_ext (3)     - copy an ACL from internal to external representation
acl_copy_int (3)     - copy an ACL from external to internal representation
archive_util (3)     - libarchive utility functions
```

- Muestra todos los comandos relacionados con “copy” y su breve descripción.

```bash
apropos list
```

- Muestra comandos relacionados con “list”, como `ls`, `dir`, etc.

**Observaciones importantes**

1. Útil cuando **no recuerdas el nombre exacto del comando**.

2. Devuelve coincidencias de la **descripción, no del nombre del comando**.

3. También depende de la **base de datos de `whatis`**, que se puede actualizar con `sudo mandb`.
