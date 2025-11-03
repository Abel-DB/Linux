
# Manejo de Atajos Útiles en la Shell de Linux

Los **atajos de teclado en la Shell (Bash)** permiten editar comandos, moverse por el texto, manejar procesos y navegar por el historial de manera más rápida y eficiente.

Son herramientas esenciales para cualquier usuario de Linux, ya que **aumentan la productividad y evitan escribir comandos repetidamente**.

---

## Atajos Más Usados

Estos son los atajos que deberías dominar primero, ya que se utilizan constantemente en la terminal.

### Edición y Movimiento del Cursor

| Atajo | Acción |
|-------|--------|
| `Ctrl + A` | Mueve el cursor al **inicio** de la línea. |
| `Ctrl + E` | Mueve el cursor al **final** de la línea. |
| `Alt + B` | Mueve el cursor una **palabra hacia atrás**. |
| `Alt + F` | Mueve el cursor una **palabra hacia adelante**. |
| `Ctrl + U` | Borra todo **desde el inicio hasta el cursor**. |
| `Ctrl + K` | Borra todo **desde el cursor hasta el final**. |
| `Ctrl + W` | Borra la **palabra anterior**. |
| `Ctrl + Y` | **Pega** el último texto borrado. |
| `Ctrl + L` | Limpia la pantalla (igual que `clear`). |

---

### Control de Comandos

| Atajo | Acción |
|-------|--------|
| `Ctrl + C` | **Detiene** el comando actual. |
| `Ctrl + Z` | **Suspende** el proceso actual (puedes reanudar con `fg`). |
| `Ctrl + D` | Cierra la sesión actual (igual que `exit`). |
| `!!` | Repite el **último comando ejecutado**. |
| `!n` | Ejecuta el **comando número n** del historial (`history`). |
| `!palabra` | Ejecuta el **último comando que empieza con esa palabra**. |

---

### Historial y Autocompletado

| Atajo | Acción |
|-------|--------|
| `↑` / `↓` | Navega por los **comandos anteriores**. |
| `Tab` | **Autocompleta** nombres de archivos, directorios o comandos. |
| `Ctrl + R` | Busca **comandos anteriores** escribiendo parte del texto. |
| `Ctrl + G` | Cancela la búsqueda inversa (`Ctrl + R`). |
| `history` | Muestra el **historial completo de comandos**. |

---

### Manejo de Procesos

| Atajo | Acción |
|-------|--------|
| `Ctrl + S` | **Pausa** la salida en pantalla. |
| `Ctrl + Q` | **Reanuda** la salida pausada. |
| `Ctrl + T` | Intercambia los dos últimos caracteres antes del cursor. |
| `Ctrl + _` | **Deshace** el último cambio (undo básico). |

---

## Lista Completa de Atajos en Bash

A continuación se detallan todos los atajos disponibles, organizados por categoría.

---

### Movimiento del Cursor
```bash
Ctrl + A → Ir al inicio de la línea
Ctrl + E → Ir al final de la línea
Alt + F → Adelantar una palabra
Alt + B → Retroceder una palabra
Ctrl + F → Adelantar un carácter
Ctrl + B → Retroceder un carácter
```

### Edición de Texto
```bash
Ctrl + U → Cortar desde el inicio hasta el cursor
Ctrl + K → Cortar desde el cursor hasta el final
Ctrl + W → Cortar palabra anterior
Alt + D → Cortar palabra siguiente
Ctrl + Y → Pegar el último texto cortado
Ctrl + _ → Deshacer (undo)
```

### Control de Comandos y Procesos
```bash
Ctrl + C → Cancelar comando en ejecución
Ctrl + Z → Suspender proceso
Ctrl + D → Salir o cerrar sesión
Ctrl + L → Limpiar pantalla
Ctrl + S → Pausar salida en terminal
Ctrl + Q → Reanudar salida
```

### Historial y Autocompletado
```bash
↑ / ↓ → Navegar por historial
Ctrl + R → Buscar comando anterior
Ctrl + G → Cancelar búsqueda inversa
!! → Repetir último comando
!n → Ejecutar comando número n
!palabra → Ejecutar último comando que empieza con palabra
Tab → Autocompletar
```

### Otros Útiles
```bash
Ctrl + T → Intercambiar caracteres
Alt + . → Insertar el último argumento del comando anterior
Ctrl + X, Ctrl + E → Editar línea actual en el editor predeterminado
```

## Recomendación

Practica los atajos más comunes diariamente.
Por ejemplo:

- Usa Ctrl + A y Ctrl + E para moverte rápido por los comandos.
- Usa Ctrl + R para buscar comandos previos sin tener que escribirlos de nuevo.
- Usa !! para repetir el último comando, ideal si olvidaste poner sudo.

## Consejo Final

Puedes consultar todos los atajos disponibles escribiendo.

```bash
man readLine
```

Este manual muestra todos los atajos que utiliza Bash para la edicion de linea de comandos.
