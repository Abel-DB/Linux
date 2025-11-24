# Creación de Archivos y Directorios en Linux

Este apunte cubre todo lo esencial sobre la creación y gestión de archivos y directorios, además de los editores de texto, incluyendo **Neovim (nvim)** que es el que estás aprendiendo.

---

## 1. Creación de Directorios

### 1.1. Sensibilidad a mayúsculas y minúsculas
Linux distingue entre mayúsculas y minúsculas (case-sensitive).  
Ejemplo:

- proyecto
- Proyecto
- PROYECTO

Son **tres directorios diferentes**.

---

### 1.2. Evitar espacios en los nombres
No es recomendable usar espacios, ya que complica el uso en terminal y scripts.

Incorrecto:

```bash
mkdir Mi Carpeta
```

Correcto:

```bash
mkdir mi_carpeta
mkdir mi-carpeta
```

Si necesitas espacios:

```bash
mkdir "Mi Carpeta"
mkdir Mi\ Carpeta
```

---

### 1.3. Comandos para crear directorios

- Crear un directorio:

```bash
mkdir carpeta
```

- Crear varios directorios:

```bash
mkdir dir1 dir2 dir3
```

- Crear directorios anidados (-p):

```bash
mkdir -p proyectos/2025/enero
```

- Crear directorio con permisos específicos (-m):

```bash
mkdir -m 750 privada
```

- Mostrar lo que se crea (-v):

```bash
mkdir -v demo
```

- Crear y entrar al directorio:

```bash
mkdir proyecto && cd proyecto
```

---

### 1.4. Verificación

```bash
ls -ld carpeta
```

Si tienes tree:

```bash
tree -L 2 .
```

---

### 1.5. Buenas prácticas

- Usa nombres en minúsculas
- No uses espacios
- Usa mkdir -p en scripts para evitar errores
- Mantén la estructura de carpetas clara
- Ajusta permisos si trabajas con varios usuarios

---

## 2. Creación de Archivos

---

### 2.1. Crear archivos vacíos

```bash
touch archivo.txt
```

Crear varios archivos:

```bash
touch a.txt b.txt c.txt
```

---

### 2.2. Crear archivos con contenido inicial

- Sobrescribir contenido:

```bash
echo "Hola Linux" > saludo.txt
```

- Añadir contenido sin borrar lo anterior:

```bash
echo "Nueva línea" >> saludo.txt
```

- Crear archivo con varias líneas:

```bash
cat > notas.txt <<EOF
Primera línea
Segunda línea
Tercera línea
EOF
```

### 2.3. Comprobar archivos y directorios

- Listar detalles:

```bash
ls -l
```

- Ver solo el directorio:

```bash
ls -ld carpeta
```

- Crear estructura y visualizarla:

```bash
mkdir -p proyecto/{src,docs,tests}
tree proyecto
```

---

## 3. Editores de Texto

Editar archivos es esencial para configuraciones, scripts y desarrollo.

### 3.1. Nano — Editor sencillo

Abrir archivo:

```bash
nano archivo.txt
```

Atajos importantes:

- Ctrl + O → Guardar
- Ctrl + X → Salir
- Ctrl + K → Cortar línea
- Ctrl + U → Pegar
- Ctrl + W → Buscar

Ideal para principiantes.

### 3.2. Vim — Editor clásico

Abrir archivo:

```bash
vim archivo.txt
```

Modos principales:

- Normal: navegar, borrar, copiar
- Insert: escribir texto (i)
- Visual: seleccionar texto (v)

Comandos básicos:

- :w → Guardar
- :q → Salir
- :wq → Guardar y salir
- dd → Borrar línea
- yy → Copiar línea
- p → Pegar

### 3.3. Neovim (nvim) — Editor moderno

Este es el editor que estás aprendiendo.
Abrir archivo:

```bash
nvim archivo.txt
```

Modos:

- i → INSERT
- Esc → NORMAL
- v → VISUAL

Comandos básicos:

- :w → Guardar
- :q → Salir
- :wq → Guardar y salir
- dd → Borrar línea
- yy → Copiar
- p → Pegar

Ejemplo práctico:

```bash
nvim notas.txt
```

- Presiona 'i' y escribe: Aprendiendo Neovim en Linux
- Presiona 'Esc' y luego escribe ':wq' para guardar y salir

### 3.4. ¿Cuál usar?

| Editor | Dificultad | Ideal para                                |
| ------ | ---------- | ----------------------------------------- |
| Nano   | Fácil      | Ediciones rápidas                         |
| Vim    | Medio      | Usuarios avanzados                        |
| Neovim | Alto       | Programación, personalización y scripting |

Conclusión

Con estos conocimientos puedes:

- Crear y organizar directorios correctamente
- Crear archivos vacíos o con contenido
- Editar archivos con Nano, Vim o Neovim
- Seguir buenas prácticas de nombres y permisos

Todo esto es fundamental para trabajar profesionalmente en Linux.
