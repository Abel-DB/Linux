# ¿Qué es la Shell de Linux?

## Concepto General
La **Shell de Linux** es un **intérprete de comandos** que sirve como puente entre el usuario y el **núcleo del sistema operativo (kernel)**.  
Recibe órdenes en forma de texto (comandos), las interpreta y hace que el sistema las ejecute.  

En palabras simples, la **Shell es la interfaz de texto que te permite interactuar directamente con Linux**.

---

## Importancia de la Shell en Linux  
1. **Control total del sistema**: permite ejecutar tareas avanzadas sin necesidad de gráficos.  
2. **Automatización**: se pueden crear *scripts* para ahorrar tiempo en tareas repetitivas.  
3. **Ligereza y rapidez**: no depende de interfaces gráficas.  
4. **Flexibilidad**: existen diferentes shells con características y mejoras.  

---

## Tipos de Shell en Linux  
- **sh (Bourne Shell)** → La original, base de muchas otras.  
- **bash (Bourne Again Shell)** → La más usada por defecto en la mayoría de distros.  
- **zsh (Z Shell)** → Autocompletado avanzado y muy personalizable.  
- **fish (Friendly Interactive Shell)** → Sugerencias y resaltado de sintaxis.  
- **ksh (Korn Shell)** → Mezcla de características de Bourne y C Shell.  

---

## Diferencia entre Shell y Terminal  
- **Shell** → El intérprete de comandos (software).  
- **Terminal** → El programa o ventana donde usamos la Shell.  

Ejemplo: Abrir “Terminal” en Ubuntu lanza una ventana, pero lo que realmente ejecuta tus comandos es la **Shell (generalmente Bash)**.  

---

## Partes principales de la Shell (cuando entras a la terminal)  
Cuando abrimos una terminal, la Shell nos muestra un **prompt de comandos**, que es el espacio donde escribimos órdenes.  

Ejemplo de prompt típico en **bash**:

```bash
usuario@equipo:~$
```

### Explicación de las partes:

**1. usuario** → Nombre del usuario que inició sesión.

**2. @** → Separador entre usuario y equipo.

**3. equipo (hostname)** → Nombre del computador o servidor.

**4. :~** → Directorio actual (aquí `~` significa la carpeta personal del usuario).

**5. $** → Indica el tipo de usuario:

- `$` → Usuario normal.

- `#` → Usuario administrador (root).

## Ejemplo de uso en la Shell

Si en la terminal escribes:

```bash
pwd
```

La shel muestra

```bash
/home/usuario
```

Aqui:
- El **prompt** (`usuario@equipo:~$`) te dice dónde estás y quién eres.

- El **comando** (`pwd`) fue interpretado por la Shell.

- El **resultado** (`/home/usuario`) lo devolvió el sistema.
